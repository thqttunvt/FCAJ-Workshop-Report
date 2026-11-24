---
title: "Nhật ký công việc Tuần 10"
date: 2026-11-25
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---

# **Nhật ký công việc Tuần 10 — Chạy lại load test: 5xx từ 26% về 0, Kiểm tra giới hạn tốc độ & Ghi lại kết quả**

## **1. Mục tiêu tuần**

- Chạy lại load test của Tuần 8 khi concurrency của Lambda đã là 1.000, với cùng điều kiện.
- Xác nhận quá tải kết thúc bằng `429` rõ ràng chứ không phải `5xx`.
- Ghi lại kết quả trước và sau cho báo cáo cuối.

## **2. Lịch trình thực hiện**

| Ngày      | Mô tả công việc                                                                                                                       | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo                                                                                                                                                                                              |
| :-------- | :------------------------------------------------------------------------------------------------------------------------------------ | :----------- | :-------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Thứ 2** | • Chuẩn bị lần chạy lại với cùng 80 request song song và cùng các route như mốc Tuần 8 (26% `5xx` khi giới hạn concurrency là 10)     | 16/11/2026   | 16/11/2026      | [Concurrency của Lambda](https://docs.aws.amazon.com/lambda/latest/dg/lambda-concurrency.html)                                                                                                                  |
| **Thứ 3** | • Chạy load test với concurrency của Lambda là 1.000: tỉ lệ `5xx` giảm từ 26% về 0                                                    | 17/11/2026   | 17/11/2026      | [Concurrency của Lambda](https://docs.aws.amazon.com/lambda/latest/dg/lambda-concurrency.html)                                                                                                                  |
| **Thứ 4** | • Đọc chỉ số Lambda trên CloudWatch trong khung giờ test (`Duration`, `Errors`, `Throttles`); thời gian chạy trung bình khoảng 144 ms | 18/11/2026   | 18/11/2026      | [Chỉ số của Lambda](https://docs.aws.amazon.com/lambda/latest/dg/monitoring-metrics.html), [Workshop 5.10](../../5-workshop/5.10-monitoring/)                                                                   |
| **Thứ 5** | • Gửi một loạt request vượt giới hạn API (20 req/giây, burst 50) và xác nhận các request dư nhận `429` thay vì `5xx`                  | 19/11/2026   | 19/11/2026      | [Throttling cho HTTP API](https://docs.aws.amazon.com/apigateway/latest/developerguide/http-api-throttling.html), [Repository ReLoop](https://github.com/madlyham/ReLoop/blob/main/terraform/api.tf) (`api.tf`) |
| **Thứ 6** | • Ghi lại số liệu trước và sau (`5xx` 26% → 0, thời gian trung bình khoảng 144 ms, `429` khi vượt giới hạn) cho báo cáo cuối          | 20/11/2026   | 20/11/2026      | [Đề xuất](../../2-proposal/)                                                                                                                                                                                    |

## **3. Kết quả đạt được**

### **Cơ sở lý thuyết**

- Hiểu khác biệt giữa sập khi quá tải (`5xx`) và chủ động từ chối (`429`), và vì sao client có thể thử lại an toàn với trường hợp thứ hai.
- Hiểu một phép so sánh trước – sau công bằng phải giữ nguyên tải, route và dữ liệu.

### **Cài đặt & Thiết lập môi trường**

- Load test lặp lại được với 80 request song song, so với mốc Tuần 8.
- Theo dõi `Duration`, `Errors` và `Throttles` trên CloudWatch trong khung giờ test.

### **Kỹ năng thực hành & Vận hành**

- Đo được `5xx` giảm từ 26% về 0 sau khi tăng concurrency.
- Xác nhận request vượt giới hạn API nhận `429`, và ghi lại mọi số liệu cho báo cáo cuối.
