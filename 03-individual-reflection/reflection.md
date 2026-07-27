# 03 — Individual Reflection — Day 02

## Thành viên nhóm

| STT | Họ và tên | Mã học viên | Vai trò trong nhóm |
|-----|-----------|-------------|--------------------|
| 1 | Trần Duy Khánh | | Pitch problem owner: Trình bày bài toán ticket support triage, đề xuất luồng xử lý và góp ý hoàn thiện quy trình vận hành cho trợ giảng (TA) |
| 2 | Nguyễn Hùng Phát | | Challenger: Phản biện phạm vi bài toán, cảnh báo rủi ro AI phân loại sai ticket khẩn cấp và hỗ trợ lập kế hoạch kiểm chứng |
| 3 | Lê Nhật Hoàng | | Problem Statement owner: Tổng hợp Problem Statement v0/v1, dẫn dắt so sánh ma trận độ mơ hồ và độ phức tạp giữa Rule / Workflow / Agent |
| 4 | Phạm Nguyễn Khánh Minh | | Research & Decision owner: Nghiên cứu các giải pháp hiện có trên thị trường, phân tích yếu tố rủi ro và tổng hợp quyết định thử nghiệm (Pilot) |

---

## Vai trò trong nhóm

**Vai trò:** Research & Decision owner

Em phụ trách nghiên cứu hiện trạng, phân tích các giải pháp thị trường và hỗ trợ nhóm đưa ra đánh giá quyết định, cụ thể bao gồm:

- Khảo sát và phân tích mô hình xử lý ticket support của các công cụ hiện hành như Zendesk, Intercom, Freshdesk, Slack AI
- Đề xuất định hướng cho nhóm không xây dựng hệ thống tự động hoàn toàn mà chọn mô hình Workflow có sự kiểm duyệt của con người (Human-in-the-loop)
- Tổng hợp ma trận rủi ro, xác định ranh giới kiểm soát và xây dựng tiêu chí đánh giá cho quyết định cuối cùng (Go pilot nhỏ / Not Yet / No-Go)

## Tôi đã tham gia vào phần nào?

| Hoạt động | Tôi đã làm gì? | Kết quả / tác động |
|---|---|---|
| Scan cá nhân | Em đề xuất bài toán phân loại và xử lý Ticket Support từ thực tế vận hành lớp học 1.000+ học viên, chỉ ra điểm nghẽn quá tải của trợ giảng và tình trạng ticket khẩn cấp bị tồn đọng | Nhóm có một đề tài đầu vào cụ thể, đi kèm số liệu định lượng sơ bộ về khối lượng ticket và thời gian phản hồi |
| Pitch Problem Card | Em tham gia trình bày Problem Card #1 về Support Ticket Triage, làm rõ các đối tượng liên quan (Actor), quy trình hiện tại (Current Workflow) và nút thắt tại khâu phân loại thủ công | Bài toán đã được mô tả đầy đủ các yếu tố cốt lõi, giúp cả nhóm hình dung rõ điểm nghẽn cần tập trung giải quyết |
| Phản biện bài toán | Em cùng nhóm phản biện các đề tài khác như Nhắc lịch cá nhân hóa (phụ thuộc dữ liệu riêng tư) hay Auto FAQ đơn lẻ (chỉ giải quyết phần ngọn, không xử lý được ticket khẩn) | Giúp bớt được các ý tưởng quá rộng hoặc chưa đánh đúng điểm nghẽn, giữ sự tập trung vào bài toán hàng chờ ticket |
| Phân cụm ý tưởng | Em hỗ trợ tổng hợp 12 ý tưởng ban đầu thành 4 cụm bài toán (Ticket support, Reminder, FAQ/search, Dashboard) | Nhóm có bức tranh tổng quan và thống nhất chọn cụm Ticket Support làm đề tài trọng tâm |
| Lựa chọn đề tài | Em tham gia chấm điểm đồng thuận (đạt 33/35 điểm) dựa trên các tiêu chí: Đối tượng rõ ràng, Quy trình rõ ràng, Nỗi đau có căn cứ và Tác động đo lường được | Nhóm đạt sự thống nhất cao khi lựa chọn bài toán Support Ticket Triage cho lớp học quy mô lớn |
| Nghiên cứu giải pháp | Em trực tiếp tìm hiểu 4 công cụ trên thị trường (Zendesk, Intercom, Freshdesk, Slack AI), chỉ ra các hạn chế và bài học thực tiễn | Cùng bỏ qua định hướng xây dựng agent tự động hoàn toàn, chốt mô hình Workflow kết hợp Rule, AI và sự kiểm duyệt của trợ giảng |
| Xây dựng Workflow | Em cùng nhóm phác thảo luồng vận hành hiện tại và luồng cải tiến mục tiêu, xác định rõ các bước AI hỗ trợ và ranh giới kiểm duyệt của trợ giảng | Chọn quy trình mới đảm bảo tính khả thi và phân định rõ trách nhiệm giữa hệ thống quy tắc, AI và con người |
| Problem Statement | Em đóng góp ý kiến hoàn thiện Problem Statement v0 và v1, đặc biệt ở các trường ranh giới an toàn (Boundary) và điểm can thiệp của AI (AI Intervention Point) | Ngăn ngừa rủi ro AI tự ý đưa ra các quyết định vượt thẩm quyền, đưa những quy định hard code |
| Đánh giá cấp độ AI | Em cùng nhóm đưa bài toán vào ma trận (Độ mơ hồ cao + Độ phức tạp vừa/cao) và so sánh 3 cấp độ giải pháp (Rule / Workflow / Agent) | Nhóm thống nhất chọn mô hình Workflow có AI hỗ trợ nhằm cân bằng giữa hiệu quả giảm tải công việc và độ an toàn vận hành |
| Đưa ra quyết định | Em tổng hợp tiêu chí đánh giá và đề xuất phương án **Thử nghiệm nhỏ (Pilot)** trên dữ liệu ticket thực tế 1 tuần, chưa triển khai chính thức | Quyết định đảm bảo tính thận trọng và thực tế, giúp nhóm kiểm chứng giả định trước khi đầu tư nguồn lực |

---

## Bảng sử dụng AI trong quá trình làm bài

| Giai đoạn | Em dùng AI để làm gì? | AI hỗ trợ hiệu quả ở đâu? | AI chưa phù hợp / sơ sài ở đâu? | Em điều chỉnh gì dựa trên nhận định cá nhân? |
|---|---|---|---|---|
| Scan bài toán | Gợi ý cấu trúc phân tích theo 6 lăng kính và hệ thống hóa các dấu hiệu thực tế | Giúp gom các ý quan sát rải rác vào khung báo cáo nhìn gọn gàng | Hay bị phô trương dùng từ đao to búa lớn với gợi ý để AI nhảy vào sửa cả lỗi code | Giữ đúng thực tế vận hành là AI chỉ phân loại gom nhóm ticket, lỗi kỹ thuật vẫn phải do con người xử lý |
| Problem Card | Đề xuất khung mô tả quy trình hiện tại với các chỉ số đo lường hiệu quả | Chi tiết hóa luồng ticket di chuyển từ lúc gửi đến lúc phản hồi xong | AI tự ý cho phép hệ thống tự gửi thẳng phản hồi cho học viên mà bỏ qua khâu duyệt | Cài thêm ranh giới người thật (Human Boundary), bắt buộc TA phải bấm duyệt mới được gửi |
| Nghiên cứu | Tóm tắt các tính năng tự động hóa và ưu nhược điểm của các công cụ support hiện hành | Tổng hợp nhanh pattern xử lý ticket phổ biến của các bên Zendesk hay Intercom | Đánh giá quá cao các con agent tự trả lời mà ngó lơ rủi ro AI bịa tin sai | Rút ra bài học cho nhóm là chỉ dùng AI gom nhóm phân loại, giữ con người làm mốc chặn an toàn |
| Workflow | Phác thảo luồng vận hành trước sau kèm bảng phân tích đầu vào đầu ra | Chuẩn hóa sơ đồ quy trình và ước lượng thời gian tiết kiệm ở mỗi bước | Gộp chung bước phân loại với phản hồi làm mờ ranh giới kiểm duyệt | Tách rời thành 3 bước rõ ràng: AI gom nhóm $\rightarrow$ AI gợi ý câu trả lời $\rightarrow$ TA kiểm duyệt quyết định |
| Problem Statement | Kiểm tra độ đầy đủ các trường thông tin trong bản Problem Statement | Liên kết các thành phần quy trình thành một bản tuyên bố bài toán hoàn chỉnh | Nhét luôn giải pháp công nghệ vào phần mô tả vấn đề thay vì tập trung vào điểm nghẽn người dùng | Bóc tách phần mô tả vấn đề về đúng bản chất điểm nghẽn vận hành, chuyển hẳn AI sang trường điểm can thiệp |
| Đánh giá cấp độ AI | Lập bảng so sánh 3 cấp độ giải pháp trên ma trận độ mơ hồ và độ phức tạp | Phân tích rõ ưu nhược điểm giữa Rule-based, Workflow và Autonomous Agent | Thiên vị đề xuất làm Agent tự chủ cho hiện đại mà chưa tính hết rủi ro vận hành | Quyết định chốt mức Workflow có kiểm soát, bác bỏ phương án Agent vì nguy cơ mất an toàn dữ liệu |
| Đưa ra quyết định | Xây dựng tiêu chí đánh giá các phương án Go / Not Yet / No-Go và lập kế hoạch thử nghiệm | Đưa ra khung tiêu chí đánh giá quyết định khá logic và bài bản | Khẳng định Go Production ngay vì thấy tác động lớn và đo lường được | Hạ xuống mức Pilot nhỏ (Not Yet) vì baseline thực tế bắt buộc phải kiểm chứng qua dữ liệu thật |

---

## Kết luận cá nhân

Qua buổi học seminar, em nhận ra rằng vai trò **Research & Decision owner** không chỉ là tìm kiếm các giải pháp công nghệ mới, mà quan trọng hơn là giữ sự tỉnh táo và góc nhìn khách quan trước những phương án ẩn chứa nhiều rủi ro vận hành

Những bài học ý nghĩa nhất em rút ra được bao gồm:

1. **Tránh tâm lý phụ thuộc vào Agent tự động:** Một giải pháp AI hiệu quả trong vận hành không nhất thiết phải thay thế hoàn toàn con người. Mô hình **Workflow** hỗ trợ giảm bớt các thao tác lặp đi lặp lại (đọc, phân loại, soạn thảo mẫu), giúp con người tập trung vào các quyết định quan trọng nhất (kiểm duyệt, phê duyệt và xử lý các trường hợp khẩn cấp)
2. **Quyết định dựa trên thực tế (Evidence-based Decision):** Không nên vội vã triển khai chính thức khi các giả định chưa được kiểm chứng. Việc lựa chọn phương án "Thử nghiệm nhỏ" giúp nhóm vừa xác minh được tỷ lệ ticket trùng lặp thực tế, vừa xây dựng được hàng rào an toàn bảo vệ trải nghiệm của học viên
3. **Tinh thần phản biện:** trong quá trình làm việc nhóm, có những câu hỏi như *"Nếu AI phân loại sai ticket khẩn cấp thì hậu quả ra sao?"* hay *"Có giải pháp đơn giản hơn mà không cần dùng AI không?"* —  giúp bài toán của nhóm và suy nghĩ của em trở nên thực tế và chặt chẽ hơn

Trong các bài tập và dự án tiếp theo, em sẽ tiếp tục duy trì tư duy "Problem-First", ưu tiên xác minh dữ liệu thực tế trước khi lựa chọn công nghệ, và luôn thiết kế ranh giới kiểm duyệt minh bạch cho mọi ứng dụng AI
