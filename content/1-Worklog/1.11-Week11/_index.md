---
title: "Week 11 Worklog"
date: 2026-11-25
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---

# **Week 11 Worklog — Cleanup of My Leftover Resources & Unused Access Keys**

## **1. Weekly Objectives**

- Find and remove the AWS resources I created while self-practising and during development that are not part of the Terraform stack.
- Remove the access keys I no longer use.

## **2. Weekly Execution Schedule**

| Day           | Task Description                                                                                                                         | Start Date | Completion Date | Reference Material                                                                                                                                                                              |
| :------------ | :--------------------------------------------------------------------------------------------------------------------------------------- | :--------- | :-------------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Monday**    | • List the resources I created in `ap-southeast-1` while self-practising and during development, using AWS Resource Explorer and the CLI | 23/11/2026 | 23/11/2026      | [AWS Resource Explorer](https://docs.aws.amazon.com/resource-explorer/latest/userguide/welcome.html)                                                                                            |
| **Tuesday**   | • Compare my list with the resources in `terraform/` and mark the ones Terraform does not manage, plus any access keys I no longer use   | 24/11/2026 | 24/11/2026      | [ReLoop Repository](https://github.com/madlyham/ReLoop/tree/main/terraform) (`terraform/`), [IAM Security Best Practices](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html) |
| **Wednesday** | • Delete my marked leftovers and unused access keys                                                                                      | 25/11/2026 | 25/11/2026      | [Workshop 5.12](../../5-workshop/5.12-cleanup-and-iac/)                                                                                                                                         |

## **3. Key Achievements & Outcomes**

### **Theoretical Foundation**

- Understood how comparing a live inventory with infrastructure code finds forgotten resources before they show up on the bill.

### **Environment Setup & Configuration**

- No resource of mine left outside the Terraform stack; no unused access keys.

### **Practical Skills & Operations**

- Carried out a safe cleanup: listed my resources first, marked the ones outside Terraform, then deleted only those.
