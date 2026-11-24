---
title: "Nhật ký công việc Tuần 7"
date: 2026-11-25
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

# **Nhật ký công việc Tuần 7 — Sự kiện cộng đồng Smart Plushies, Cập nhật job AI cho Kimi K3 & Chặn job treo**

## **1. Mục tiêu tuần**

- Tham gia Sự kiện 5 (Smart Plushies for Children cùng Operation Smile Vietnam).
- Giữ job AI chạy đúng khi model đổi sang Kimi K3, và ghi lại model nào tạo ra từng kết quả.
- Cập nhật phần kiểm tra đầu ra AI cho các trường mới.
- Không để một lượt phân tích nằm `PENDING` mãi khi worker bị chết.

## **2. Lịch trình thực hiện**

| Ngày      | Mô tả công việc                                                                                                                                                                                                                                                                                                                           | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo                                                                                                                                                                                           |
| :-------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :----------- | :-------------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Thứ 2** | • Tham gia [Sự kiện 5: Smart Plushies for Children – In Collaboration with Operation Smile Vietnam](../../4-eventparticipated/4.5-event5/) (13:30 – 15:30 tại phòng EC2, tầng 36, văn phòng AWS Việt Nam, Bitexco Financial Tower). Chúng tôi lắp ráp và lập trình thú bông tương tác cho các em nhỏ được Operation Smile hỗ trợ điều trị | 26/10/2026   | 26/10/2026      | [Sự kiện 5](../../4-eventparticipated/4.5-event5/)                                                                                                                                                           |
| **Thứ 3** | • Lưu `modelId` vào mỗi item phân tích để sau này so sánh được kết quả giữa model cũ và model mới                                                                                                                                                                                                                                         | 27/10/2026   | 27/10/2026      | [Repository ReLoop](https://github.com/madlyham/ReLoop/tree/main/backend/api) (`src/modules/ai/aiService.ts`)                                                                                                |
| **Thứ 4** | • Kiểm tra lại toàn bộ job AI sau khi AI chuyển sang Kimi K3 trên Bedrock (`global.moonshotai.kimi-k3`) ngày 28/10/2026, dùng ảnh thiết bị thật                                                                                                                                                                                           | 28/10/2026   | 28/10/2026      | [Tài liệu Amazon Bedrock](https://docs.aws.amazon.com/bedrock/), [Repository ReLoop](https://github.com/madlyham/ReLoop/blob/main/terraform/variables.tf) (`variables.tf`)                                   |
| **Thứ 5** | • Cập nhật kiểm tra phía server cho hai trường đầu ra AI mới `observedTextAndLabels` và `identifiedComponents`, kiểm tra lại chữ tiếng Việt có dấu                                                                                                                                                                                        | 29/10/2026   | 29/10/2026      | [Tool use trên Bedrock](https://docs.aws.amazon.com/bedrock/latest/userguide/tool-use.html), [Repository ReLoop](https://github.com/madlyham/ReLoop/tree/main/backend/api) (`src/shared/validate.ts`)        |
| **Thứ 6** | • Thêm chốt chặn job treo trong `get()`: Lambda worker hết giờ sau 180 giây, nên lượt phân tích còn `PENDING` sau 4 phút sẽ được chốt `FAILED` để người bán tự nhập                                                                                                                                                                       | 30/10/2026   | 30/10/2026      | [Timeout của Lambda](https://docs.aws.amazon.com/lambda/latest/dg/configuration-timeout.html), [Repository ReLoop](https://github.com/madlyham/ReLoop/tree/main/backend/api) (`src/modules/ai/aiService.ts`) |

## **3. Kết quả đạt được**

### **Cơ sở lý thuyết**

- Hiểu worker bất đồng bộ không có dead-letter queue có thể biến mất âm thầm, nên đường đọc phải phát hiện được job không bao giờ xong.
- Học cách giữ kiểm tra schema chặt cho đầu ra AI để đổi model không làm hỏng dữ liệu đã lưu.

### **Cài đặt & Thiết lập môi trường**

- Item phân tích lưu `modelId`; kiểm tra đầu ra AI có thêm `observedTextAndLabels` và `identifiedComponents`.
- Giới hạn job treo 4 phút, lớn hơn timeout 180 giây của worker.

### **Kỹ năng thực hành & Vận hành**

- Job AI của tôi vẫn chạy đúng sau khi chuyển sang Kimi K3.
- Cùng lắp ráp thú bông tương tác cho các em nhỏ tại sự kiện với Operation Smile Vietnam.
