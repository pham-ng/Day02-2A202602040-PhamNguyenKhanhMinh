# 01 - Individual Problem Scan

Chủ đề cá nhân chọn để scan: **Tự động hóa phân loại và xử lý Ticket Support cho lớp học 1.000+ học viên**

## 1. Scan rộng

| # | Lăng kính | Problem quan sát được | Ai chịu ảnh hưởng? | Dấu hiệu thật |
|---|---|---|---|---|
| 1 | Lặp lại | TA phải đọc và gõ câu trả lời thủ công cho nhiều ticket có cùng nội dung (deadline, link nộp bài, quyền GitHub/LMS) | TA, Mentor | Mất 3-5h/ngày vào đợt checkpoint; trả lời cùng một câu hỏi hàng chục lần |
| 2 | Tốn thời gian | Ticket khẩn cấp (lỗi kỹ thuật, mất quyền truy cập hệ thống) bị lẫn vào hàng chờ (queue) chung với câu hỏi thông thường | Học viên, TA | Ticket khẩn bị trễ 1-2 ngày; học viên bị nghẽn tiến độ không nộp được bài |
| 3 | Pain từ người khác | Học viên gửi ticket thiếu thông tin (không ghi rõ bài tập nào, thiếu ảnh chụp lỗi, thiếu link repo) | TA, Học viên | TA phải trao đổi 2-3 vòng mới xác định đúng nguyên nhân lỗi, tốn 4-12h thu thập thông tin |
| 4 | AI có thể tốt hơn | Học viên không tìm thấy thông tin deadline/quy định đã thông báo trên Discord/LMS nên tạo ticket hỏi lại | Học viên, TA | Tìm kiếm trên Discord khó khăn, tốn 15-30 phút tra cứu tin nhắn cũ cho mỗi lần tìm |
| 5 | Tốn thời gian | Coach/TA Lead khó tổng hợp được các chủ đề lỗi nổi bật trong ngày để cảnh báo chung cho cả lớp | Coach, TA Lead | Phải đọc lướt qua 100+ ticket thủ công mỗi cuối ngày, mất 2-3h tổng hợp |
| 6 | Rủi ro chất lượng | Lớp quy mô lớn (>1.000 học viên) khiến TA quá tải, dẫn đến trả lời sót hoặc phản hồi thiếu chu đáo | Học viên, TA | Tỷ lệ hài lòng của học viên giảm, hàng chờ tồn đọng 50+ ticket mỗi ngày |

## 2. Top 3

| Rank | Problem | Vì sao chọn | Điều còn chưa chắc |
|---|---|---|---|
| 1 | Phân loại, gom nhóm ticket trùng lặp và phát hiện ticket khẩn cấp | Điểm nghẽn vận hành nghiêm trọng của TA/Mentor, bottleneck rõ ràng, đo lường được bằng thời gian phản hồi ticket khẩn cấp | Tỷ lệ ticket trùng lặp thực tế trong log là bao nhiêu %; rủi ro AI phân loại sai ticket khẩn |
| 2 | Tự động hóa Form Validation & Thu thập ngữ cảnh Ticket | Giảm thời gian trao đổi lặp lại do ticket thiếu thông tin ngữ cảnh ban đầu | Phụ thuộc vào khả năng tùy biến giao diện UI/Form của hệ thống ticketing |
| 3 | Tự động tổng hợp câu hỏi thường gặp (Auto FAQ) & Cảnh báo lỗi gia tăng đột biến | Giúp tự động phát hiện các câu hỏi lặp lại nhiều lần để đăng bài giải đáp chung cho cả lớp, giảm bớt ticket mới | Nếu học viên không có thói quen đọc thông báo giải đáp chung thì tác động thực tế không cao |

## 3. Problem Card #1 - Phân loại và gom nhóm Ticket Support

**Problem 1 câu:**  
Trong lớp học quy mô 1.000+ học viên, lượng ticket gửi về quá lớn gây quá tải hàng chờ; TA phải đọc và phân loại thủ công từng ticket, khiến các ticket lỗi kỹ thuật/quyền truy cập khẩn cấp bị trễ từ 1–2 ngày.

**Actor:**  
Trợ giảng (TA), Mentor phụ trách hỗ trợ và Học viên gửi ticket.

**Thời điểm / bối cảnh:**  
Các đợt cao điểm nộp bài (Deadline bài tập tuần, Checkpoint dự án, kỳ thi trực tuyến).

**Current workflow:**

```text
1. Học viên gặp sự cố và tạo ticket với nội dung mô tả tự do
2. Ticket đi vào hàng chờ (queue) chung của hệ thống hỗ trợ theo thứ tự thời gian
3. TA mở từng ticket và đọc nội dung chi tiết thủ công
4. TA tự đánh giá chủ đề và mức độ ưu tiên bằng mắt
5. TA gõ câu trả lời thủ công hoặc nhắn lại hỏi thêm thông tin nếu thiếu
6. Nếu là trường hợp phức tạp/lỗi hệ thống, TA escalate (chuyển tiếp) cho Tech Lead/Mentor
```

**Bottleneck:**  
Bước 3-5: TA mất quá nhiều thời gian đọc lặp đi lặp lại các ticket tương tự nhau và tự phân loại thủ công, dẫn đến ticket khẩn cấp bị chìm dưới lượng lớn ticket thông thường.

**Impact:**  
Ticket khẩn cấp bị tồn đọng 1–2 ngày; TA kiệt sức do tác vụ lặp lại (mất 3-5h/ngày); học viên hoang mang vì chậm tiến độ bài tập.

**Success metric:**  
Giảm thời gian nhận diện ticket khẩn cấp từ 24–48 giờ xuống dưới 2 giờ; Giảm 50–70% số ticket trùng lặp mà TA phải trả lời thủ công trong giai đoạn thử nghiệm (pilot).

**Non-AI alternative:**  
Tạo Google Form bắt buộc chọn Danh mục/Độ ưu tiên cố định (Category/Priority), viết sẵn câu trả lời mẫu (Canned Responses) cho TA sao chép, hoặc sử dụng chatbot FAQ theo từ khóa (keyword).

**AI hypothesis:**  
AI đóng vai trò phân loại (classification), chấm điểm ưu tiên (priority), gom nhóm (clustering) ticket trùng lặp và soạn thảo câu trả lời mẫu (draft responses); TA kiểm duyệt (Human-in-the-loop) trước khi gửi.

**Quick gut:**  
Workflow.

### Draft current workflow

```text
CURRENT STATE - Trả lời trễ 1-2 ngày

[1 Học viên tạo ticket tự do]
-> [2 Vào hàng chờ (queue) chung]
-> [3 TA đọc từng ticket thủ công: 2-5'/ticket]  <-- bottleneck
-> [4 TA tự phân loại & gõ câu trả lời: 3-7'/ticket]  <-- bottleneck
-> [5 Escalate chuyển tiếp nếu cần]
-> [6 Học viên nhận phản hồi]
```

### Draft future workflow

```text
FUTURE STATE - Xử lý khẩn cấp dưới 2 giờ

[1 Học viên tạo ticket]
-> [2 Rule tự động thu thập metadata: 5s]
-> [3 AI phân loại, đánh giá ưu tiên & gom nhóm ticket trùng: 10s]
-> [4 AI soạn thảo câu trả lời mẫu: 5s]
-> [5 TA kiểm duyệt / phê duyệt / chuyển tiếp: 1-2']  <-- human boundary
-> [6 Phản hồi tới học viên]

Fallback: Nếu AI có độ tự tin (confidence) thấp hoặc phát hiện từ khóa rủi ro cao -> đẩy trực tiếp vào hàng chờ thủ công cho TA xử lý.
```

## 4. Problem Cards #2 và #3 - tóm tắt

| Card | Actor | Bottleneck | Metric | Quick gut | Vì sao chưa chọn làm #1 |
|---|---|---|---|---|---|
| Tự động hóa Form Validation & Thu thập ngữ cảnh Ticket | Học viên, TA | Ticket thiếu thông tin khiến TA phải trao đổi qua lại 2-3 vòng | Ticket thiếu info < 5%; Phản hồi vòng đầu < 15 phút | Rule / Workflow | Chỉ giải quyết khâu đầu vào, chưa giải quyết triệt để tình trạng quá tải hàng chờ |
| Tự động tổng hợp câu hỏi thường gặp (Auto FAQ) & Cảnh báo lỗi gia tăng đột biến | TA Lead, Coach | Tổng hợp log thủ công cuối ngày mới phát hiện đợt lỗi | Phát hiện đợt lỗi gia tăng đột biến < 30 phút | Workflow | Đây là tính năng bổ trợ (output phụ) cho khâu Phân loại ticket |
