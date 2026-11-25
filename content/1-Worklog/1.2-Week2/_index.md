---
title: "Week 2 Worklog"
date: 2026-11-25
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

# **Week 2 Worklog — Self-Study of Serverless Services (S3, DynamoDB, Lambda, API Gateway), AWS Cost Basics & Buildrathon Kickoff**

## **1. Weekly Objectives**

- Study the four serverless services a backend uses every day: S3, DynamoDB, Lambda and API Gateway.
- Understand how AWS bills these services and where to watch the cost (credits, Cost Explorer, Budgets).
- Try the services on my own in the Console to connect the theory with what I see.
- Attend Event 1 (Buildrathon Kickoff) and pick the capstone topic with the team.

## **2. Weekly Execution Schedule**

| Day           | Task Description                                                                                                                                                                                                                                                                                                                                                          | Start Date | Completion Date | Reference Material                                                                                                                                                                                         |
| :------------ | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :--------- | :-------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Monday**    | • Study Amazon S3: buckets and objects, Block Public Access, encryption, versioning, lifecycle rules and CORS                                                                                                                                                                                                                                                             | 21/09/2026 | 21/09/2026      | [Amazon S3 Docs](https://docs.aws.amazon.com/s3/)                                                                                                                                                          |
| **Tuesday**   | • Study presigned URLs: how they give temporary access to one object so the bucket can stay private; try creating a bucket and uploading a file on my own                                                                                                                                                                                                                 | 22/09/2026 | 22/09/2026      | [S3 Presigned URLs](https://docs.aws.amazon.com/AmazonS3/latest/userguide/using-presigned-url.html)                                                                                                        |
| **Wednesday** | • Study Amazon DynamoDB: partition key and sort key (`PK`/`SK`), `Query` vs `Scan`, global secondary indexes, On-Demand capacity and the single-table design idea                                                                                                                                                                                                         | 23/09/2026 | 23/09/2026      | [DynamoDB Best Practices](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/best-practices.html)                                                                                            |
| **Thursday**  | • Study AWS Lambda and API Gateway HTTP API: handler, event, cold start, routes, CORS and logs in CloudWatch; try a small hello-world function on my own                                                                                                                                                                                                                  | 24/09/2026 | 24/09/2026      | [AWS Lambda Docs](https://docs.aws.amazon.com/lambda/), [Amazon API Gateway Docs](https://docs.aws.amazon.com/apigateway/)                                                                                 |
| **Friday**    | • Study AWS cost basics: Free Tier, promotional credits, Cost Explorer by service and Budgets alerts; compare how serverless and EC2 are charged                                                                                                                                                                                                                          | 25/09/2026 | 25/09/2026      | [AWS Cost Explorer](https://docs.aws.amazon.com/cost-management/latest/userguide/ce-what-is.html), [AWS Budgets](https://docs.aws.amazon.com/cost-management/latest/userguide/budgets-managing-costs.html) |
| **Saturday**  | • Attend [Event 1: Buildrathon – Kickoff: Code the Future with CMC Global](../../4-eventparticipated/4.1-event1/) (09:00 AM – 12:00 PM at the AWS Vietnam Office, Level 26, Bitexco Financial Tower). Theme of the day: don't just learn Cloud & AI for the knowledge, build real products with your teammates. The Tech Lead from CMC Global shared how their team in Australia and the developers in Vietnam talk and handle bugs through Slack; after the event the team chose **ReLoop**, a marketplace for used and broken electronics, as our capstone | 26/09/2026 | 26/09/2026      | [Event 1](../../4-eventparticipated/4.1-event1/)                                                                                              |

## **3. Key Achievements & Outcomes**

### **Theoretical Foundation**

- Understood why serverless fits a student team with limited credits: no idle servers, and the bill follows the number of requests.
- Learned that in DynamoDB the key design comes first: each screen should be answered by a `Query` on a known key, not by a `Scan`.
- Learned that a presigned URL gives one person temporary access to one object, so the bucket itself never has to be public.

### **Environment Setup & Configuration**

- Explored S3, DynamoDB, Lambda and API Gateway in the Console on my own and removed what I created afterwards.
- Know where to check the credit balance and the cost per service in the Billing console and Cost Explorer.

### **Practical Skills & Operations**

- Can describe how a browser request travels through API Gateway to Lambda and then to DynamoDB or S3.
- Joined the Buildrathon kickoff with my team and agreed on ReLoop as our project.
