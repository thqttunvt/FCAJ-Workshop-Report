---
title: "Week 12 Worklog"
date: 2026-11-25
weight: 12
chapter: false
pre: " <b> 1.12. </b> "
---

# **Week 12 Worklog — Final Report, Live Demo of My Backend Flows & Handover [Planned]**

> **Status:** Planned (upcoming sprint: 30/11/2026 – 04/12/2026; last updated 25/11/2026).

## **1. Weekly Objectives**

- Finish my internship report with the verified results from my own work (data model, background jobs, AI job, matching, load test).
- Demo the backend flows I built: AI listing, branch matching and listing expiry.
- Hand over clear notes on my modules so others can run and change them without me.

## **2. Weekly Execution Schedule**

| Day           | Planned Task Description                                                                                                         | Target Date | Status  | Reference Material                                                                                                                                                                                               |
| :------------ | :------------------------------------------------------------------------------------------------------------------------------- | :---------- | :------ | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Monday**    | • Write my part of the final report: key design, timers, background matching and the AI job, with the reasons behind each choice | 30/11/2026  | Planned | [ReLoop Repository](https://github.com/madlyham/ReLoop/tree/main/backend/api) (`src/store/keys.ts`), [AWS Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html) |
| **Tuesday**   | • Finish the report: load-test results (26% → 0 `5xx`), the $11.70/month cost breakdown and lessons learned                      | 01/12/2026  | Planned | [Proposal](../../2-proposal/), [AWS Cost Explorer](https://docs.aws.amazon.com/cost-management/latest/userguide/ce-what-is.html)                                                                                 |
| **Wednesday** | • Rehearse the demo of my flows with test accounts: AI listing from photos, matching to nearby branches, listing expiry          | 02/12/2026  | Planned | [Workshop 5.11](../../5-workshop/5.11-end-to-end-verification/)                                                                                                                                                  |
| **Thursday**  | • Present my flows in the final live demo to the AWS mentors and answer questions on the backend design                          | 03/12/2026  | Planned | [Proposal](../../2-proposal/), [Workshop](../../5-workshop/)                                                                                                                                                     |
| **Friday**    | • Hand over notes on my modules (key formats in `keys.ts`, timer kinds, matching rules, AI limits) and close the internship      | 04/12/2026  | Planned | [ReLoop Repository](https://github.com/madlyham/ReLoop)                                                                                                                                                          |

## **3. Expected Outcomes**

### **Theoretical Foundation**

- Consolidate the lesson that clear documentation is part of the product: someone else must be able to run my code without me.
- Sum up the 12-week path from self-studying AWS basics to building the background jobs of a serverless backend.

### **Environment Setup & Configuration**

- Final report and handover notes for my modules in place.
- My modules running on the ReLoop stack within the AWS credit window (until 28/02/2027).

### **Practical Skills & Operations**

- Deliver a smooth live demo of my flows.
- Explain my backend trade-offs (single table, time-bucketed timers, async jobs, geohash matching) clearly during mentor Q&A.
