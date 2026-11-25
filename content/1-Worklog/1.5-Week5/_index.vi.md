---
title: "Nhật ký công việc Tuần 5"
date: 2026-11-25
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

# **Nhật ký công việc Tuần 5 — Tìm AI phân tích ảnh & Nghiên cứu luồng xử lý backend của ReLoop**

## **1. Mục tiêu tuần**

- Tìm một model AI nhìn ảnh thiết bị rồi mô tả ra chữ tốt, để dùng cho ReLoop.
- Nghiên cứu các luồng xử lý chính của ReLoop (đăng tin, báo giá, giao dịch) trước khi làm tiếp phần backend.

## **2. Lịch trình thực hiện**

| Ngày      | Mô tả công việc                                                                                                                                               | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo                                                                                                                  |
| :-------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------ | :----------- | :-------------- | :---------------------------------------------------------------------------------------------------------------------------------- |
| **Thứ 2** | • Tìm hiểu trên Amazon Bedrock có những model AI nào đọc được ảnh và trả lời bằng chữ                                                                          | 12/10/2026   | 12/10/2026      | [Tài liệu Amazon Bedrock](https://docs.aws.amazon.com/bedrock/)                                                                     |
| **Thứ 3** | • Tự thử các model đó với ảnh thiết bị thật (laptop, điện thoại, đồ hỏng), xem model nào nhìn ảnh rồi mô tả ra chữ tốt                                         | 13/10/2026   | 13/10/2026      | [Tài liệu Amazon Bedrock](https://docs.aws.amazon.com/bedrock/)                                                                     |
| **Thứ 4** | • Nghiên cứu luồng đăng tin: người bán tải ảnh lên S3, ảnh được gửi đi phân tích, rồi tin được lưu vào DynamoDB                                               | 14/10/2026   | 14/10/2026      | [Workshop 5.7](../../5-workshop/5.7-s3-photos/), [Workshop 5.8](../../5-workshop/5.8-ai-processing/)                               |
| **Thứ 5** | • Nghiên cứu luồng báo giá và giao dịch: request đi qua API Gateway, Lambda rồi tới DynamoDB thế nào, và trạng thái đổi ra sao theo các quy tắc ở Tuần 3     | 15/10/2026   | 15/10/2026      | [Workshop 5.5](../../5-workshop/5.5-api-backend/)                                                                                  |
| **Thứ 6** | • Ghi chú lại các luồng xử lý chính (đăng tin, báo giá, giao dịch) để dùng khi làm phần backend ở các tuần sau                                               | 16/10/2026   | 16/10/2026      | [Workshop 5.5](../../5-workshop/5.5-api-backend/)                                                                                  |

## **3. Kết quả đạt được**

### **Cơ sở lý thuyết**

- Hiểu một request đi qua API Gateway, Lambda rồi tới DynamoDB hoặc S3 thế nào trong từng luồng của ReLoop.
- Học được rằng AI phải được thử trên ảnh thật của đúng loại sản phẩm, không chỉ trên ảnh mẫu.

### **Cài đặt & Thiết lập môi trường**

- Ghi chú các luồng xử lý chính của ReLoop: đăng tin, báo giá, giao dịch.

### **Kỹ năng thực hành & Vận hành**

- Biết những model nào trên Bedrock đọc được ảnh và trả lời bằng chữ.
- Nắm được các luồng xử lý để làm phần backend ở các tuần sau.
