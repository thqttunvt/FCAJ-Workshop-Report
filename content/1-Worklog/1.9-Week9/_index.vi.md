---
title: "Nhật ký công việc Tuần 9"
date: 2026-11-25
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---

# **Nhật ký công việc Tuần 9 — Phần backend trong Đề xuất Phần 2, Rà soát chi phí Cost Explorer & Sự kiện Cloud Mastery**

## **1. Mục tiêu tuần**

- Viết phần backend của Đề xuất Phần 2 (mô hình dữ liệu và xử lý nền) dựa trên đúng những gì có trong code.
- Xem chi phí AWS thực tế trong Cost Explorer và đưa số liệu vào đề xuất.
- Hoàn thành phần của tôi trước hạn nộp ngày 13/11/2026.
- Tham gia Sự kiện 6 (Cloud Mastery) tại văn phòng AWS Việt Nam.

## **2. Lịch trình thực hiện**

| Ngày      | Mô tả công việc                                                                                                                                                                                                                                                                                             | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo                                                                                                                               |
| :-------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :----------- | :-------------- | :----------------------------------------------------------------------------------------------------------------------------------------------- |
| **Thứ 2** | • Thu thập thông tin cho phần của tôi trong Đề xuất Phần 2 từ code: thiết kế khóa và access pattern, các job nền (quét, ghép, job AI) và giới hạn của chúng                                                                                                                                                 | 09/11/2026   | 09/11/2026      | [Đề xuất](../../2-proposal/), [Repository ReLoop](https://github.com/madlyham/ReLoop/tree/main/backend/api) (`src/store/keys.ts`)                |
| **Thứ 3** | • Viết phần lưu trữ: một bảng DynamoDB không có scan, bảng tin chợ chia theo tháng, mọi khoản tiền lưu dạng số nguyên VND                                                                                                                                                                                   | 10/11/2026   | 10/11/2026      | [Đề xuất](../../2-proposal/), [Thực hành tốt với DynamoDB](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/best-practices.html) |
| **Thứ 4** | • Viết phần xử lý nền: job quét EventBridge 15 phút theo ngăn giờ, ghép chi nhánh trong 1–15 km (trong 5 km lên trước), và job AI (`202` + hỏi lại kết quả, 3 ảnh, 20 lượt mỗi người mỗi ngày)                                                                                                              | 11/11/2026   | 11/11/2026      | [Đề xuất](../../2-proposal/), [Workshop 5.9](../../5-workshop/5.9-eventbridge/)                                                                  |
| **Thứ 5** | • Xem chi phí từng dịch vụ trong Cost Explorer: stack tốn khoảng 11,70 USD/tháng, trong đó 10,00 USD là web ACL WAF trên CloudFront và khoảng 1,70 USD là phí sử dụng; đưa số liệu vào đề xuất                                                                                                              | 12/11/2026   | 12/11/2026      | [AWS Cost Explorer](https://docs.aws.amazon.com/cost-management/latest/userguide/ce-what-is.html)                                                |
| **Thứ 6** | • Đối chiếu phần của tôi với code lần cuối và nộp cho **Đề xuất Phần 2** (nộp ngày 13/11/2026)                                                                                                                                                                                                              | 13/11/2026   | 13/11/2026      | [Đề xuất](../../2-proposal/)                                                                                                                     |
| **Thứ 7** | • Tham gia [Sự kiện 6: Cloud Mastery – Cloud Sharing Session for Students](../../4-eventparticipated/4.6-event6/) (buổi sáng, văn phòng AWS Việt Nam, tầng 26, Bitexco Financial Tower). Phần hỏi đáp mở kéo dài về nghề và kỹ năng cloud, kết thúc bằng trò chơi Quiz.com trực tiếp với hơn 100 người chơi | 14/11/2026   | 14/11/2026      | [Sự kiện 6](../../4-eventparticipated/4.6-event6/)                                                                                               |

## **3. Kết quả đạt được**

### **Cơ sở lý thuyết**

- Học cách viết tài liệu kỹ thuật dựa trên code chứ không dựa trên trí nhớ, để mọi con số đều kiểm chứng được.
- Hiểu qua hóa đơn thật rằng một khoản phí cố định (web ACL của WAF) có thể đắt hơn nhiều so với tất cả dịch vụ tính theo request cộng lại.

### **Cài đặt & Thiết lập môi trường**

- Phần backend của Đề xuất Phần 2 (lưu trữ và xử lý nền) đã viết xong và nộp ngày 13/11/2026.
- Số liệu Cost Explorer thật (khoảng 11,70 USD/tháng) đã có trong đề xuất.

### **Kỹ năng thực hành & Vận hành**

- Giải thích thiết kế backend bằng lời dễ hiểu cho người ngoài nhóm.
- Đọc Cost Explorer theo từng dịch vụ và gắn mỗi khoản chi với phần hệ thống gây ra nó.
