---
title: "Week 5 Worklog"
date: 2026-11-25
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

# **Week 5 Worklog — Finding an Image-Analysis AI & Studying ReLoop's Backend Processing Flows**

## **1. Weekly Objectives**

- Find an AI model that can look at a device photo and describe it well in text, to use in ReLoop.
- Study ReLoop's main processing flows (posting a listing, quotes, transactions) before continuing with the backend.

## **2. Weekly Execution Schedule**

| Day           | Task Description                                                                                                                                              | Start Date | Completion Date | Reference Material                                                                                    |
| :------------ | :------------------------------------------------------------------------------------------------------------------------------------------------------------ | :--------- | :-------------- | :---------------------------------------------------------------------------------------------------- |
| **Monday**    | • Find out which AI models on Amazon Bedrock can read an image and answer in text                                                                             | 12/10/2026 | 12/10/2026      | [Amazon Bedrock Docs](https://docs.aws.amazon.com/bedrock/)                                           |
| **Tuesday**   | • Try those models myself with real device photos (laptops, phones, broken devices) and see which one describes the photo well in text                        | 13/10/2026 | 13/10/2026      | [Amazon Bedrock Docs](https://docs.aws.amazon.com/bedrock/)                                           |
| **Wednesday** | • Study the listing flow: the seller uploads photos to S3, the photos are sent for analysis, and the listing is saved in DynamoDB                            | 14/10/2026 | 14/10/2026      | [Workshop 5.7](../../5-workshop/5.7-s3-photos/), [Workshop 5.8](../../5-workshop/5.8-ai-processing/) |
| **Thursday**  | • Study the quote and transaction flows: how a request goes through API Gateway and Lambda to DynamoDB, and how states change under the Week 3 rules         | 15/10/2026 | 15/10/2026      | [Workshop 5.5](../../5-workshop/5.5-api-backend/)                                                    |
| **Friday**    | • Write notes on the main processing flows (listing, quote, transaction) to use when building the backend in the following weeks                             | 16/10/2026 | 16/10/2026      | [Workshop 5.5](../../5-workshop/5.5-api-backend/)                                                    |

## **3. Key Achievements & Outcomes**

### **Theoretical Foundation**

- Understood how a request moves through API Gateway and Lambda to DynamoDB or S3 in each ReLoop flow.
- Learned that AI has to be tried on real photos of the right kind of product, not only on sample pictures.

### **Environment Setup & Configuration**

- Notes on ReLoop's main processing flows: listing, quote and transaction.

### **Practical Skills & Operations**

- Know which models on Bedrock can read an image and answer in text.
- Understand the processing flows well enough to build the backend in the following weeks.
