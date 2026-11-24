---
title: "Week 10 Worklog"
date: 2026-11-25
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---

# **Week 10 Worklog — Load-Test Re-run: 5xx from 26% to 0, Throttling Check & Results Write-up**

## **1. Weekly Objectives**

- Re-run the Week 8 load test now that Lambda concurrency is 1,000, under the same conditions.
- Confirm that overload ends in a clean `429`, not a `5xx`.
- Write the before and after results down for the final report.

## **2. Weekly Execution Schedule**

| Day           | Task Description                                                                                                                            | Start Date | Completion Date | Reference Material                                                                                                                                                                                          |
| :------------ | :------------------------------------------------------------------------------------------------------------------------------------------ | :--------- | :-------------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Monday**    | • Prepare the re-run with the same 80 parallel requests and the same routes as the Week 8 baseline (26% `5xx` at a concurrency limit of 10) | 16/11/2026 | 16/11/2026      | [Lambda Concurrency](https://docs.aws.amazon.com/lambda/latest/dg/lambda-concurrency.html)                                                                                                                  |
| **Tuesday**   | • Run the load test with Lambda concurrency at 1,000: the `5xx` rate drops from 26% to 0                                                    | 17/11/2026 | 17/11/2026      | [Lambda Concurrency](https://docs.aws.amazon.com/lambda/latest/dg/lambda-concurrency.html)                                                                                                                  |
| **Wednesday** | • Read the Lambda metrics in CloudWatch for the test window (`Duration`, `Errors`, `Throttles`); average duration is about 144 ms           | 18/11/2026 | 18/11/2026      | [Lambda Metrics](https://docs.aws.amazon.com/lambda/latest/dg/monitoring-metrics.html), [Workshop 5.10](../../5-workshop/5.10-monitoring/)                                                                  |
| **Thursday**  | • Send a burst above the API limit (20 req/s, burst 50) and confirm the extra requests get `429` instead of `5xx`                           | 19/11/2026 | 19/11/2026      | [HTTP API Throttling](https://docs.aws.amazon.com/apigateway/latest/developerguide/http-api-throttling.html), [ReLoop Repository](https://github.com/madlyham/ReLoop/blob/main/terraform/api.tf) (`api.tf`) |
| **Friday**    | • Write up the before and after numbers (26% → 0 `5xx`, about 144 ms average duration, `429` above the limit) for the final report          | 20/11/2026 | 20/11/2026      | [Proposal](../../2-proposal/)                                                                                                                                                                               |

## **3. Key Achievements & Outcomes**

### **Theoretical Foundation**

- Learned the difference between failing under load (`5xx`) and pushing back on purpose (`429`), and why clients can safely retry the second one.
- Understood that a fair before-and-after test must keep the same load, routes and data.

### **Environment Setup & Configuration**

- Repeatable load test with 80 parallel requests, run against the Week 8 baseline.
- CloudWatch view of `Duration`, `Errors` and `Throttles` for the test window.

### **Practical Skills & Operations**

- Measured `5xx` falling from 26% to 0 after the concurrency raise.
- Confirmed that requests above the API limit get `429`, and recorded every number for the final report.
