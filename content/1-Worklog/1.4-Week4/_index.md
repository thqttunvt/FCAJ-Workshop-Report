---
title: "Week 4 Worklog"
date: 2026-11-25
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

# **Week 4 Worklog — DynamoDB Access Patterns, Single-Table Key Design, Proposal Part 1 & keys.ts**

## **1. Weekly Objectives**

- List the query every screen needs before writing any query code, with no table scans.
- Design the single-table keys (`PK`/`SK` and `GSI1`) that answer those queries.
- Hand my access-pattern sheet over for Proposal Part 1 (submitted 08/10/2026).
- Start development on 09/10/2026 by turning the sheet into `keys.ts`.

## **2. Weekly Execution Schedule**

| Day           | Task Description                                                                                                                                                                                                | Start Date | Completion Date | Reference Material                                                                                                                                                             |
| :------------ | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :--------- | :-------------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Monday**    | • List the screens of ReLoop (market feed, my listings, listing detail, quotes, transactions, chat, notifications) and the exact query each one needs                                                           | 05/10/2026 | 05/10/2026      | [DynamoDB Best Practices](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/best-practices.html)                                                                |
| **Tuesday**   | • Design the base keys: `USER#<id>` / `PROFILE`, `LISTING#<id>` / `META`, `LISTING#<id>` / `QUOTE#<id>`, `TX#<id>` / `META`, and a market feed split by month `FEED#<YYYY-MM>` so one `Query` serves one screen | 06/10/2026 | 06/10/2026      | [DynamoDB Partition Key Design](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/bp-partition-key-design.html), [Workshop 5.6](../../5-workshop/5.6-dynamodb/) |
| **Wednesday** | • Design the `GSI1` keys for the other lookups: `<ENTITY>#STATUS#<status>` for status lists, `OWNER#<id>` for a seller's listings, `GEO4#<geohash>` for branches near a point                                   | 07/10/2026 | 07/10/2026      | [DynamoDB Secondary Indexes](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/GSI.html)                                                                        |
| **Thursday**  | • Hand my access-pattern sheet over for **Proposal Part 1** (submitted 08/10/2026)                                                                                                                              | 08/10/2026 | 08/10/2026      | [Proposal](../../2-proposal/)                                                                                                                                                  |
| **Friday**    | • **Development starts:** write `src/store/keys.ts` from the sheet as the single place for every key format, so no module builds a key string by hand                                                           | 09/10/2026 | 09/10/2026      | [ReLoop Repository](https://github.com/madlyham/ReLoop/tree/main/backend/api) (`src/store/keys.ts`)                                                                            |

## **3. Key Achievements & Outcomes**

### **Theoretical Foundation**

- Learned to design DynamoDB from the queries backwards: first the screens, then the keys, never a `Scan`.
- Understood how splitting a busy partition by month (`FEED#<YYYY-MM>`) keeps the market feed fast as it grows.

### **Environment Setup & Configuration**

- Access-pattern sheet covering every screen, used in Proposal Part 1 (08/10/2026).
- `keys.ts` with the base keys and the `GSI1` keys (`STATUS`, `OWNER`, `GEO4`) from 09/10/2026.

### **Practical Skills & Operations**

- Mapped every screen to exactly one `Query` before writing query code.
- Turned the sheet into working code on the first day of development.
