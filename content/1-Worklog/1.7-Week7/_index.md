---
title: "Week 7 Worklog"
date: 2026-11-25
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

# **Week 7 Worklog — Smart Plushies Community Event, Choosing Kimi K3 for ReLoop & Studying the Post-Listing Flow**

## **1. Weekly Objectives**

- Attend Event 5 (Smart Plushies for Children with Operation Smile Vietnam).
- Try Kimi K3 further with more real device photos.
- Choose Kimi K3 as the AI model for ReLoop and tell the team.
- Keep studying the processing flow after a listing is posted.

## **2. Weekly Execution Schedule**

| Day           | Task Description                                                                                                                                                                                                                                                                                                                                     | Start Date | Completion Date | Reference Material                                                                                                                                                        |
| :------------ | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :--------- | :-------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Monday**    | • Attend [Event 5: Smart Plushies for Children – In Collaboration with Operation Smile Vietnam](../../4-eventparticipated/4.5-event5/) (01:30 PM – 03:30 PM in the EC2 Room, Level 36, AWS Vietnam Office, Bitexco Financial Tower). We assembled and programmed interactive plushies for children treated by Operation Smile                       | 26/10/2026 | 26/10/2026      | [Event 5](../../4-eventparticipated/4.5-event5/)                                                                                                                          |
| **Tuesday**   | • Try Kimi K3 with more device photos: several angles, broken devices, Vietnamese labels                                                                                                                                                                                                                                                             | 27/10/2026 | 27/10/2026      | [Amazon Bedrock Docs](https://docs.aws.amazon.com/bedrock/)                                                                                                               |
| **Wednesday** | • Choose Kimi K3 and tell the team; the team switches ReLoop's AI to Kimi K3 on Bedrock (`global.moonshotai.kimi-k3`) on 28/10/2026                                                                                                                                                                                                                  | 28/10/2026 | 28/10/2026      | [Amazon Bedrock Docs](https://docs.aws.amazon.com/bedrock/), [ReLoop Repository](https://github.com/madlyham/ReLoop/blob/main/terraform/variables.tf) (`variables.tf`) |
| **Thursday**  | • Try the live ReLoop on AWS with real photos after the switch: the AI describes about 90% of each photo correctly, so the seller only adjusts a little before posting                                                                                                                                                                              | 29/10/2026 | 29/10/2026      | [Workshop 5.8](../../5-workshop/5.8-ai-processing/)                                                                                                                       |
| **Friday**    | • Study the processing flow after a listing is posted: how it gets matched to nearby branches and how partners see it, to prepare for the branch matching work in Week 8                                                                                                                                                                             | 30/10/2026 | 30/10/2026      | [Workshop 5.5](../../5-workshop/5.5-api-backend/)                                                                                                                         |

## **3. Key Achievements & Outcomes**

### **Theoretical Foundation**

- Learned that the model a whole team depends on should be tried on many kinds of real photos first.

### **Environment Setup & Configuration**

- ReLoop uses Kimi K3 on Amazon Bedrock from 28/10/2026.

### **Practical Skills & Operations**

- The AI on ReLoop describes about 90% of a real photo correctly, and sellers only fix a little.
- Helped assemble interactive plushies for children at the Operation Smile Vietnam event.
