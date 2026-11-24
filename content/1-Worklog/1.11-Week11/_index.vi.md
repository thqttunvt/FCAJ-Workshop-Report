---
title: "Nhật ký công việc Tuần 11"
date: 2026-11-25
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---

# **Nhật ký công việc Tuần 11 — Dọn tài nguyên thừa của tôi, Kiểm tra lại module & Kiểm tra chi phí cuối [Dự kiến]**

> **Trạng thái:** Dự kiến (tuần hiện tại: 23/11/2026 – 27/11/2026; cập nhật ngày 25/11/2026).

## **1. Mục tiêu tuần**

- Tìm và xóa các tài nguyên AWS tôi tạo khi tự thử và khi phát triển mà không thuộc stack Terraform.
- Kiểm tra lại các module của tôi (ghép chi nhánh, job AI, job đóng tin hết hạn) trên stack đang chạy sau khi dọn.
- Kiểm tra chi phí cuối so với ước tính 11,70 USD/tháng và số dư credit 189,80 USD (21/11/2026).

## **2. Lịch trình thực hiện**

| Ngày      | Mô tả công việc dự kiến                                                                                                                                                                        | Ngày dự kiến | Trạng thái | Tài liệu tham khảo                                                                                                                                                                        |
| :-------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :----------- | :--------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Thứ 2** | • Liệt kê các tài nguyên tôi đã tạo ở `ap-southeast-1` khi tự thử và khi phát triển, bằng AWS Resource Explorer và CLI                                                                         | 23/11/2026   | Dự kiến    | [AWS Resource Explorer](https://docs.aws.amazon.com/resource-explorer/latest/userguide/welcome.html)                                                                                      |
| **Thứ 3** | • So danh sách với các tài nguyên trong `terraform/`, đánh dấu những cái Terraform không quản lý và các access key tôi không còn dùng                                                          | 24/11/2026   | Dự kiến    | [Repository ReLoop](https://github.com/madlyham/ReLoop/tree/main/terraform) (`terraform/`), [Thực hành bảo mật IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html) |
| **Thứ 4** | • Xóa các tài nguyên thừa đã đánh dấu và access key không dùng                                                                                                                                 | 25/11/2026   | Dự kiến    | [Workshop 5.12](../../5-workshop/5.12-cleanup-and-iac/)                                                                                                                                   |
| **Thứ 5** | • Kiểm tra lại module của tôi trên stack đang chạy: tin mới có item `MATCH#`, lượt phân tích AI chạy xong, job quét 15 phút vẫn đóng tin đến hạn                                               | 26/11/2026   | Dự kiến    | [Workshop 5.11](../../5-workshop/5.11-end-to-end-verification/)                                                                                                                           |
| **Thứ 6** | • Kiểm tra Cost Explorer lần cuối so với 11,70 USD/tháng (10,00 USD WAF + khoảng 1,70 USD phí sử dụng) và thời gian credit còn dùng được (189,80 USD ngày 21/11/2026, hiệu lực đến 28/02/2027) | 27/11/2026   | Dự kiến    | [AWS Cost Explorer](https://docs.aws.amazon.com/cost-management/latest/userguide/ce-what-is.html)                                                                                         |

## **3. Kết quả dự kiến**

### **Cơ sở lý thuyết**

- Hiểu cách đối chiếu danh sách tài nguyên thật với code hạ tầng giúp tìm ra tài nguyên bị quên trước khi chúng hiện lên hóa đơn.
- Xác nhận bằng số liệu thật rằng phí cố định của WAF chiếm phần lớn hóa đơn, còn phần lõi serverless gần như bằng 0 ở lưu lượng hiện tại.

### **Cài đặt & Thiết lập môi trường**

- Không còn tài nguyên nào của tôi nằm ngoài stack Terraform; không còn access key bỏ không.
- Các module của tôi vẫn chạy đúng trên stack sau khi dọn.

### **Kỹ năng thực hành & Vận hành**

- Dọn dẹp an toàn, sau đó kiểm tra lại module của tôi đều đạt.
- Viết bản tóm tắt ngắn về chi phí và credit cho báo cáo cuối.
