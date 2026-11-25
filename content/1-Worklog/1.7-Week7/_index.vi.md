---
title: "Nhật ký công việc Tuần 7"
date: 2026-11-25
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

# **Nhật ký công việc Tuần 7 — Sự kiện cộng đồng Smart Plushies, Chọn Kimi K3 cho ReLoop & Nghiên cứu luồng sau khi đăng tin**

## **1. Mục tiêu tuần**

- Tham gia Sự kiện 5 (Smart Plushies for Children cùng Operation Smile Vietnam).
- Thử thêm Kimi K3 với nhiều ảnh thiết bị thật hơn.
- Chọn Kimi K3 làm model AI cho ReLoop và báo cho nhóm.
- Nghiên cứu tiếp luồng xử lý sau khi tin được đăng.

## **2. Lịch trình thực hiện**

| Ngày      | Mô tả công việc                                                                                                                                                                                                                                                                                                                           | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo                                                                                                                                                         |
| :-------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :----------- | :-------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Thứ 2** | • Tham gia [Sự kiện 5: Smart Plushies for Children – In Collaboration with Operation Smile Vietnam](../../4-eventparticipated/4.5-event5/) (13:30 – 15:30 tại phòng EC2, tầng 36, văn phòng AWS Việt Nam, Bitexco Financial Tower). Chúng tôi lắp ráp và lập trình thú bông tương tác cho các em nhỏ được Operation Smile hỗ trợ điều trị | 26/10/2026   | 26/10/2026      | [Sự kiện 5](../../4-eventparticipated/4.5-event5/)                                                                                                                         |
| **Thứ 3** | • Thử thêm Kimi K3 với nhiều ảnh thiết bị hơn: chụp nhiều góc, thiết bị hỏng, nhãn tiếng Việt                                                                                                                                                                                                                                             | 27/10/2026   | 27/10/2026      | [Tài liệu Amazon Bedrock](https://docs.aws.amazon.com/bedrock/)                                                                                                            |
| **Thứ 4** | • Chọn Kimi K3 và báo cho nhóm; nhóm chuyển AI của ReLoop sang Kimi K3 trên Bedrock (`global.moonshotai.kimi-k3`) ngày 28/10/2026                                                                                                                                                                                                          | 28/10/2026   | 28/10/2026      | [Tài liệu Amazon Bedrock](https://docs.aws.amazon.com/bedrock/), [Repository ReLoop](https://github.com/madlyham/ReLoop/blob/main/terraform/variables.tf) (`variables.tf`) |
| **Thứ 5** | • Dùng thử ReLoop trên AWS với ảnh thật sau khi chuyển: AI mô tả đúng khoảng 90% nội dung ảnh, người bán chỉ cần chỉnh lại một chút trước khi đăng                                                                                                                                                                                        | 29/10/2026   | 29/10/2026      | [Workshop 5.8](../../5-workshop/5.8-ai-processing/)                                                                                                                        |
| **Thứ 6** | • Nghiên cứu luồng xử lý sau khi tin được đăng: tin được ghép với các chi nhánh gần ra sao và đối tác thấy tin thế nào, để chuẩn bị cho phần ghép chi nhánh ở Tuần 8                                                                                                                                                                       | 30/10/2026   | 30/10/2026      | [Workshop 5.5](../../5-workshop/5.5-api-backend/)                                                                                                                          |

## **3. Kết quả đạt được**

### **Cơ sở lý thuyết**

- Học được rằng model mà cả nhóm dựa vào nên được thử trên nhiều loại ảnh thật trước khi dùng.

### **Cài đặt & Thiết lập môi trường**

- ReLoop dùng Kimi K3 trên Amazon Bedrock từ ngày 28/10/2026.

### **Kỹ năng thực hành & Vận hành**

- AI trên ReLoop mô tả đúng khoảng 90% nội dung ảnh thật, người bán chỉ cần chỉnh lại một chút.
- Cùng lắp ráp thú bông tương tác cho các em nhỏ tại sự kiện với Operation Smile Vietnam.
