---
title: "Nhật ký công việc Tuần 11"
date: 2026-11-25
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---

# **Nhật ký công việc Tuần 11 — Dọn tài nguyên thừa & Access key không dùng của tôi**

## **1. Mục tiêu tuần**

- Tìm và xóa các tài nguyên AWS tôi tạo khi tự thử và khi phát triển mà không thuộc stack Terraform.
- Xóa các access key tôi không còn dùng.

## **2. Lịch trình thực hiện**

| Ngày      | Mô tả công việc                                                                                                                      | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo                                                                                                                                                                        |
| :-------- | :----------------------------------------------------------------------------------------------------------------------------------- | :----------- | :-------------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Thứ 2** | • Liệt kê các tài nguyên tôi đã tạo ở `ap-southeast-1` khi tự thử và khi phát triển, bằng AWS Resource Explorer và CLI               | 23/11/2026   | 23/11/2026      | [AWS Resource Explorer](https://docs.aws.amazon.com/resource-explorer/latest/userguide/welcome.html)                                                                                      |
| **Thứ 3** | • So danh sách với các tài nguyên trong `terraform/`, đánh dấu những cái Terraform không quản lý và các access key tôi không còn dùng | 24/11/2026   | 24/11/2026      | [Repository ReLoop](https://github.com/madlyham/ReLoop/tree/main/terraform) (`terraform/`), [Thực hành bảo mật IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html) |
| **Thứ 4** | • Xóa các tài nguyên thừa đã đánh dấu và access key không dùng                                                                       | 25/11/2026   | 25/11/2026      | [Workshop 5.12](../../5-workshop/5.12-cleanup-and-iac/)                                                                                                                                   |

## **3. Kết quả đạt được**

### **Cơ sở lý thuyết**

- Hiểu cách đối chiếu danh sách tài nguyên thật với code hạ tầng giúp tìm ra tài nguyên bị quên trước khi chúng hiện lên hóa đơn.

### **Cài đặt & Thiết lập môi trường**

- Không còn tài nguyên nào của tôi nằm ngoài stack Terraform; không còn access key bỏ không.

### **Kỹ năng thực hành & Vận hành**

- Dọn dẹp an toàn: liệt kê tài nguyên của mình trước, đánh dấu những cái nằm ngoài Terraform, rồi chỉ xóa đúng những cái đó.
