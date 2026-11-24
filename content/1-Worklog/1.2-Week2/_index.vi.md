---
title: "Nhật ký công việc Tuần 2"
date: 2026-11-25
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

# **Nhật ký công việc Tuần 2 — Tự học các dịch vụ serverless (S3, DynamoDB, Lambda, API Gateway), Chi phí AWS cơ bản & Buildrathon Kickoff**

## **1. Mục tiêu tuần**

- Học bốn dịch vụ serverless mà backend dùng hằng ngày: S3, DynamoDB, Lambda và API Gateway.
- Hiểu AWS tính phí các dịch vụ này thế nào và theo dõi chi phí ở đâu (credit, Cost Explorer, Budgets).
- Tự thử các dịch vụ trên Console để gắn lý thuyết với những gì nhìn thấy.
- Tham gia Sự kiện 1 (Buildrathon Kickoff) và cùng nhóm chọn đề tài capstone.

## **2. Lịch trình thực hiện**

| Ngày      | Mô tả công việc                                                                                                                                                                                                                                                                                                                                                 | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo                                                                                                                                                                                         |
| :-------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :----------- | :-------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Thứ 2** | • Học Amazon S3: bucket và object, Block Public Access, mã hóa, versioning, lifecycle rule và CORS                                                                                                                                                                                                                                                              | 21/09/2026   | 21/09/2026      | [Tài liệu Amazon S3](https://docs.aws.amazon.com/s3/)                                                                                                                                                      |
| **Thứ 3** | • Tìm hiểu presigned URL: cách cấp quyền tạm thời cho một object để bucket vẫn riêng tư; tự thử tạo bucket và tải lên một file                                                                                                                                                                                                                                  | 22/09/2026   | 22/09/2026      | [Presigned URL của S3](https://docs.aws.amazon.com/AmazonS3/latest/userguide/using-presigned-url.html)                                                                                                     |
| **Thứ 4** | • Học Amazon DynamoDB: partition key và sort key (`PK`/`SK`), `Query` so với `Scan`, global secondary index, chế độ On-Demand và ý tưởng thiết kế một bảng                                                                                                                                                                                                      | 23/09/2026   | 23/09/2026      | [Thực hành tốt với DynamoDB](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/best-practices.html)                                                                                         |
| **Thứ 5** | • Học AWS Lambda và API Gateway HTTP API: handler, event, cold start, route, CORS và log trong CloudWatch; tự thử một hàm hello-world nhỏ                                                                                                                                                                                                                       | 24/09/2026   | 24/09/2026      | [Tài liệu AWS Lambda](https://docs.aws.amazon.com/lambda/), [Tài liệu Amazon API Gateway](https://docs.aws.amazon.com/apigateway/)                                                                         |
| **Thứ 6** | • Tìm hiểu chi phí AWS cơ bản: Free Tier, credit khuyến mãi, Cost Explorer theo dịch vụ và cảnh báo Budgets; so sánh cách tính phí của serverless với EC2                                                                                                                                                                                                       | 25/09/2026   | 25/09/2026      | [AWS Cost Explorer](https://docs.aws.amazon.com/cost-management/latest/userguide/ce-what-is.html), [AWS Budgets](https://docs.aws.amazon.com/cost-management/latest/userguide/budgets-managing-costs.html) |
| **Thứ 7** | • Tham gia [Sự kiện 1: Buildrathon – Kickoff: Code the Future with CMC Global](../../4-eventparticipated/4.1-event1/) (10:30 – 12:00 tại văn phòng AWS Việt Nam, tầng 26, Bitexco Financial Tower). Các phần chia sẻ xoay quanh Generative AI, quy trình agent và RAG; sau sự kiện nhóm chọn **ReLoop**, chợ mua bán đồ điện tử cũ và hỏng, làm đề tài capstone | 26/09/2026   | 26/09/2026      | [Sự kiện 1](../../4-eventparticipated/4.1-event1/), [Tài liệu Amazon Bedrock](https://docs.aws.amazon.com/bedrock/)                                                                                        |

## **3. Kết quả đạt được**

### **Cơ sở lý thuyết**

- Hiểu vì sao serverless hợp với nhóm sinh viên có ít credit: không có máy chủ chạy không, chi phí đi theo số request.
- Học được rằng với DynamoDB phải thiết kế khóa trước: mỗi màn hình nên được trả lời bằng `Query` trên khóa đã biết, không dùng `Scan`.
- Hiểu presigned URL chỉ cấp quyền tạm thời cho một người trên một object, nên bucket không bao giờ cần công khai.

### **Cài đặt & Thiết lập môi trường**

- Tự khám phá S3, DynamoDB, Lambda và API Gateway trên Console và xóa những gì đã tạo sau khi thử.
- Biết xem số dư credit và chi phí theo từng dịch vụ ở Billing console và Cost Explorer.

### **Kỹ năng thực hành & Vận hành**

- Mô tả được đường đi của một request từ trình duyệt qua API Gateway tới Lambda rồi tới DynamoDB hoặc S3.
- Tham gia buổi kickoff Buildrathon cùng nhóm và thống nhất chọn đề tài ReLoop.
