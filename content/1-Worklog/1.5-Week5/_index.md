---
title: "Week 5 Worklog"
date: 2026-11-25
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

# **Week 5 Worklog — Background AI Listing Job: aiService.ts, Async Lambda Self-Invoke & AI Output Validation**

## **1. Weekly Objectives**

- Run AI listing analysis in the background so the API answers at once instead of waiting for the model.
- Make the job safe to run twice: a duplicate or late run must never overwrite a finished result.
- Check every AI answer on the server before it can be saved into a listing.

## **2. Weekly Execution Schedule**

| Day           | Task Description                                                                                                                                                                                                                                                | Start Date | Completion Date | Reference Material                                                                                                                                                                                                                                      |
| :------------ | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :--------- | :-------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Monday**    | • Study the pieces my job depends on: the photo store (`ImageStore.read`, moderation check) and the `Analyzer` interface that calls Amazon Bedrock                                                                                                              | 12/10/2026 | 12/10/2026      | [Amazon Bedrock Docs](https://docs.aws.amazon.com/bedrock/), [Workshop 5.8](../../5-workshop/5.8-ai-processing/)                                                                                                                                        |
| **Tuesday**   | • Design the analysis item `USER#<id>` / `AI#<analysisId>` with status `PENDING` → `COMPLETED` / `FAILED`: the create call returns `202` at once and the client polls the result                                                                                | 13/10/2026 | 13/10/2026      | [ReLoop Repository](https://github.com/madlyham/ReLoop/tree/main/backend/api) (`src/store/keys.ts`)                                                                                                                                                     |
| **Wednesday** | • Implement `create()` in `aiService.ts`: accept only the user's own photo keys, at most 3 photos per analysis, require moderated photos, write the `PENDING` item, then start the worker with a Lambda self-invoke (`InvocationType=Event`)                    | 14/10/2026 | 14/10/2026      | [Lambda Asynchronous Invocation](https://docs.aws.amazon.com/lambda/latest/dg/invocation-async.html), [ReLoop Repository](https://github.com/madlyham/ReLoop/tree/main/backend/api) (`src/modules/ai/aiService.ts`)                                     |
| **Thursday**  | • Implement the worker `run()`: it only works on a `PENDING` item and saves with a versioned conditional write, so a duplicate run cannot overwrite a finished result; on any error it saves `FAILED` with a message asking the seller to fill the form by hand | 15/10/2026 | 15/10/2026      | [DynamoDB Condition Expressions](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Expressions.ConditionExpressions.html), [ReLoop Repository](https://github.com/madlyham/ReLoop/tree/main/backend/api) (`src/modules/ai/aiService.ts`) |
| **Friday**    | • Add server-side checks of every AI field (title, category, brand, model, condition) before it is saved; test the full job with in-memory fakes and with real laptop and phone photos                                                                          | 16/10/2026 | 16/10/2026      | [Bedrock Tool Use](https://docs.aws.amazon.com/bedrock/latest/userguide/tool-use.html), [ReLoop Repository](https://github.com/madlyham/ReLoop/tree/main/backend/api) (`src/shared/validate.ts`)                                                        |

## **3. Key Achievements & Outcomes**

### **Theoretical Foundation**

- Learned how an asynchronous Lambda invoke lets a slow task run after the API has already answered.
- Understood optimistic locking with a version number: a write succeeds only if nobody changed the item since it was read.

### **Environment Setup & Configuration**

- `aiService.ts` with `create()`, `get()` and the worker `run()`; analysis items `USER#<id>` / `AI#<analysisId>`.
- Worker started by Lambda self-invoke on AWS and run right after the response in local tests.

### **Practical Skills & Operations**

- The API returns `202` at once and the client gets the result by polling.
- An AI answer that does not match the listing schema is never saved.
