---
title: "Week 1 Worklog"
date: 2026-11-25
weight: 1
chapter: false
pre: " <b> 1.1. </b> "
---

# **Week 1 Worklog — FCAJ Onboarding & Self-Study of AWS Fundamentals: Global Infrastructure, IAM, AWS CLI, VPC & EC2**

## **1. Weekly Objectives**

- Join the First Cloud AI Journey cohort and understand how the AWS global infrastructure (Regions, Availability Zones) is organised.
- Study the core ideas every AWS project depends on: the shared responsibility model, IAM, VPC and EC2.
- Try each service on my own in the AWS Console to see how the concepts look in practice.

## **2. Weekly Execution Schedule**

| Day           | Task Description                                                                                                                                                                                         | Start Date | Completion Date | Reference Material                                                                                                  |
| :------------ | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :--------- | :-------------- | :------------------------------------------------------------------------------------------------------------------ |
| **Monday**    | • Attend FCAJ onboarding, meet the cohort and read the internship rules; study Regions, Availability Zones, edge locations and what the Free Tier covers                                                 | 14/09/2026 | 14/09/2026      | [AWS Global Infrastructure](https://docs.aws.amazon.com/whitepapers/latest/aws-overview/global-infrastructure.html) |
| **Tuesday**   | • Study IAM: users, groups, roles, JSON policies (`Effect`, `Action`, `Resource`), MFA, least privilege, and why the root user should not be used for daily work                                         | 15/09/2026 | 15/09/2026      | [IAM Security Best Practices](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html)                 |
| **Wednesday** | • Study how the AWS CLI and SDKs authenticate (credentials, profiles, default region); try a few read-only commands on my own to see the responses                                                       | 16/09/2026 | 16/09/2026      | [AWS CLI User Guide](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-welcome.html)                        |
| **Thursday**  | • Study VPC networking: CIDR blocks, public and private subnets, Internet Gateway, NAT, route tables, and Security Groups (stateful) vs Network ACLs (stateless); explore the default VPC in the Console | 17/09/2026 | 17/09/2026      | [Amazon VPC Docs](https://docs.aws.amazon.com/vpc/)                                                                 |
| **Friday**    | • Study EC2: instance types, AMIs, EBS volumes, key pairs, Elastic IPs and how EC2 is billed; try launching a small instance on my own, then terminate it so it does not keep charging                   | 18/09/2026 | 18/09/2026      | [Amazon EC2 Docs](https://docs.aws.amazon.com/ec2/)                                                                 |

## **3. Key Achievements & Outcomes**

### **Theoretical Foundation**

- Understood the shared responsibility model: AWS secures the cloud, and the customer secures what they put in it (identities, data, network rules).
- Learned least privilege: an identity gets only the actions it needs, and the root user is kept for account-level tasks only.
- Understood why private subnets keep databases and internal servers out of reach from the Internet.

### **Environment Setup & Configuration**

- Got familiar with the AWS Console and the main pages of IAM, VPC and EC2 by exploring them myself.
- Removed everything I created while trying things out, so no resource kept running after the week.

### **Practical Skills & Operations**

- Can read an IAM JSON policy and say what it allows or denies.
- Can explain how a request reaches an instance in a public subnet (Internet Gateway → route table → Security Group).
