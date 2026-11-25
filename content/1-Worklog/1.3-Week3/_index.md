---
title: "Week 3 Worklog"
date: 2026-11-25
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

# **Week 3 Worklog — ReLoop Specification Review, Backend Business Rules, AI Day Watch Party & Fireside Chat with Dr. Werner Vogels**

## **1. Weekly Objectives**

- Read the ReLoop specification v1.0 from a backend point of view and write down every question that affects data or APIs.
- Write the backend rules (states, who may change them, how money is stored) into the shared decision log QĐ-01 → QĐ-45.
- Take the **Backend Engineer** role in the team.
- Attend Event 2 (AWS Cloud and AI Day Hanoi – Watch Party) and Event 3 (Fireside Chat with Dr. Werner Vogels).

## **2. Weekly Execution Schedule**

| Day           | Task Description                                                                                                                                                                                                                                                                                                                                                                          | Start Date | Completion Date | Reference Material                                                                                                                                  |
| :------------ | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :--------- | :-------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Monday**    | • Read the 1,189-paragraph specification v1.0 and list my backend questions: which states a listing can be in, who may see a quote, how prices are stored, what happens when a deal is cancelled                                                                                                                                                                                          | 28/09/2026 | 28/09/2026      | [Proposal](../../2-proposal/), [AWS Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html)          |
| **Tuesday**   | • Attend [Event 2: AWS Cloud and AI Day Hanoi – Watch Party](../../4-eventparticipated/4.2-event2/) (08:00 AM – 05:00 PM at the AWS Vietnam Office, Level 26, Bitexco Financial Tower). Watched the keynote from Hanoi on Agentic AI, data foundation and Cloud modernization, then joined the on-site discussions on moving AI agents into real operation and keeping costs down; lesson: settle the cost you can accept before choosing tools                                                                    | 29/09/2026 | 29/09/2026      | [Event 2](../../4-eventparticipated/4.2-event2/), [AWS Cost Explorer](https://docs.aws.amazon.com/cost-management/latest/userguide/ce-what-is.html) |
| **Wednesday** | • Map each user role (Guest, Partner tier 1, Partner tier 2, Admin, Finance Admin) to the API actions it may call; this map later became the 4 Cognito groups `Admins`, `FinanceAdmins`, `Partners`, `Owners`                                                                                                                                                                             | 30/09/2026 | 30/09/2026      | [Amazon Cognito User Pool Groups](https://docs.aws.amazon.com/cognito/latest/developerguide/cognito-user-pools-user-groups.html)                    |
| **Thursday**  | • Write my backend decisions into the decision log: listing states (`PENDING_REVIEW` → `ACTIVE` → `MATCHED` → `COMPLETED` / `EXPIRED` / `CANCELLED`), quote and transaction states, which actor (`OWNER`, `PARTNER`, `ADMIN`, `SYSTEM`) may make each change, and all prices stored as integer VND                                                                                        | 01/10/2026 | 01/10/2026      | [ReLoop Repository](https://github.com/madlyham/ReLoop/tree/main/backend/api) (`src/domain/stateMachines.ts`)                                       |
| **Friday**    | • Attend [Event 3: Fireside Chat with Dr. Werner – Navigating the Future of Cloud & AI in Vietnam](../../4-eventparticipated/4.3-event3/) (10:30 AM – 12:00 PM at the AWS Vietnam Office, Level 26, Bitexco Financial Tower). Dr. Werner talked about the "Renaissance Developer" and why engineers stay responsible for the code AI writes. Take the **Backend Engineer** role: the DynamoDB data layer and the business rules | 02/10/2026 | 02/10/2026      | [Event 3](../../4-eventparticipated/4.3-event3/), [AWS IAM Docs](https://docs.aws.amazon.com/iam/)                                                  |

## **3. Key Achievements & Outcomes**

### **Theoretical Foundation**

- Learned that a decision with an ID (for example QĐ-07) ends repeated debates and gives code reviews a clear reference.
- Took from Dr. Werner Vogels' talk that a backend must expect failure: retries, idempotent writes and conditional updates are part of the design.
- Understood the FinOps idea from AI Day: agree on what the system may cost per month before choosing services.

### **Environment Setup & Configuration**

- Backend rules written in the shared decision log: state lists, allowed transitions and the actor for each transition.
- Role-to-action map that the backend authorization follows.

### **Practical Skills & Operations**

- Turned vague parts of the specification into precise state rules that could be coded directly as state machines.
- Attended the full-day AI Day watch party and the fireside chat with Dr. Werner Vogels at Bitexco Financial Tower.
