---
title: "Nhật ký công việc Tuần 12"
date: 2026-11-25
weight: 12
chapter: false
pre: " <b> 1.12. </b> "
---

# **Nhật ký công việc Tuần 12 — Báo cáo cuối, Demo trực tiếp các luồng backend của tôi & Bàn giao [Dự kiến]**

> **Trạng thái:** Dự kiến (tuần kế tiếp: 30/11/2026 – 04/12/2026; cập nhật ngày 25/11/2026).

## **1. Mục tiêu tuần**

- Hoàn thiện báo cáo thực tập với kết quả đã kiểm chứng từ phần việc của tôi (mô hình dữ liệu, job nền, job AI, ghép chi nhánh, load test).
- Demo các luồng backend tôi đã làm: AI tạo tin, ghép chi nhánh và đóng tin hết hạn.
- Bàn giao ghi chú rõ ràng về các module của tôi để người khác vận hành và sửa được mà không cần tôi.

## **2. Lịch trình thực hiện**

| Ngày      | Mô tả công việc dự kiến                                                                                                                            | Ngày dự kiến | Trạng thái | Tài liệu tham khảo                                                                                                                                                                                               |
| :-------- | :------------------------------------------------------------------------------------------------------------------------------------------------- | :----------- | :--------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Thứ 2** | • Viết phần của tôi trong báo cáo cuối: thiết kế khóa, hẹn giờ, ghép chi nhánh chạy nền và job AI, kèm lý do cho từng lựa chọn                     | 30/11/2026   | Dự kiến    | [Repository ReLoop](https://github.com/madlyham/ReLoop/tree/main/backend/api) (`src/store/keys.ts`), [AWS Well-Architected Framework](https://docs.aws.amazon.com/wellarchitected/latest/framework/welcome.html) |
| **Thứ 3** | • Hoàn thiện báo cáo: kết quả load test (`5xx` 26% → 0), bảng chi phí 11,70 USD/tháng và bài học rút ra                                            | 01/12/2026   | Dự kiến    | [Đề xuất](../../2-proposal/), [AWS Cost Explorer](https://docs.aws.amazon.com/cost-management/latest/userguide/ce-what-is.html)                                                                                  |
| **Thứ 4** | • Tổng duyệt demo các luồng của tôi bằng tài khoản thử: AI tạo tin từ ảnh, ghép với chi nhánh gần, đóng tin hết hạn                                | 02/12/2026   | Dự kiến    | [Workshop 5.11](../../5-workshop/5.11-end-to-end-verification/)                                                                                                                                                  |
| **Thứ 5** | • Trình bày các luồng của tôi trong buổi demo trực tiếp cuối cùng với mentor AWS và trả lời câu hỏi về thiết kế backend                            | 03/12/2026   | Dự kiến    | [Đề xuất](../../2-proposal/), [Workshop](../../5-workshop/)                                                                                                                                                      |
| **Thứ 6** | • Bàn giao ghi chú về các module của tôi (định dạng khóa trong `keys.ts`, các loại mốc hẹn giờ, quy tắc ghép, giới hạn AI) và kết thúc kỳ thực tập | 04/12/2026   | Dự kiến    | [Repository ReLoop](https://github.com/madlyham/ReLoop)                                                                                                                                                          |

## **3. Kết quả dự kiến**

### **Cơ sở lý thuyết**

- Củng cố bài học: tài liệu rõ ràng là một phần của sản phẩm, người khác phải vận hành được code của tôi mà không cần tôi.
- Tổng kết chặng đường 12 tuần từ tự học kiến thức AWS cơ bản đến xây dựng các job nền của một backend serverless.

### **Cài đặt & Thiết lập môi trường**

- Báo cáo cuối và ghi chú bàn giao cho các module của tôi đã hoàn tất.
- Các module của tôi chạy trên stack ReLoop trong thời hạn credit AWS (đến 28/02/2027).

### **Kỹ năng thực hành & Vận hành**

- Demo trực tiếp trôi chảy các luồng của tôi.
- Giải thích rõ các đánh đổi trong phần backend của tôi (một bảng, hẹn giờ theo ngăn giờ, job bất đồng bộ, ghép bằng geohash) khi mentor hỏi.
