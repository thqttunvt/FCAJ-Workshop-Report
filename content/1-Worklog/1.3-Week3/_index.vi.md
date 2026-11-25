---
title: "Nhật ký công việc Tuần 3"
date: 2026-11-25
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

# **Nhật ký công việc Tuần 3 — Rà soát đặc tả ReLoop, Quy tắc nghiệp vụ backend, AI Day Watch Party & Fireside Chat với Dr. Werner Vogels**

## **1. Mục tiêu tuần**

- Đọc đặc tả ReLoop v1.0 dưới góc nhìn backend và ghi lại mọi câu hỏi ảnh hưởng tới dữ liệu hoặc API.
- Viết các quy tắc backend (trạng thái, ai được đổi trạng thái, cách lưu tiền) vào sổ quyết định chung QĐ-01 → QĐ-45.
- Nhận vai trò **Backend Engineer** trong nhóm.
- Tham gia Sự kiện 2 (AWS Cloud and AI Day Hanoi – Watch Party) và Sự kiện 3 (Fireside Chat với Dr. Werner Vogels).

## **2. Lịch trình thực hiện**

| Ngày      | Mô tả công việc                                                                                                                                                                                                                                                                                                                                                                        | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo                                                                                                                                    |
| :-------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :----------- | :-------------- | :---------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Thứ 2** | • Đọc đặc tả v1.0 dài 1.189 đoạn và liệt kê các câu hỏi backend: tin đăng có những trạng thái nào, ai được xem báo giá, lưu giá tiền ra sao, giao dịch bị hủy thì xử lý thế nào                                                                                                                                                                                                        | 28/09/2026   | 28/09/2026      | [Đề xuất](../../2-proposal/), [AWS Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html)             |
| **Thứ 3** | • Tham gia [Sự kiện 2: AWS Cloud and AI Day Hanoi – Watch Party](../../4-eventparticipated/4.2-event2/) (08:00 – 17:00 tại văn phòng AWS Việt Nam, tầng 26, Bitexco Financial Tower). Xem keynote từ Hà Nội về Agentic AI, Data Foundation và hiện đại hóa Cloud, rồi cùng thảo luận tại chỗ về cách đưa AI Agent vào vận hành thật và tối ưu chi phí; bài học: chốt mức chi phí chấp nhận được trước rồi mới chọn công cụ                                                                                 | 29/09/2026   | 29/09/2026      | [Sự kiện 2](../../4-eventparticipated/4.2-event2/), [AWS Cost Explorer](https://docs.aws.amazon.com/cost-management/latest/userguide/ce-what-is.html) |
| **Thứ 4** | • Ánh xạ mỗi vai trò người dùng (Khách, Đối tác cấp 1, Đối tác cấp 2, Admin, Finance Admin) với các hành động API được phép gọi; bảng này về sau thành 4 group Cognito `Admins`, `FinanceAdmins`, `Partners`, `Owners`                                                                                                                                                                 | 30/09/2026   | 30/09/2026      | [Group trong Cognito User Pool](https://docs.aws.amazon.com/cognito/latest/developerguide/cognito-user-pools-user-groups.html)                        |
| **Thứ 5** | • Viết các quyết định backend vào sổ quyết định: trạng thái tin đăng (`PENDING_REVIEW` → `ACTIVE` → `MATCHED` → `COMPLETED` / `EXPIRED` / `CANCELLED`), trạng thái báo giá và giao dịch, bên nào (`OWNER`, `PARTNER`, `ADMIN`, `SYSTEM`) được thực hiện từng bước chuyển, và mọi giá tiền lưu dạng số nguyên VND                                                                       | 01/10/2026   | 01/10/2026      | [Repository ReLoop](https://github.com/madlyham/ReLoop/tree/main/backend/api) (`src/domain/stateMachines.ts`)                                         |
| **Thứ 6** | • Tham gia [Sự kiện 3: Fireside Chat with Dr. Werner – Navigating the Future of Cloud & AI in Vietnam](../../4-eventparticipated/4.3-event3/) (10:30 – 12:00 tại văn phòng AWS Việt Nam, tầng 26, Bitexco Financial Tower). Dr. Werner nói về "Renaissance Developer" và việc kỹ sư vẫn phải chịu trách nhiệm với code do AI viết. Nhận vai trò **Backend Engineer**: tầng dữ liệu DynamoDB và quy tắc nghiệp vụ | 02/10/2026   | 02/10/2026      | [Sự kiện 3](../../4-eventparticipated/4.3-event3/), [Tài liệu AWS IAM](https://docs.aws.amazon.com/iam/)                                              |

## **3. Kết quả đạt được**

### **Cơ sở lý thuyết**

- Học được rằng một quyết định có mã (ví dụ QĐ-07) chấm dứt tranh luận lặp lại và cho code review một mốc tham chiếu rõ ràng.
- Rút ra từ bài nói của Dr. Werner Vogels: backend phải tính trước chuyện lỗi; retry, ghi idempotent và cập nhật có điều kiện là một phần của thiết kế.
- Hiểu ý tưởng FinOps ở AI Day: thống nhất hệ thống được phép tốn bao nhiêu mỗi tháng trước khi chọn dịch vụ.

### **Cài đặt & Thiết lập môi trường**

- Quy tắc backend đã ghi vào sổ quyết định chung: danh sách trạng thái, các bước chuyển hợp lệ và bên được thực hiện từng bước.
- Bảng vai trò – hành động mà phần phân quyền backend làm theo.

### **Kỹ năng thực hành & Vận hành**

- Biến những phần mơ hồ của đặc tả thành quy tắc trạng thái rõ ràng, có thể code thẳng thành state machine.
- Tham dự trọn ngày AI Day watch party và buổi fireside chat với Dr. Werner Vogels tại Bitexco Financial Tower.
