---
title: "Chia sẻ, đóng góp ý kiến"
date: 2026-11-25
weight: 7
chapter: false
pre: " <b> 7. </b> "
---

Dưới đây là những chia sẻ cá nhân và góp ý xây dựng của mình sau thời gian tham gia chương trình **First Cloud AI Journey (FCAJ)**, với mong muốn đóng góp cho việc trải nghiệm của các khóa thực tập sinh tiếp theo.

### Đánh giá chung

**1. Môi trường làm việc**

Cởi mở và thực tế. Phần lớn việc học diễn ra qua kênh trao đổi của nhóm và tại văn phòng AWS Việt Nam (tầng 26, Bitexco), nơi các sự kiện giúp mình gặp trực tiếp với các anh chị mentor, kỹ sư AWS và các bạn thực tập khác. Mọi thắc mắc về bất kỳ mức độ nào đều được lắng nghe, trao đổi và góp ý để đạt được kết quả, nhờ đó giúp bản thân biết mình cần được trau dồi thêm những kiến thức nào.

**2. Sự hỗ trợ của mentor / team admin**

Các anh/chị mentor định hướng thay vì đưa sẵn đáp án: góp ý kiến trúc, proposal và đặt nhiều câu hỏi khó về chi phí và bảo mật. Team admin sắp xếp sự kiện, hạn nộp và mẫu báo cáo rõ ràng. Nếu có thêm một buổi ở giữa kỳ để báo cáo tiến độ và kiến trúc thì có thể sẽ hiệu quả hơn.

**3. Sự phù hợp giữa công việc và chuyên ngành học**

Rất phù hợp. Mình học an toàn thông tin, và trong ReLoop mình được phân vai trò làm backend, trước đó thì mình cũng đã có tìm hiểu nên với lần này thì ngoài việc biết được các luồng xử lý dữ liệu thì còn giúp mình vận dụng kiến thức vào một hệ thống thực tế. Bên cạnh phần backend, mình còn tìm hiểu các lớp bảo mật nhóm áp dụng cho hệ thống: AWS WAF, đăng nhập Cognito, IAM role, cùng với việc vận dụng WAF vào trong việc kiểm tra đăng nhập hoặc spam. Ngoài dự án, riêng bản thân còn được trải nghiệm thêm về pentest khi tự sử dụng thử dịch vụ AWS Security Agent.

**4. Cơ hội học hỏi & phát triển kỹ năng**

Mình thấy bản thân có tiến bộ thêm nhờ nghiên cứu tìm hiểu trong dự án ReLoop: WAF, CloudFront, Cognito, Lambda, API Gateway, DynamoDB, Rekognition, Bedrock, Terraform và GitHub Actions trên một dự án chạy thật, cùng với việc so sánh DynamoDB với RDS để chọn cơ sở dữ liệu phù hợp. Kỹ năng mềm cũng tốt lên: viết proposal, ghi worklog hằng tuần, viết 3 bài blog về triển khai các bước vận hành tối đa hỗ trợ cho học tập, nghiên cứu và tìm hiểu hướng đi về luồng xử lý code sao cho không bị xung đột. Ngoài dự án, được thực tập ở AWS giúp mình có thể tự xây dựng thử một hệ thống sử dụng EC2 để làm trạm trung chuyển (gateway) nhằm phục vụ việc kiểm thử độ trễ mạng đa vùng, định tuyến lưu lượng ổn định khi kết nối quốc tế và quản lý tập trung địa chỉ IP đầu ra cho hệ thống.

**5. Văn hóa & tinh thần đồng đội**

Nhóm AWSS3nt1n4L chia việc theo thế mạnh (frontend, backend, AI, hạ tầng) và luôn hỗ trợ nhau khi có người bị kẹt. Tại các sự kiện, các chia sẻ của anh/chị mentor và các diễn giả đều rất hay, đáng để học hỏi, nhưng cũng không kém khi cộng đồng FCAJ rất là thân thiện, ham học hỏi nên thường phần hỏi đáp sẽ kéo rất dài.

**6. Chính sách / phúc lợi cho thực tập sinh**

Phúc lợi chính là credit AWS để xây dựng trên dịch vụ thật, được tham gia miễn phí các sự kiện và workshop của AWS, và làm việc từ xa linh hoạt giữa các buổi lên văn phòng. Nếu giới hạn của tài khoản (quotas) được nói rõ lúc đầu thì việc thực tập sẽ rõ ràng hơn.

---

### Một số câu hỏi khác

**Điều bạn hài lòng nhất trong thời gian thực tập?**

Đưa ReLoop từ một ý tưởng thành hệ thống chạy thật trên các dịch vụ AWS trong 12 tuần. Khoảnh khắc đáng nhớ nhất là lúc kiểm thử lớp bảo vệ WAF của hệ thống. Lúc đầu mình chỉ gửi thử một ít request để xem hệ thống phản ứng thế nào khi bị spam, sau đó tăng lên gửi thật nhiều request liên tục, và kết quả là các request đó bị chặn đúng như WAF đã cảnh báo. Sau khi khắc phục, hệ thống không còn tình trạng IP bẩn (IP có dấu hiệu tấn công hoặc spam) hay request spam lọt vào nữa. Tiếp theo là chạy thử sản phẩm: gửi một ảnh thật lên, bấm AI phân tích và AI mô tả đúng khoảng 90% nội dung bức ảnh, người đăng tin chỉ cần chỉnh lại một chút trước khi đăng. Các sự kiện tại văn phòng AWS, nhất là phiên hỏi đáp kéo dài đầy sôi nổi tại sự kiện Cloud Mastery, cũng rất đáng nhớ.

**Điều bạn nghĩ công ty cần cải thiện cho các thực tập sinh sau?**

Có thể hỗ trợ thêm ít quotas của Bedrock về Claude Sonnet thì sẽ hiệu quả hơn.

**Nếu giới thiệu cho bạn bè, bạn có khuyên họ thực tập ở đây không? Vì sao?**

Có, với những bạn sẵn sàng tự học. Bạn được thực hành thực tế với AWS sẽ giúp bạn trải nghiệm được quá trình làm dự án rõ ràng kèm theo các sơ đồ kiến trúc, được đồng hành và hỗ trợ bởi các anh chị trong team, và được học hỏi thêm các kiến thức thông qua sự kiện.

---

### Đề xuất & mong muốn

**Bạn có đề xuất gì để cải thiện trải nghiệm trong kỳ thực tập?**

- Một buổi demo giữa kỳ để các nhóm trình bày tiến độ và nhận góp ý của mentor trước buổi thuyết trình cuối.
- Một trang "bài học kinh nghiệm" chung về các lỗi hay gặp từ dịch vụ (IAM về phân quyền và tài chính).

**Bạn có muốn tiếp tục chương trình này trong tương lai?**

Có. Mình muốn tiếp tục hoàn thiện ReLoop, tham gia tích cực vào cộng đồng FCAJ.

**Góp ý khác (tự do chia sẻ):**

Cảm ơn các anh/chị mentor, team admin FCAJ và các thành viên nhóm AWSS3nt1n4L.
