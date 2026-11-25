---
title: "Tự đánh giá"
date: 2026-11-25
weight: 6
chapter: false
pre: " <b> 6. </b> "
---

## Báo cáo tự đánh giá kết quả thực tập

Tôi thực tập tại **Công ty TNHH Amazon Web Services Việt Nam (Workforce Bootcamp - First Cloud AI Journey)** từ **14/09/2026 đến 04/12/2026**. Là sinh viên ngành An toàn thông tin tại Đại học FPT, đây là lần đầu tôi được áp dụng những gì đã học vào một hệ thống chạy thật trên AWS.

Hai tuần đầu tôi tự học nền tảng AWS và các dịch vụ serverless. Sau đó tôi nhận vai trò **Backend Engineer** trong nhóm **ReLoop**, một chợ mua bán đồ điện tử cũ và hỏng chạy serverless trên AWS. Phần tôi phụ trách gồm: thiết kế khóa DynamoDB một bảng (`keys.ts`), các quy tắc nghiệp vụ backend, timer chạy nền không dùng `Scan` (`timers.ts`) gắn với EventBridge, ghép tin đăng với chi nhánh gần nhất bằng geohash, và chạy lại load test để xác nhận lỗi `5xx` giảm từ 26% về 0. Về phần AI, tôi tự test các model phân tích ảnh và chọn Kimi K3 cho ReLoop. Tôi cũng viết phần backend cho Proposal Phần 1 và Phần 2, và 3 bài blog về bảo mật trên AWS.

Về thái độ làm việc, tôi cố gắng hoàn thành đúng hạn các phần được giao, viết tài liệu dựa trên code thật để mọi số liệu đều kiểm chứng được, và trao đổi với nhóm khi gặp vướng mắc.

Tôi tự đánh giá bản thân theo các tiêu chí sau:

| STT | Tiêu chí đánh giá | Mô tả | Tốt | Khá | Trung bình | Nhận xét cụ thể |
| :---: | :--- | :--- | :---: | :---: | :---: | :--- |
| 1 | **Kiến thức & kỹ năng chuyên môn** | Nắm vững chuyên môn, áp dụng thực tế, sử dụng thành thạo công cụ, chất lượng công việc | ☐ | ✅ | ☐ | Dùng được DynamoDB, Lambda, API Gateway, EventBridge và S3 cho phần backend của ReLoop; vẫn cần học sâu hơn về giới hạn của từng dịch vụ và các trường hợp lỗi. |
| 2 | **Khả năng học hỏi** | Khả năng tiếp thu kiến thức mới và tốc độ nắm bắt công việc | ✅ | ☐ | ☐ | Tự học nền tảng AWS và serverless trong 2 tuần đầu, đến tuần 4 đã bắt đầu viết code backend (`keys.ts`, 09/10/2026). |
| 3 | **Tính chủ động** | Tinh thần tự giác, chủ động tìm kiếm công việc mà không chờ nhắc nhở | ✅ | ☐ | ☐ | Chủ động rà đặc tả để đưa các quy tắc backend vào sổ quyết định chung, tự test các model AI phân tích ảnh để chọn model cho nhóm, và tự thử thêm AWS Security Agent ngoài dự án. |
| 4 | **Ý thức trách nhiệm** | Hoàn thành công việc đúng hạn và đảm bảo chất lượng cam kết | ☐ | ✅ | ☐ | Nộp phần backend cho Proposal Phần 1 (08/10) và Phần 2 (13/11) đúng hạn; cần kiểm tra kỹ hơn các trường hợp lỗi trước khi bàn giao một tính năng. |
| 5 | **Tính kỷ luật** | Tuân thủ giờ giấc, nội quy và quy trình làm việc | ☐ | ✅ | ☐ | Ghi worklog đều hằng tuần và làm theo quy tắc chung của nhóm; cần dọn tài nguyên tự tạo ngay sau khi thử thay vì để dồn lại cuối kỳ. |
| 6 | **Tinh thần cầu tiến** | Sẵn sàng lắng nghe góp ý và không ngừng hoàn thiện bản thân | ✅ | ☐ | ☐ | Tiếp thu các câu hỏi của mentor về chi phí và bảo mật; tự tìm hiểu thêm các lớp bảo mật của hệ thống (WAF, Cognito, IAM) dù đó không phải phần tôi phụ trách. |
| 7 | **Kỹ năng giao tiếp** | Khả năng trình bày ý tưởng và báo cáo công việc rõ ràng, mạch lạc | ☐ | ✅ | ☐ | Viết được phần backend của proposal bằng lời dễ hiểu cho người ngoài nhóm; cần cập nhật tiến độ với các mảng khác thường xuyên hơn. |
| 8 | **Làm việc nhóm** | Phối hợp hiệu quả với đồng nghiệp và tích cực trong hoạt động nhóm | ☐ | ✅ | ☐ | Làm đúng phần việc đã chia trong nhóm AWSS3nt1n4L và nối phần backend của mình với phần AI và hạ tầng của các bạn; cần chủ động hỗ trợ các mảng khác nhiều hơn. |
| 9 | **Tác phong làm việc** | Tôn trọng đồng nghiệp, đối tác và văn hóa doanh nghiệp | ✅ | ☐ | ☐ | Tôn trọng mentor, đồng đội và đối tác; tham gia đủ 6 sự kiện tại văn phòng AWS Việt Nam. |
| 10 | **Kỹ năng giải quyết vấn đề** | Nhận diện vấn đề, đề xuất giải pháp sáng tạo và khả thi | ☐ | ✅ | ☐ | Giải quyết được các vấn đề thật như tìm tin theo vị trí và chạy timer nền mà không cần `Scan`; nhưng có lỗi, như `5xx` khi tải cao, chỉ lộ ra khi chạy load test. |
| 11 | **Đóng góp cho dự án/tập thể** | Hiệu quả công việc thực tế, sáng kiến và sự ghi nhận từ nhóm | ☐ | ✅ | ☐ | Đóng góp phần lõi backend của ReLoop: thiết kế dữ liệu, quy tắc nghiệp vụ, timer, ghép chi nhánh và số liệu load test cho báo cáo; cùng kết quả tự test AI để chọn Kimi K3. |
| 12 | **Đánh giá chung** | Nhận định tổng thể về toàn bộ quá trình thực tập | ☐ | ✅ | ☐ | Đi từ tự học AWS cơ bản đến tự viết các phần backend chạy thật trong 12 tuần; vẫn cần cải thiện việc lường trước lỗi và giới hạn dịch vụ, cũng như trao đổi với nhóm. |

---

### Những điểm cần cải thiện

* **Lường trước lỗi và giới hạn dịch vụ:** Một số vấn đề tôi chỉ phát hiện khi đã chạy thật, như lỗi `5xx` khi tải cao chỉ lộ ra lúc chạy load test. Tôi cần nghĩ tới timeout, concurrency, quota và các trường hợp chạy trùng ngay từ lúc thiết kế.
* **Dọn tài nguyên gọn gàng hơn:** Những tài nguyên tôi tạo khi tự thử và khi phát triển, nằm ngoài Terraform, vẫn phải để tới tuần 11 mới rà và dọn. Tôi nên dọn ngay sau khi thử xong.
* **Trao đổi với nhóm:** Tôi tập trung nhiều vào phần backend của mình. Tôi cần cập nhật tiến độ và hỏi han các mảng khác (frontend, AI, hạ tầng) thường xuyên hơn.

---

### Kế hoạch hành động

1. **Ghi giới hạn và trường hợp lỗi trước khi code:** Với mỗi tính năng chạy nền, ghi ra timeout, concurrency, quota và cách xử lý khi chạy trễ hoặc chạy trùng trước khi bắt đầu viết.
2. **Dọn tài nguyên ngay sau khi thử:** Gắn tag cho tài nguyên tự tạo và xem Cost Explorer hằng tuần để không còn gì chạy thừa.
3. **Cập nhật tiến độ hằng tuần cho nhóm:** Mỗi tuần chia sẻ ngắn phần backend đã làm gì, đang vướng gì và cần ai hỗ trợ.
