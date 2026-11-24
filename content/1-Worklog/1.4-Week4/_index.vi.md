---
title: "Nhật ký công việc Tuần 4"
date: 2026-11-25
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

# **Nhật ký công việc Tuần 4 — Access pattern DynamoDB, Thiết kế khóa một bảng, Đề xuất Phần 1 & keys.ts**

## **1. Mục tiêu tuần**

- Liệt kê truy vấn mà mỗi màn hình cần trước khi viết code truy vấn, không dùng scan.
- Thiết kế khóa cho mô hình một bảng (`PK`/`SK` và `GSI1`) để trả lời các truy vấn đó.
- Gửi bảng access pattern của tôi cho Đề xuất Phần 1 (nộp ngày 08/10/2026).
- Bắt đầu phát triển ngày 09/10/2026 bằng việc chuyển bảng đó thành `keys.ts`.

## **2. Lịch trình thực hiện**

| Ngày      | Mô tả công việc                                                                                                                                                                                                  | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo                                                                                                                                                      |
| :-------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :----------- | :-------------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Thứ 2** | • Liệt kê các màn hình của ReLoop (bảng tin chợ, tin của tôi, chi tiết tin, báo giá, giao dịch, chat, thông báo) và truy vấn chính xác mà mỗi màn hình cần                                                       | 05/10/2026   | 05/10/2026      | [Thực hành tốt với DynamoDB](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/best-practices.html)                                                      |
| **Thứ 3** | • Thiết kế khóa chính: `USER#<id>` / `PROFILE`, `LISTING#<id>` / `META`, `LISTING#<id>` / `QUOTE#<id>`, `TX#<id>` / `META`, và bảng tin chợ chia theo tháng `FEED#<YYYY-MM>` để mỗi màn hình chỉ cần một `Query` | 06/10/2026   | 06/10/2026      | [Thiết kế partition key](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/bp-partition-key-design.html), [Workshop 5.6](../../5-workshop/5.6-dynamodb/) |
| **Thứ 4** | • Thiết kế khóa `GSI1` cho các kiểu tra cứu còn lại: `<ENTITY>#STATUS#<trạng thái>` cho danh sách theo trạng thái, `OWNER#<id>` cho tin của một người bán, `GEO4#<geohash>` cho chi nhánh gần một vị trí         | 07/10/2026   | 07/10/2026      | [Secondary index của DynamoDB](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/GSI.html)                                                               |
| **Thứ 5** | • Gửi bảng access pattern của tôi cho **Đề xuất Phần 1** (nộp ngày 08/10/2026)                                                                                                                                   | 08/10/2026   | 08/10/2026      | [Đề xuất](../../2-proposal/)                                                                                                                                            |
| **Thứ 6** | • **Bắt đầu phát triển:** viết `src/store/keys.ts` từ bảng access pattern, làm nơi duy nhất định nghĩa mọi định dạng khóa để không module nào tự ghép chuỗi khóa                                                 | 09/10/2026   | 09/10/2026      | [Repository ReLoop](https://github.com/madlyham/ReLoop/tree/main/backend/api) (`src/store/keys.ts`)                                                                     |

## **3. Kết quả đạt được**

### **Cơ sở lý thuyết**

- Học cách thiết kế DynamoDB đi ngược từ truy vấn: màn hình trước, khóa sau, không bao giờ `Scan`.
- Hiểu việc chia partition đông dữ liệu theo tháng (`FEED#<YYYY-MM>`) giúp bảng tin chợ vẫn nhanh khi dữ liệu tăng.

### **Cài đặt & Thiết lập môi trường**

- Bảng access pattern cho mọi màn hình, dùng trong Đề xuất Phần 1 (08/10/2026).
- `keys.ts` có các khóa chính và khóa `GSI1` (`STATUS`, `OWNER`, `GEO4`) từ ngày 09/10/2026.

### **Kỹ năng thực hành & Vận hành**

- Gắn mỗi màn hình với đúng một `Query` trước khi viết code truy vấn.
- Chuyển bảng thiết kế thành code chạy được ngay ngày code đầu tiên.
