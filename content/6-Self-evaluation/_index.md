---
title: "Self-evaluation"
date: 2026-11-25
weight: 6
chapter: false
pre: " <b> 6. </b> "
---

## Self-Evaluation Report

I did my internship at **Amazon Web Services Viet Nam Company Limited (Workforce Bootcamp - First Cloud AI Journey)** from **14/09/2026 to 04/12/2026**. As a Cybersecurity student at FPT University, this was the first time I applied what I had learned to a real system running on AWS.

I spent the first two weeks studying AWS fundamentals and serverless services on my own. After that I took the **Backend Engineer** role in the **ReLoop** team, a serverless marketplace on AWS for used and broken electronics. My part covered: the single-table DynamoDB key design (`keys.ts`), the backend business rules, scan-free background timers (`timers.ts`) driven by EventBridge, matching listings to nearby branches with geohash, and re-running the load test to confirm that `5xx` errors dropped from 26% to 0. On the AI side, I tested image-analysis models on my own and chose Kimi K3 for ReLoop. I also wrote the backend sections of Proposal Parts 1 and 2, and 3 blog posts on security on AWS.

In my work attitude, I tried to finish my assigned parts on time, write documentation from the real code so every number can be checked, and talk to the team when I got stuck.

I evaluate myself on the following criteria:

| No. | Criteria | Description | Good | Fair | Average | Specific Comment |
| :--- | :--- | :--- | :---: | :---: | :---: | :--- |
| 1 | **Professional knowledge & skills** | Understanding of the field, applying knowledge in practice, proficiency with tools, work quality | ☐ | ✅ | ☐ | Used DynamoDB, Lambda, API Gateway, EventBridge and S3 for the ReLoop backend; I still need to learn more about each service's limits and failure cases. |
| 2 | **Ability to learn** | Ability to absorb new knowledge and learn quickly | ✅ | ☐ | ☐ | Studied AWS fundamentals and serverless on my own in the first 2 weeks, and was writing backend code by Week 4 (`keys.ts`, 09/10/2026). |
| 3 | **Proactiveness** | Taking initiative, seeking out tasks without waiting for instructions | ✅ | ☐ | ☐ | Reviewed the specification to put the backend rules into the shared decision log, tested image-analysis AI models on my own to choose one for the team, and tried AWS Security Agent on my own outside the project. |
| 4 | **Sense of responsibility** | Completing tasks on time and ensuring quality | ☐ | ✅ | ☐ | Handed in my backend parts for Proposal Part 1 (08/10) and Part 2 (13/11) on time; I need to check failure cases more carefully before handing a feature over. |
| 5 | **Discipline** | Adhering to schedules, rules, and work processes | ☐ | ✅ | ☐ | Kept a weekly worklog and followed the team's shared rules; I need to clean up the resources I create right after trying them, instead of leaving it to the end. |
| 6 | **Progressive mindset** | Willingness to receive feedback and improve oneself | ✅ | ☐ | ☐ | Took on the mentors' questions about cost and security; studied the system's security layers (WAF, Cognito, IAM) on my own even though they were not my part. |
| 7 | **Communication** | Presenting ideas and reporting work clearly | ☐ | ✅ | ☐ | Wrote the backend parts of the proposal in plain words for readers outside the team; I need to share my progress with the other tracks more often. |
| 8 | **Teamwork** | Working effectively with colleagues and participating in teams | ☐ | ✅ | ☐ | Did my assigned part in team AWSS3nt1n4L and connected my backend work with my teammates' AI and infrastructure parts; I need to help the other tracks more actively. |
| 9 | **Professional conduct** | Respecting colleagues, partners, and the work environment | ✅ | ☐ | ☐ | Respectful with mentors, teammates and partners; attended all 6 events at the AWS Vietnam office. |
| 10 | **Problem-solving skills** | Identifying problems, proposing solutions, and showing creativity | ☐ | ✅ | ☐ | Solved real problems such as finding listings by location and running background timers without a `Scan`; but some issues, like `5xx` under load, only showed up in the load test. |
| 11 | **Contribution to project/team** | Work effectiveness, innovative ideas, recognition from the team | ☐ | ✅ | ☐ | Contributed the core of the ReLoop backend: data design, business rules, timers, branch matching and the load-test figures for the report; plus my AI tests that led to choosing Kimi K3. |
| 12 | **Overall** | General evaluation of the entire internship period | ☐ | ✅ | ☐ | Went from self-studying AWS basics to writing backend parts that run for real in 12 weeks; I still need to get better at foreseeing failures and service limits, and at communicating with the team. |

---

### Areas for Improvement

* **Foreseeing failures and service limits:** I found some problems only once things were running, such as the `5xx` errors under load that only showed up in the load test. I need to think about timeouts, concurrency, quotas and duplicate runs from the design stage.
* **Cleaning up resources:** The resources I created while trying things out and during development, outside Terraform, were left until Week 11 to review and remove. I should clean them up right after I finish trying them.
* **Communicating with the team:** I focused a lot on my own backend part. I need to share my progress and check in with the other tracks (frontend, AI, infrastructure) more often.

---

### Action Plan

1. **Write down limits and failure cases before coding:** For each background feature, note the timeout, concurrency, quota and what happens on a late or duplicate run before I start writing it.
2. **Clean up right after trying things:** Tag the resources I create and check Cost Explorer every week so nothing is left running.
3. **Weekly progress update for the team:** Each week, share briefly what the backend part has done, what is blocking it and who I need help from.
