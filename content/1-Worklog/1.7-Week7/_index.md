---
title: "Week 7 Worklog"
date: 2026-11-25
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

# **Week 7 Worklog — Smart Plushies Community Event, AI Job Updates for Kimi K3 & Stale-Job Guard**

## **1. Weekly Objectives**

- Attend Event 5 (Smart Plushies for Children with Operation Smile Vietnam).
- Keep my AI job working when the model changes to Kimi K3, and record which model produced each result.
- Update the AI output checks for the new output fields.
- Stop an analysis from staying `PENDING` forever when the worker dies.

## **2. Weekly Execution Schedule**

| Day           | Task Description                                                                                                                                                                                                                                                                                                              | Start Date | Completion Date | Reference Material                                                                                                                                                                                       |
| :------------ | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :--------- | :-------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Monday**    | • Attend [Event 5: Smart Plushies for Children – In Collaboration with Operation Smile Vietnam](../../4-eventparticipated/4.5-event5/) (01:30 PM – 03:30 PM in the EC2 Room, Level 36, AWS Vietnam Office, Bitexco Financial Tower). We assembled and programmed interactive plushies for children treated by Operation Smile | 26/10/2026 | 26/10/2026      | [Event 5](../../4-eventparticipated/4.5-event5/)                                                                                                                                                         |
| **Tuesday**   | • Save `modelId` on every analysis item, so results from the old and the new model can be compared later                                                                                                                                                                                                                      | 27/10/2026 | 27/10/2026      | [ReLoop Repository](https://github.com/madlyham/ReLoop/tree/main/backend/api) (`src/modules/ai/aiService.ts`)                                                                                            |
| **Wednesday** | • Re-test my AI job end to end after AI moved to Kimi K3 on Bedrock (`global.moonshotai.kimi-k3`) on 28/10/2026, using real device photos                                                                                                                                                                                     | 28/10/2026 | 28/10/2026      | [Amazon Bedrock Docs](https://docs.aws.amazon.com/bedrock/), [ReLoop Repository](https://github.com/madlyham/ReLoop/blob/main/terraform/variables.tf) (`variables.tf`)                                   |
| **Thursday**  | • Update the server-side checks for the new AI output fields `observedTextAndLabels` and `identifiedComponents`, and re-test Vietnamese text with diacritics                                                                                                                                                                  | 29/10/2026 | 29/10/2026      | [Bedrock Tool Use](https://docs.aws.amazon.com/bedrock/latest/userguide/tool-use.html), [ReLoop Repository](https://github.com/madlyham/ReLoop/tree/main/backend/api) (`src/shared/validate.ts`)         |
| **Friday**    | • Add a stale-job guard in `get()`: the worker Lambda times out at 180 s, so an analysis still `PENDING` after 4 minutes is closed as `FAILED` and the seller can fill the form by hand                                                                                                                                       | 30/10/2026 | 30/10/2026      | [Lambda Timeout](https://docs.aws.amazon.com/lambda/latest/dg/configuration-timeout.html), [ReLoop Repository](https://github.com/madlyham/ReLoop/tree/main/backend/api) (`src/modules/ai/aiService.ts`) |

## **3. Key Achievements & Outcomes**

### **Theoretical Foundation**

- Learned that an async worker with no dead-letter queue can disappear silently, so the read path must detect a job that never finished.
- Learned to keep a strict schema check on AI output, so a model change cannot break saved data.

### **Environment Setup & Configuration**

- Analysis items store `modelId`; AI output checks cover `observedTextAndLabels` and `identifiedComponents`.
- Stale-job limit of 4 minutes, above the 180 s worker timeout.

### **Practical Skills & Operations**

- My AI job kept working after the switch to Kimi K3.
- Helped assemble interactive plushies for children at the Operation Smile Vietnam event.
