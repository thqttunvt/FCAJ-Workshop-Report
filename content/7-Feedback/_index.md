---
title: "Sharing and Feedback"
date: 2026-11-25
weight: 7
chapter: false
pre: " <b> 7. </b> "
---

Below are my personal reflections and constructive feedback after taking part in the **First Cloud AI Journey (FCAJ)** program, shared in the hope of contributing to the experience of future cohorts.

### Overall Evaluation

**1. Working Environment**

Open and hands-on. Most of the learning happened in our team channel and at the AWS Vietnam office (Level 26, Bitexco), where the events let me meet the mentors, AWS engineers and other interns in person. Every question, at any level, was listened to, discussed and given feedback until we reached a result, and that helped me see which knowledge I still needed to build up.

**2. Support from Mentor / Team Admin**

The mentors pointed us in the right direction instead of handing over answers: they gave feedback on our architecture and proposal, and asked many hard questions about cost and security. The admin team kept events, deadlines and report templates clear. A mid-term session to report progress and architecture could make this even more effective.

**3. Relevance of Work to Academic Major**

Very relevant. I study cybersecurity, and in ReLoop I was given the backend role. I had already studied some backend before, so this time, besides learning how the data flows are processed, I could also apply my knowledge to a real system. Alongside the backend, I studied the security layers the team applied to the system: AWS WAF, Cognito sign-in, IAM roles, and how WAF is used to check sign-ins and spam. Outside the project, I also got some hands-on pentest experience by trying the AWS Security Agent service on my own.

**4. Learning & Skill Development Opportunities**

I feel I have grown through researching and learning in the ReLoop project: WAF, CloudFront, Cognito, Lambda, API Gateway, DynamoDB, Rekognition, Bedrock, Terraform and GitHub Actions on a live project, along with comparing DynamoDB against RDS to choose the right database. My soft skills improved too: writing the proposal, keeping a weekly worklog, and writing 3 blog posts about deployment and operation steps that support learning and research, and about how to organise code changes so they do not conflict. Outside the project, the internship at AWS also let me build, on my own, a small setup that uses EC2 as a gateway, to test multi-region network latency, keep traffic routing stable over international connections and manage outbound IP addresses in one place.

**5. Company Culture & Team Spirit**

Our team AWSS3nt1n4L split work by strength (frontend, backend, AI, infrastructure) and always helped each other whenever someone was stuck. At the events, the talks from the mentors and speakers were all valuable and worth learning from, and the FCAJ community was just as great: friendly and eager to learn, so the Q&A sessions usually ran very long.

**6. Internship Policies / Benefits**

The main benefits were AWS credits to build on real services, free access to AWS events and workshops, and flexible remote work between office sessions. If the account limits (quotas) had been explained at the start, the internship would have been clearer.

---

### Additional Questions

**What did you find most satisfying during your internship?**

Taking ReLoop from an idea to a live system on AWS services in 12 weeks. The most memorable moment was testing the system's WAF protection. At first I sent only a few requests to see how the system reacted to spam, then I sent a large number of requests in a row, and those requests were blocked exactly as WAF had warned. After the fixes, the system no longer had bad IPs (IPs showing signs of attacks or spam) or spam requests getting through. Next was a trial run of the product: I uploaded a real photo, clicked AI analysis, and the AI described about 90% of the photo correctly, so the seller only needed to adjust a little before posting. The events at the AWS office, especially the long and lively Q&A at Cloud Mastery, were also very memorable.

**What do you think the company should improve for future interns?**

A little more Bedrock quota for Claude Sonnet would make the work more effective.

**If recommending to a friend, would you suggest they intern here? Why or why not?**

Yes, for anyone willing to learn on their own. Hands-on practice with AWS lets you go through a clear project process with architecture diagrams, with guidance and support from the team, and you learn even more through the events.

---

### Suggestions & Expectations

**Do you have any suggestions to improve the internship experience?**

- A mid-term demo where teams present their progress and get mentor feedback before the final presentation.
- A shared "lessons learned" page on common errors with AWS services (IAM permissions and billing).

**Would you like to continue this program in the future?**

Yes. I want to keep improving ReLoop and stay active in the FCAJ community.

**Any other comments (free sharing):**

Thank you to the mentors, the FCAJ admin team and my teammates in AWSS3nt1n4L.
