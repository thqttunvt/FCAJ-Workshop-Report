---
title: "Week 6 Worklog"
date: 2026-11-25
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

# **Week 6 Worklog — Scan-Free Background Timers (timers.ts), EventBridge 15-Minute Sweep & Cloud & AI Infrastructure Meetup**

## **1. Weekly Objectives**

- Give the backend a way to run work at a set time (listing expiry, transaction reminders) without scanning the table.
- Connect the sweep to Amazon EventBridge so it runs every 15 minutes on AWS.
- Make every timer safe to run late or twice.
- Attend Event 4 (Cloud & AI Infrastructure Meetup).

## **2. Weekly Execution Schedule**

| Day           | Task Description                                                                                                                                                                                                                                                                                                    | Start Date | Completion Date | Reference Material                                                                                                                                                                                                        |
| :------------ | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :--------- | :-------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Monday**    | • Design timer items grouped by hour: `TIMER#<YYYY-MM-DDTHH>` / `<kind>#<id>`, so the sweep reads a few hour buckets with `Query` instead of a `Scan`                                                                                                                                                               | 19/10/2026 | 19/10/2026      | [DynamoDB Best Practices](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/best-practices.html), [ReLoop Repository](https://github.com/madlyham/ReLoop/tree/main/backend/api) (`src/store/keys.ts`)      |
| **Tuesday**   | • Implement `timerOp()` and `TimerSweeper` in `timers.ts`: read the buckets from 72 hours ago up to now, run each timer that is due, delete it after success, and keep a failed one so the next sweep retries it                                                                                                    | 20/10/2026 | 20/10/2026      | [ReLoop Repository](https://github.com/madlyham/ReLoop/tree/main/backend/api) (`src/modules/jobs/timers.ts`)                                                                                                              |
| **Wednesday** | • Add the timer kinds `LISTING_EXPIRE` (listings close after 7 days), `LISTING_MATCH`, `TX_REMIND`, `TX_AUTO_COMPLETE` and `TX_CANCEL`, and a hook for periodic jobs such as the monthly fee run                                                                                                                    | 21/10/2026 | 21/10/2026      | [ReLoop Repository](https://github.com/madlyham/ReLoop/tree/main/backend/api) (`src/modules/jobs/timers.ts`)                                                                                                              |
| **Thursday**  | • Connect the sweep to an EventBridge rule `rate(15 minutes)` that invokes the API Lambda, and log `timer_sweep` / `timer_failed` events for CloudWatch                                                                                                                                                             | 22/10/2026 | 22/10/2026      | [EventBridge Scheduled Rules](https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-create-rule-schedule.html), [ReLoop Repository](https://github.com/madlyham/ReLoop/blob/main/terraform/events.tf) (`events.tf`) |
| **Friday**    | • Test late and duplicate runs with a fake clock: each handler re-reads the current state first, so a timer for a listing that is already closed does nothing                                                                                                                                                       | 23/10/2026 | 23/10/2026      | [Workshop 5.9](../../5-workshop/5.9-eventbridge/)                                                                                                                                                                         |
| **Saturday**  | • Attend [Event 4: Cloud & AI Infrastructure Meetup](../../4-eventparticipated/4.4-event4/) (10:30 AM – 12:00 PM at the AWS Vietnam Office, Level 26, Bitexco Financial Tower). Five talks from Revve AI, STYL Solutions, AWS Student Builder Group HCMUTE and ACB covered Vietnamese Voice AI, AWS RAM with SCPs, pentesting with Security Agent, Bedrock AgentCore and a 24/7 Kiro Crew agent | 24/10/2026 | 24/10/2026      | [Event 4](../../4-eventparticipated/4.4-event4/)                                                                                                                       |

## **3. Key Achievements & Outcomes**

### **Theoretical Foundation**

- Learned how time-bucketed keys turn "find everything that is due" into a few cheap `Query` calls.
- Understood why background jobs must be idempotent: a scheduler may run late, and a retry may run the same work twice.

### **Environment Setup & Configuration**

- `timers.ts` with 5 timer kinds, a 72-hour lookback and retry on failure.
- EventBridge rule `rate(15 minutes)` calling the API Lambda.

### **Practical Skills & Operations**

- Listings now close by themselves after 7 days without any table scan.
- Tested late and duplicate sweeps; neither changes data that is already final.
