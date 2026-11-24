---
title: "Week 8 Worklog"
date: 2026-11-25
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

# **Week 8 Worklog — Background Branch Matching with Geohash & Haversine, AI Daily Cap & AI Label History**

## **1. Weekly Objectives**

- Match every new listing, in the background, to each approved branch whose service area (1–15 km) covers it.
- Put nearby branches (within 5 km) first, and retry matching automatically if it fails.
- Cap AI use at 20 analyses per user per day.
- Keep the AI suggestion next to the seller's final choice to measure AI accuracy later.

## **2. Weekly Execution Schedule**

| Day           | Task Description                                                                                                                                                                                                                        | Start Date | Completion Date | Reference Material                                                                                                                                                                                           |
| :------------ | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :--------- | :-------------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Monday**    | • Implement `geo.ts`: geohash precision 4 (a cell of about 39 × 19.5 km) plus its 8 neighbours always covers the 15 km maximum radius; branches are indexed under `GSI1` `GEO4#<geohash>`                                               | 02/11/2026 | 02/11/2026      | [DynamoDB Secondary Indexes](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/GSI.html), [ReLoop Repository](https://github.com/madlyham/ReLoop/tree/main/backend/api) (`src/shared/geo.ts`) |
| **Tuesday**   | • Implement the matching step: query the 9 cells, keep each branch whose Haversine distance is within its `radiusKm`, write one `LISTING#<id>` / `MATCH#<branchId>` item per match, and show partners the distance rounded up to 0.5 km | 03/11/2026 | 03/11/2026      | [ReLoop Repository](https://github.com/madlyham/ReLoop/tree/main/backend/api) (`src/modules/listings/listingService.ts`)                                                                                     |
| **Wednesday** | • Run matching in the background after a listing is posted; if it fails, a `LISTING_MATCH` timer (my sweep from Week 6) retries it after 5 minutes without blocking the post; sort results so branches within 5 km come first           | 04/11/2026 | 04/11/2026      | [ReLoop Repository](https://github.com/madlyham/ReLoop/tree/main/backend/api) (`src/modules/jobs/timers.ts`)                                                                                                 |
| **Thursday**  | • Add the AI cap: an `AIQUOTA#<day>` counter per user (Vietnam date) with an optimistic retry, error `AI_DAILY_LIMIT` at 20 analyses, and a TTL of 2 days so old counters clean themselves up                                           | 05/11/2026 | 05/11/2026      | [DynamoDB TTL](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/TTL.html), [ReLoop Repository](https://github.com/madlyham/ReLoop/tree/main/backend/api) (`src/modules/ai/aiService.ts`)     |
| **Friday**    | • Save the AI suggestion next to the seller's final values under `AILABEL#<YYYY-MM>` when a listing is created from an analysis, so AI accuracy can be measured month by month                                                          | 06/11/2026 | 06/11/2026      | [ReLoop Repository](https://github.com/madlyham/ReLoop/tree/main/backend/api) (`src/store/keys.ts`)                                                                                                          |

## **3. Key Achievements & Outcomes**

### **Theoretical Foundation**

- Learned why a geohash cell must be larger than the search radius, so the cell and its 8 neighbours always contain every candidate.
- Understood that matching is safe to re-run because it writes the same items again, which makes a retry timer enough.

### **Environment Setup & Configuration**

- `geo.ts` (geohash, neighbours, Haversine) and `MATCH#` items for each listing.
- `AIQUOTA#<day>` counters with a 20-per-day limit and a 2-day TTL; `AILABEL#<YYYY-MM>` history.

### **Practical Skills & Operations**

- A new listing reaches every branch whose 1–15 km area covers it, nearest first, without the seller waiting.
- Users who reach 20 analyses in a day get a clear `AI_DAILY_LIMIT` message.
