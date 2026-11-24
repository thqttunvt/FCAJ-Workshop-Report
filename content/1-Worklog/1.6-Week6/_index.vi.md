---
title: "Nhật ký công việc Tuần 6"
date: 2026-11-25
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

# **Nhật ký công việc Tuần 6 — Hẹn giờ chạy nền không cần scan (timers.ts), Job quét EventBridge 15 phút & Cloud & AI Infrastructure Meetup**

## **1. Mục tiêu tuần**

- Cho backend chạy việc đúng thời điểm (tin hết hạn, nhắc giao dịch) mà không phải quét cả bảng.
- Nối job quét với Amazon EventBridge để chạy mỗi 15 phút trên AWS.
- Bảo đảm mọi mốc hẹn giờ chạy trễ hay chạy hai lần đều an toàn.
- Tham gia Sự kiện 4 (Cloud & AI Infrastructure Meetup).

## **2. Lịch trình thực hiện**

| Ngày      | Mô tả công việc                                                                                                                                                                                                                                                                                                       | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo                                                                                                                                                                                                         |
| :-------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :----------- | :-------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Thứ 2** | • Thiết kế item hẹn giờ gom theo giờ: `TIMER#<YYYY-MM-DDTHH>` / `<loại>#<id>`, để job chỉ đọc vài "ngăn" giờ bằng `Query` thay vì `Scan`                                                                                                                                                                              | 19/10/2026   | 19/10/2026      | [Thực hành tốt với DynamoDB](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/best-practices.html), [Repository ReLoop](https://github.com/madlyham/ReLoop/tree/main/backend/api) (`src/store/keys.ts`)    |
| **Thứ 3** | • Viết `timerOp()` và `TimerSweeper` trong `timers.ts`: đọc các ngăn từ 72 giờ trước tới hiện tại, chạy mốc đã đến hạn, xóa mốc khi thành công và giữ lại mốc lỗi để lần quét sau chạy lại                                                                                                                            | 20/10/2026   | 20/10/2026      | [Repository ReLoop](https://github.com/madlyham/ReLoop/tree/main/backend/api) (`src/modules/jobs/timers.ts`)                                                                                                               |
| **Thứ 4** | • Thêm các loại mốc `LISTING_EXPIRE` (tin đóng sau 7 ngày), `LISTING_MATCH`, `TX_REMIND`, `TX_AUTO_COMPLETE` và `TX_CANCEL`, cùng chỗ gắn việc định kỳ như lập phí hằng tháng                                                                                                                                         | 21/10/2026   | 21/10/2026      | [Repository ReLoop](https://github.com/madlyham/ReLoop/tree/main/backend/api) (`src/modules/jobs/timers.ts`)                                                                                                               |
| **Thứ 5** | • Nối job quét với rule EventBridge `rate(15 minutes)` gọi Lambda API, và ghi log `timer_sweep` / `timer_failed` lên CloudWatch                                                                                                                                                                                       | 22/10/2026   | 22/10/2026      | [Rule định kỳ của EventBridge](https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-create-rule-schedule.html), [Repository ReLoop](https://github.com/madlyham/ReLoop/blob/main/terraform/events.tf) (`events.tf`) |
| **Thứ 6** | • Thử chạy trễ và chạy trùng bằng đồng hồ giả: mỗi handler đọc lại trạng thái hiện tại trước, nên mốc của tin đã đóng sẽ không làm gì                                                                                                                                                                                 | 23/10/2026   | 23/10/2026      | [Workshop 5.9](../../5-workshop/5.9-eventbridge/)                                                                                                                                                                          |
| **Thứ 7** | • Tham gia [Sự kiện 4: Cloud & AI Infrastructure Meetup](../../4-eventparticipated/4.4-event4/) (10:30 – 12:00 tại văn phòng AWS Việt Nam, tầng 26, Bitexco Financial Tower). Diễn giả từ OMZ, Viettel AI và Viettel Networks chia sẻ về lưu trữ object cho dữ liệu AI, phục vụ suy luận trên GPU và định tuyến agent | 24/10/2026   | 24/10/2026      | [Sự kiện 4](../../4-eventparticipated/4.4-event4/), [Tài liệu Amazon S3](https://docs.aws.amazon.com/s3/)                                                                                                                  |

## **3. Kết quả đạt được**

### **Cơ sở lý thuyết**

- Hiểu cách khóa gom theo giờ biến việc "tìm mọi thứ đến hạn" thành vài lệnh `Query` rẻ.
- Hiểu vì sao job nền phải idempotent: bộ hẹn giờ có thể chạy trễ, và lần thử lại có thể làm cùng một việc hai lần.

### **Cài đặt & Thiết lập môi trường**

- `timers.ts` với 5 loại mốc, quét lùi 72 giờ và chạy lại khi lỗi.
- Rule EventBridge `rate(15 minutes)` gọi Lambda API.

### **Kỹ năng thực hành & Vận hành**

- Tin đăng tự đóng sau 7 ngày mà không cần quét bảng.
- Đã thử quét trễ và quét trùng; cả hai đều không thay đổi dữ liệu đã chốt.
