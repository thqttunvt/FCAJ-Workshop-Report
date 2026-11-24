---
title: "Nhật ký công việc"
date: 2026-11-25
weight: 1
chapter: false
pre: " <b> 1. </b> "
---

Nhật ký này ghi lại 12 tuần thực tập của tôi tại Amazon Web Services Việt Nam (Workforce Bootcamp - First Cloud AI Journey, từ 14/09/2026 đến 04/12/2026). Tuần 1–10 đã hoàn thành; Tuần 11–12 là kế hoạch và được ghi rõ là dự kiến. Hai tuần đầu tôi tự học nền tảng AWS và các dịch vụ serverless rồi tự thử trên Console. Sau đó tôi đảm nhận vai trò **Backend Engineer** của dự án **ReLoop**, một chợ trực tuyến serverless trên AWS giúp người dùng bán đồ điện tử cũ hoặc hỏng cho tiệm sửa chữa, người buôn lại và đơn vị tái chế gần nhà. Phần của tôi là thiết kế khóa DynamoDB, quy tắc nghiệp vụ, job AI chạy nền, hẹn giờ không cần scan, ghép chi nhánh và giới hạn AI theo ngày. Mỗi tuần liệt kê việc tôi làm theo từng ngày.

Song song với dự án, tôi đã tham gia **6 sự kiện** do AWS Việt Nam và các đối tác tổ chức. Mỗi sự kiện được đối chiếu trong tuần diễn ra và mô tả chi tiết ở mục [Các sự kiện đã tham gia](../4-eventparticipated/).

### Tổng quan nhật ký theo tuần

- **Tuần 1:** [Nhập môn FCAJ & Tự học nền tảng AWS: Hạ tầng toàn cầu, IAM, AWS CLI, VPC & EC2](1.1-week1/)
- **Tuần 2:** [Tự học các dịch vụ serverless (S3, DynamoDB, Lambda, API Gateway), Chi phí AWS cơ bản & Buildrathon Kickoff](1.2-week2/)  
  _(Đối chiếu: [Sự kiện 1: Buildrathon – Kickoff: Code the Future with CMC Global](../4-eventparticipated/4.1-event1/) ngày 26/09/2026)_
- **Tuần 3:** [Rà soát đặc tả ReLoop, Quy tắc nghiệp vụ backend, AI Day Watch Party & Fireside Chat với Dr. Werner Vogels](1.3-week3/)  
  _(Đối chiếu: [Sự kiện 2: AWS Cloud and AI Day Hanoi – Watch Party](../4-eventparticipated/4.2-event2/) ngày 29/09/2026 & [Sự kiện 3: Fireside Chat với Dr. Werner Vogels](../4-eventparticipated/4.3-event3/) ngày 02/10/2026)_
- **Tuần 4:** [Access pattern DynamoDB, Thiết kế khóa một bảng, Đề xuất Phần 1 & keys.ts](1.4-week4/)
- **Tuần 5:** [Job AI tạo tin đăng chạy nền: aiService.ts, Lambda tự gọi bất đồng bộ & Kiểm tra đầu ra AI](1.5-week5/)
- **Tuần 6:** [Hẹn giờ chạy nền không cần scan (timers.ts), Job quét EventBridge 15 phút & Cloud & AI Infrastructure Meetup](1.6-week6/)  
  _(Đối chiếu: [Sự kiện 4: Cloud & AI Infrastructure Meetup](../4-eventparticipated/4.4-event4/) ngày 24/10/2026)_
- **Tuần 7:** [Sự kiện cộng đồng Smart Plushies, Cập nhật job AI cho Kimi K3 & Chặn job treo](1.7-week7/)  
  _(Đối chiếu: [Sự kiện 5: Smart Plushies for Children – In Collaboration with Operation Smile Vietnam](../4-eventparticipated/4.5-event5/) ngày 26/10/2026)_
- **Tuần 8:** [Ghép chi nhánh chạy nền bằng Geohash & Haversine, Giới hạn AI theo ngày & Lịch sử nhãn AI](1.8-week8/)
- **Tuần 9:** [Phần backend trong Đề xuất Phần 2, Rà soát chi phí Cost Explorer & Sự kiện Cloud Mastery](1.9-week9/)  
  _(Đối chiếu: [Sự kiện 6: Cloud Mastery – Cloud Sharing Session for Students](../4-eventparticipated/4.6-event6/) ngày 14/11/2026)_
- **Tuần 10:** [Chạy lại load test: 5xx từ 26% về 0, Kiểm tra giới hạn tốc độ & Ghi lại kết quả](1.10-week10/)
- **Tuần 11:** [Dọn tài nguyên thừa của tôi, Kiểm tra lại module & Kiểm tra chi phí cuối [Dự kiến]](1.11-week11/)
- **Tuần 12:** [Báo cáo cuối, Demo trực tiếp các luồng backend của tôi & Bàn giao [Dự kiến]](1.12-week12/)
