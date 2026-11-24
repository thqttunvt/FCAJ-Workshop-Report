---
title: "Nhật ký công việc Tuần 1"
date: 2026-11-25
weight: 1
chapter: false
pre: " <b> 1.1. </b> "
---

# **Nhật ký công việc Tuần 1 — Nhập môn FCAJ & Tự học nền tảng AWS: Hạ tầng toàn cầu, IAM, AWS CLI, VPC & EC2**

## **1. Mục tiêu tuần**

- Tham gia khóa First Cloud AI Journey và hiểu cách hạ tầng toàn cầu của AWS được tổ chức (Region, Availability Zone).
- Học các khái niệm cốt lõi mà mọi dự án AWS đều dựa vào: mô hình trách nhiệm chung, IAM, VPC và EC2.
- Tự thử từng dịch vụ trên AWS Console để thấy các khái niệm đó trong thực tế.

## **2. Lịch trình thực hiện**

| Ngày      | Mô tả công việc                                                                                                                                                                         | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo                                                                                             |
| :-------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :----------- | :-------------- | :------------------------------------------------------------------------------------------------------------- |
| **Thứ 2** | • Tham gia buổi nhập môn FCAJ, làm quen các bạn trong khóa và đọc nội quy thực tập; tìm hiểu Region, Availability Zone, edge location và phạm vi của Free Tier                          | 14/09/2026   | 14/09/2026      | [Hạ tầng toàn cầu AWS](https://docs.aws.amazon.com/whitepapers/latest/aws-overview/global-infrastructure.html) |
| **Thứ 3** | • Học IAM: user, group, role, policy JSON (`Effect`, `Action`, `Resource`), MFA, đặc quyền tối thiểu và lý do không dùng tài khoản root cho công việc hằng ngày                         | 15/09/2026   | 15/09/2026      | [Thực hành bảo mật IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html)                  |
| **Thứ 4** | • Tìm hiểu cách AWS CLI và SDK xác thực (credential, profile, region mặc định); tự chạy thử vài lệnh chỉ đọc để xem kết quả trả về                                                      | 16/09/2026   | 16/09/2026      | [Hướng dẫn AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-welcome.html)                    |
| **Thứ 5** | • Học mạng VPC: dải CIDR, subnet public và private, Internet Gateway, NAT, route table, so sánh Security Group (stateful) với Network ACL (stateless); tự xem VPC mặc định trên Console | 17/09/2026   | 17/09/2026      | [Tài liệu Amazon VPC](https://docs.aws.amazon.com/vpc/)                                                        |
| **Thứ 6** | • Học EC2: loại instance, AMI, ổ EBS, key pair, Elastic IP và cách EC2 tính phí; tự thử tạo một máy nhỏ rồi xóa để không bị tính phí tiếp                                               | 18/09/2026   | 18/09/2026      | [Tài liệu Amazon EC2](https://docs.aws.amazon.com/ec2/)                                                        |

## **3. Kết quả đạt được**

### **Cơ sở lý thuyết**

- Hiểu mô hình trách nhiệm chung: AWS bảo vệ hạ tầng đám mây, còn khách hàng bảo vệ những gì mình đưa lên (danh tính, dữ liệu, luật mạng).
- Nắm nguyên tắc đặc quyền tối thiểu: mỗi danh tính chỉ có đúng quyền cần dùng, tài khoản root chỉ dành cho việc cấp tài khoản.
- Hiểu vì sao subnet private giúp cơ sở dữ liệu và máy chủ nội bộ không bị truy cập trực tiếp từ Internet.

### **Cài đặt & Thiết lập môi trường**

- Làm quen AWS Console và các trang chính của IAM, VPC, EC2 bằng cách tự khám phá.
- Xóa hết những gì đã tạo khi thử nghiệm, không để tài nguyên nào chạy sau khi kết thúc tuần.

### **Kỹ năng thực hành & Vận hành**

- Đọc được một policy IAM dạng JSON và biết nó cho phép hay chặn gì.
- Giải thích được đường đi của một request tới máy trong subnet public (Internet Gateway → route table → Security Group).
