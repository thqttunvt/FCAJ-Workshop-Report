---
title: "Nhật ký công việc Tuần 5"
date: 2026-11-25
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

# **Nhật ký công việc Tuần 5 — Job AI tạo tin đăng chạy nền: aiService.ts, Lambda tự gọi bất đồng bộ & Kiểm tra đầu ra AI**

## **1. Mục tiêu tuần**

- Cho phân tích AI tạo tin đăng chạy nền để API trả lời ngay, không phải chờ model.
- Làm job an toàn khi chạy hai lần: lượt chạy trùng hoặc chạy trễ không bao giờ ghi đè kết quả đã xong.
- Kiểm tra mọi câu trả lời của AI ở server trước khi được lưu vào tin đăng.

## **2. Lịch trình thực hiện**

| Ngày      | Mô tả công việc                                                                                                                                                                                                         | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo                                                                                                                                                                                                                                         |
| :-------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :----------- | :-------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Thứ 2** | • Tìm hiểu các phần mà job của tôi dựa vào: kho ảnh (`ImageStore.read`, bước kiểm duyệt) và interface `Analyzer` gọi Amazon Bedrock                                                                                     | 12/10/2026   | 12/10/2026      | [Tài liệu Amazon Bedrock](https://docs.aws.amazon.com/bedrock/), [Workshop 5.8](../../5-workshop/5.8-ai-processing/)                                                                                                                                       |
| **Thứ 3** | • Thiết kế item phân tích `USER#<id>` / `AI#<analysisId>` với trạng thái `PENDING` → `COMPLETED` / `FAILED`: lệnh tạo trả `202` ngay và client hỏi lại kết quả                                                          | 13/10/2026   | 13/10/2026      | [Repository ReLoop](https://github.com/madlyham/ReLoop/tree/main/backend/api) (`src/store/keys.ts`)                                                                                                                                                        |
| **Thứ 4** | • Viết `create()` trong `aiService.ts`: chỉ nhận ảnh của chính người dùng, tối đa 3 ảnh mỗi lượt, ảnh phải qua kiểm duyệt, ghi item `PENDING`, rồi khởi động worker bằng Lambda tự gọi (`InvocationType=Event`)         | 14/10/2026   | 14/10/2026      | [Gọi Lambda bất đồng bộ](https://docs.aws.amazon.com/lambda/latest/dg/invocation-async.html), [Repository ReLoop](https://github.com/madlyham/ReLoop/tree/main/backend/api) (`src/modules/ai/aiService.ts`)                                                |
| **Thứ 5** | • Viết worker `run()`: chỉ xử lý item còn `PENDING` và lưu bằng lệnh ghi có điều kiện theo version, nên lượt chạy trùng không ghi đè được kết quả đã xong; gặp lỗi thì lưu `FAILED` kèm thông báo mời người bán tự nhập | 15/10/2026   | 15/10/2026      | [Condition expression của DynamoDB](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Expressions.ConditionExpressions.html), [Repository ReLoop](https://github.com/madlyham/ReLoop/tree/main/backend/api) (`src/modules/ai/aiService.ts`) |
| **Thứ 6** | • Thêm kiểm tra phía server cho từng trường AI trả về (tiêu đề, danh mục, hãng, model, tình trạng) trước khi lưu; thử toàn bộ job với bản giả lập trong bộ nhớ và với ảnh laptop, điện thoại thật                       | 16/10/2026   | 16/10/2026      | [Tool use trên Bedrock](https://docs.aws.amazon.com/bedrock/latest/userguide/tool-use.html), [Repository ReLoop](https://github.com/madlyham/ReLoop/tree/main/backend/api) (`src/shared/validate.ts`)                                                      |

## **3. Kết quả đạt được**

### **Cơ sở lý thuyết**

- Hiểu cách gọi Lambda bất đồng bộ cho phép tác vụ chậm chạy sau khi API đã trả lời.
- Hiểu khóa lạc quan bằng số version: lệnh ghi chỉ thành công nếu không ai sửa item kể từ lúc đọc.

### **Cài đặt & Thiết lập môi trường**

- `aiService.ts` có `create()`, `get()` và worker `run()`; item phân tích `USER#<id>` / `AI#<analysisId>`.
- Worker được khởi động bằng Lambda tự gọi trên AWS và chạy ngay sau response khi test local.

### **Kỹ năng thực hành & Vận hành**

- API trả `202` ngay, client lấy kết quả bằng cách hỏi lại.
- Câu trả lời AI không khớp schema tin đăng sẽ không bao giờ được lưu.
