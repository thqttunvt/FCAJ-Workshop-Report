---
title: "Week 9 Worklog"
date: 2026-11-25
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---

# **Week 9 Worklog — Proposal Part 2 Backend Sections, Cost Explorer Review & Cloud Mastery Event**

## **1. Weekly Objectives**

- Write the backend parts of Proposal Part 2 (data model and background processing) from what is really in the code.
- Check the real AWS spend in Cost Explorer and put the figures into the proposal.
- Finish my sections before the submission on 13/11/2026.
- Attend Event 6 (Cloud Mastery) at the AWS Vietnam Office.

## **2. Weekly Execution Schedule**

| Day           | Task Description                                                                                                                                                                                                                                                                       | Start Date | Completion Date | Reference Material                                                                                                                             |
| :------------ | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :--------- | :-------------- | :--------------------------------------------------------------------------------------------------------------------------------------------- |
| **Monday**    | • Collect the facts for my Proposal Part 2 sections from the code: key design and access patterns, the background jobs (sweep, matching, AI job) and their limits                                                                                                                      | 09/11/2026 | 09/11/2026      | [Proposal](../../2-proposal/), [ReLoop Repository](https://github.com/madlyham/ReLoop/tree/main/backend/api) (`src/store/keys.ts`)             |
| **Tuesday**   | • Write the storage part: one DynamoDB table with zero scans, a market feed split by month, and all money stored as integer VND                                                                                                                                                        | 10/11/2026 | 10/11/2026      | [Proposal](../../2-proposal/), [DynamoDB Best Practices](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/best-practices.html) |
| **Wednesday** | • Write the background-processing part: the EventBridge 15-minute sweep over hour buckets, matching to branches within 1–15 km (5 km first), and the AI job (`202` + polling, 3 photos, 20 analyses per user per day)                                                                  | 11/11/2026 | 11/11/2026      | [Proposal](../../2-proposal/), [Workshop 5.9](../../5-workshop/5.9-eventbridge/)                                                               |
| **Thursday**  | • Review per-service spend in Cost Explorer: the stack runs at about $11.70/month, of which $10.00 is the CloudFront WAF web ACL and about $1.70 is usage; add the figures to the proposal                                                                                             | 12/11/2026 | 12/11/2026      | [AWS Cost Explorer](https://docs.aws.amazon.com/cost-management/latest/userguide/ce-what-is.html)                                              |
| **Friday**    | • Proofread my sections against the code one last time and hand them in for **Proposal Part 2** (submitted 13/11/2026)                                                                                                                                                                 | 13/11/2026 | 13/11/2026      | [Proposal](../../2-proposal/)                                                                                                                  |
| **Saturday**  | • Attend [Event 6: Cloud Mastery – Cloud Sharing Session for Students](../../4-eventparticipated/4.6-event6/) (morning, AWS Vietnam Office, Level 26, Bitexco Financial Tower). A long open Q&A on cloud careers and skills, closed by a live Quiz.com game with more than 100 players | 14/11/2026 | 14/11/2026      | [Event 6](../../4-eventparticipated/4.6-event6/)                                                                                               |

## **3. Key Achievements & Outcomes**

### **Theoretical Foundation**

- Learned to write technical documentation from the code, not from memory, so every number in it can be checked.
- Understood from the real bill that a fixed fee (the WAF web ACL) can cost far more than all the pay-per-request services together.

### **Environment Setup & Configuration**

- Backend sections of Proposal Part 2 (storage and background processing) written and handed in on 13/11/2026.
- Real Cost Explorer figures (about $11.70/month) included in the proposal.

### **Practical Skills & Operations**

- Explained the backend design in plain words for readers outside the team.
- Read Cost Explorer by service and linked each cost to the part of the system that causes it.
