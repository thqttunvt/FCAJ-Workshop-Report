---
title: "Week 11 Worklog"
date: 2026-11-25
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---

# **Week 11 Worklog — Cleanup of My Leftover Resources, Module Re-test & Final Cost Check [Planned]**

> **Status:** Planned (current sprint: 23/11/2026 – 27/11/2026; last updated 25/11/2026).

## **1. Weekly Objectives**

- Find and remove the AWS resources I created while self-practising and during development that are not part of the Terraform stack.
- Re-test my modules (branch matching, listing-expiry sweep) on the live stack after the cleanup.
- Check the final spend against the $11.70/month estimate and the $189.80 credit balance (21/11/2026).

## **2. Weekly Execution Schedule**

| Day           | Planned Task Description                                                                                                                                  | Target Date | Status  | Reference Material                                                                                                                                                                              |
| :------------ | :-------------------------------------------------------------------------------------------------------------------------------------------------------- | :---------- | :------ | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Monday**    | • List the resources I created in `ap-southeast-1` while self-practising and during development, using AWS Resource Explorer and the CLI                  | 23/11/2026  | Planned | [AWS Resource Explorer](https://docs.aws.amazon.com/resource-explorer/latest/userguide/welcome.html)                                                                                            |
| **Tuesday**   | • Compare my list with the resources in `terraform/` and mark the ones Terraform does not manage, plus any access keys I no longer use                    | 24/11/2026  | Planned | [ReLoop Repository](https://github.com/madlyham/ReLoop/tree/main/terraform) (`terraform/`), [IAM Security Best Practices](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html) |
| **Wednesday** | • Delete my marked leftovers and unused access keys                                                                                                       | 25/11/2026  | Planned | [Workshop 5.12](../../5-workshop/5.12-cleanup-and-iac/)                                                                                                                                         |
| **Thursday**  | • Re-test my modules on the live stack: a new listing gets its `MATCH#` items, and the 15-minute sweep still closes due listings | 26/11/2026  | Planned | [Workshop 5.11](../../5-workshop/5.11-end-to-end-verification/)                                                                                                                                 |
| **Friday**    | • Final Cost Explorer check against $11.70/month ($10.00 WAF + about $1.70 usage) and the credit runway ($189.80 on 21/11/2026, valid until 28/02/2027)   | 27/11/2026  | Planned | [AWS Cost Explorer](https://docs.aws.amazon.com/cost-management/latest/userguide/ce-what-is.html)                                                                                               |

## **3. Expected Outcomes**

### **Theoretical Foundation**

- Understand how comparing a live inventory with infrastructure code finds forgotten resources before they show up on the bill.
- Confirm with real numbers that the fixed WAF fee is most of the bill, while the serverless core stays close to zero at our traffic.

### **Environment Setup & Configuration**

- No resource of mine left outside the Terraform stack; no unused access keys.
- My modules still working on the live stack after the cleanup.

### **Practical Skills & Operations**

- Carry out a safe cleanup followed by a passing re-test of my modules.
- Write a short cost and credit summary for the final report.
