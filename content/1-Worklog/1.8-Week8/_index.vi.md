---
title: "Nhật ký công việc Tuần 8"
date: 2026-11-25
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

# **Nhật ký công việc Tuần 8 — Ghép chi nhánh chạy nền bằng Geohash & Haversine, Giới hạn AI theo ngày & Lịch sử nhãn AI**

## **1. Mục tiêu tuần**

- Ghép mỗi tin đăng mới, ở chế độ nền, với mọi chi nhánh đã duyệt có vùng phục vụ (1–15 km) bao phủ tin đó.
- Xếp chi nhánh gần (trong 5 km) lên trước, và tự chạy lại phần ghép nếu bị lỗi.
- Giới hạn dùng AI 20 lượt mỗi người mỗi ngày.
- Lưu gợi ý của AI cạnh lựa chọn cuối của người bán để sau này đo độ chính xác.

## **2. Lịch trình thực hiện**

| Ngày      | Mô tả công việc                                                                                                                                                                                                                | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo                                                                                                                                                                                             |
| :-------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :----------- | :-------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Thứ 2** | • Viết `geo.ts`: geohash độ chính xác 4 (ô khoảng 39 × 19,5 km) cùng 8 ô xung quanh luôn phủ đủ bán kính tối đa 15 km; chi nhánh được đánh chỉ mục theo `GSI1` `GEO4#<geohash>`                                                | 02/11/2026   | 02/11/2026      | [Secondary index của DynamoDB](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/GSI.html), [Repository ReLoop](https://github.com/madlyham/ReLoop/tree/main/backend/api) (`src/shared/geo.ts`) |
| **Thứ 3** | • Viết bước ghép: truy vấn 9 ô, giữ chi nhánh có khoảng cách Haversine nằm trong `radiusKm` của nó, ghi một item `LISTING#<id>` / `MATCH#<branchId>` cho mỗi lần ghép, và hiển thị cho đối tác khoảng cách làm tròn lên 0,5 km | 03/11/2026   | 03/11/2026      | [Repository ReLoop](https://github.com/madlyham/ReLoop/tree/main/backend/api) (`src/modules/listings/listingService.ts`)                                                                                       |
| **Thứ 4** | • Cho phần ghép chạy nền sau khi đăng tin; nếu lỗi, mốc `LISTING_MATCH` (job quét tôi viết ở Tuần 6) chạy lại sau 5 phút mà không chặn việc đăng tin; sắp xếp kết quả để chi nhánh trong 5 km lên đầu                          | 04/11/2026   | 04/11/2026      | [Repository ReLoop](https://github.com/madlyham/ReLoop/tree/main/backend/api) (`src/modules/jobs/timers.ts`)                                                                                                   |
| **Thứ 5** | • Thêm giới hạn AI: bộ đếm `AIQUOTA#<ngày>` cho từng người (theo ngày giờ Việt Nam) có thử lại lạc quan, báo lỗi `AI_DAILY_LIMIT` khi đủ 20 lượt, và TTL 2 ngày để bộ đếm cũ tự xóa                                            | 05/11/2026   | 05/11/2026      | [TTL của DynamoDB](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/TTL.html), [Repository ReLoop](https://github.com/madlyham/ReLoop/tree/main/backend/api) (`src/modules/ai/aiService.ts`)   |
| **Thứ 6** | • Lưu gợi ý của AI cạnh giá trị cuối của người bán trong `AILABEL#<YYYY-MM>` khi tin được tạo từ một lượt phân tích, để đo độ chính xác AI theo từng tháng                                                                     | 06/11/2026   | 06/11/2026      | [Repository ReLoop](https://github.com/madlyham/ReLoop/tree/main/backend/api) (`src/store/keys.ts`)                                                                                                            |

## **3. Kết quả đạt được**

### **Cơ sở lý thuyết**

- Hiểu vì sao ô geohash phải lớn hơn bán kính tìm kiếm, để ô đó cùng 8 ô xung quanh luôn chứa mọi ứng viên.
- Hiểu phần ghép chạy lại được an toàn vì nó ghi lại đúng các item cũ, nên chỉ cần một mốc hẹn giờ để thử lại.

### **Cài đặt & Thiết lập môi trường**

- `geo.ts` (geohash, ô lân cận, Haversine) và các item `MATCH#` cho mỗi tin đăng.
- Bộ đếm `AIQUOTA#<ngày>` giới hạn 20 lượt mỗi ngày, TTL 2 ngày; lịch sử `AILABEL#<YYYY-MM>`.

### **Kỹ năng thực hành & Vận hành**

- Tin mới đến được mọi chi nhánh có vùng 1–15 km bao phủ, gần nhất lên trước, mà người bán không phải chờ.
- Người dùng đủ 20 lượt trong ngày nhận thông báo `AI_DAILY_LIMIT` rõ ràng.
