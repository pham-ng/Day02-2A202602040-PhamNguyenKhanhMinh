# Group Report - Day 02

## Thành Viên Nhóm

| STT | Họ và tên | Mã học viên | Vai trò trong nhóm |
|-----|-----------|-------------|--------------------|
| 1   | Trần Duy Khánh |             | Pitch problem, góp ý workflow |
| 2   | Nguyễn Hùng Phát |             | Challenge scope, hỗ trợ validation |
| 3   | Lê Nhật Hoàng |             | Tổng hợp Problem Statement, so sánh Rule / Workflow / Agent |
| 4   | Phạm Nguyễn Khánh Minh |             | Research giải pháp, hỗ trợ decision |

## Candidate Problem Nhóm Chọn

```text
Trong lớp học hơn 1.000 học viên, số lượng TA/mentor có hạn nên queue ticket bị ngập bởi nhiều câu hỏi trùng lặp về bài tập, thông báo, lịch học, quyền truy cập, attendance và lỗi kỹ thuật. TA phải đọc và trả lời thủ công từng ticket, làm ticket mới hoặc ticket khẩn cấp bị trễ 1-2 ngày.
```

Mục tiêu ban đầu:

```text
Tự động phân loại và gom nhóm câu hỏi trùng lặp để rút ngắn thời gian nhận diện/chuyển xử lý ticket khẩn cấp xuống dưới 2 giờ.
```

---

# 01 - Group Convergence

## Tổng Hợp Candidate Problems

| # | Người đưa ra | Candidate problem | Người gặp vấn đề | Điểm nghẽn | Cảm nhận nhanh |
|---|---|---|---|---|---|
| 1 | Trần Duy Khánh | Ticket trùng lặp làm TA bị ngập | TA, học viên | Đọc và trả lời thủ công từng ticket | Đáng đào sâu nếu log xác nhận tỷ lệ lặp lại cao |
| 2 | Trần Duy Khánh | Nhắc lịch/checkpoint attendance cá nhân hóa | Học viên | Tự theo dõi lịch và tiến độ từ nhiều nguồn | Có giá trị nhưng cần data cá nhân |
| 3 | Nguyễn Hùng Phát | Tự động tạo FAQ từ câu hỏi lặp lại | TA lead, học viên | Phát hiện pattern thủ công | Gắn với ticket triage |
| 4 | Nguyễn Hùng Phát | Học viên không tìm thấy yêu cầu bài nộp | Học viên | Thông tin nằm trong worksheet/Discord/LMS | Có thể giải bằng checklist |
| 5 | Lê Nhật Hoàng | Hỏi lại quyền truy cập tool/GitHub/LMS | Học viên, TA | Nhiều lỗi truy cập lặp lại | Có urgency cao |
| 6 | Lê Nhật Hoàng | Coach khó nhìn nhóm học viên nào đang rớt tiến độ | Coach/mentor | Data attendance/checkpoint rải rác | Scope có thể lớn |
| 7 | Phạm Nguyễn Khánh Minh | Học viên hỏi lại deadline trên Discord | Học viên, TA | Search thông báo cũ khó | Có thể đưa vào FAQ/notification |
| 8 | Phạm Nguyễn Khánh Minh | Ticket lỗi kỹ thuật bị lẫn với câu hỏi bình thường | Học viên gặp lỗi | Queue không có priority rõ | Rất liên quan bài chọn |
| 9 | Phạm Nguyễn Khánh Minh | TA mất công viết lại cùng một câu trả lời | TA | Không có macro theo cluster | Dễ đo impact |
| 10 | Trần Duy Khánh | Ticket thiếu thông tin khiến TA phải hỏi lại nhiều vòng | TA, học viên | Học viên không biết cần ghi rõ lớp, buổi, link bài nộp, lỗi gặp ở đâu | Có thể cải thiện bằng form/rule trước khi dùng AI |
| 11 | Nguyễn Hùng Phát | TA khó ưu tiên ticket theo SLA/mức độ khẩn cấp | TA lead, mentor | Ticket khẩn cấp và ticket thông thường nằm chung một queue | Liên quan trực tiếp đến mục tiêu dưới 2 giờ |
| 12 | Lê Nhật Hoàng | Mentor khó xem dashboard cuối ngày về top issue của lớp | Mentor, TA lead | Phải đọc ticket thủ công mới biết chủ đề nào đang bùng lên | Có thể là output quản trị từ ticket triage |

## Gom Trùng / Cluster

| Cluster | Candidates included | Pattern chung | Ghi chú |
|---|---|---|---|
| A - Ticket support | 1, 5, 8, 9, 10, 11 | Queue support quá tải, ticket lặp lại, thiếu thông tin, khẩn cấp bị trễ | Chọn làm candidate chính |
| B - Reminder/checkpoint | 2, 6, 7 | Học viên cần nhắc lịch và cảnh báo theo tiến độ | Có thể là future extension |
| C - FAQ/search thông tin | 3, 4, 7 | Học viên không tìm thấy câu trả lời có sẵn | Có thể là output phụ từ ticket triage |
| D - Support dashboard | 6, 12 | Coach/mentor cần nhìn tổng quan tiến độ và vấn đề nổi bật | Có giá trị quản trị nhưng scope rộng hơn ticket triage |

## Shortlist

| Candidate | Vì sao vào shortlist | Rủi ro / điều chưa rõ |
|---|---|---|
| Ticket support triage | Actor rõ, workflow rõ, pain lặp lại, có metric thời gian xử lý | Cần validate tỷ lệ ticket trùng lặp và mức độ khẩn cấp |
| Personalized checkpoint reminder | Ảnh hưởng trực tiếp đến tiến độ học viên | Cần data attendance/checkpoint và quy tắc riêng tư |
| Auto FAQ from repeated questions | Giảm câu hỏi lặp lại, scope nhỏ | Nếu học viên không đọc FAQ thì impact giảm |

## Score Để Đồng Thuận

| Candidate | Actor rõ | Workflow rõ | Pain có evidence | Impact đo được | Làm trong lab | So sánh R/W/A được | Nhóm hiểu domain | Tổng |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Ticket support triage | 5 | 5 | 3 | 5 | 5 | 5 | 5 | 33 |
| Personalized checkpoint reminder | 5 | 4 | 3 | 4 | 3 | 4 | 4 | 27 |
| Auto FAQ from repeated questions | 4 | 4 | 4 | 4 | 5 | 4 | 5 | 30 |

Candidate nhóm chọn:

```text
Ticket support triage cho lớp 1.000+ học viên: phân loại, gom nhóm ticket trùng lặp, ưu tiên ticket khẩn cấp và đề xuất câu trả lời mẫu cho TA review.
```

Vì sao chọn:

```text
Problem này có actor rõ là TA/học viên, workflow hiện tại có thể vẽ được, bottleneck nằm ở bước đọc-phân loại-trả lời thủ công, metric có thể đo bằng thời gian ticket khẩn cấp được nhận diện/chuyển xử lý. Bài này cũng có thể so sánh rõ No AI, Rule, Workflow và Agent.
```

Vì sao không chọn các candidate còn lại:

```text
Checkpoint reminder có giá trị nhưng phụ thuộc nhiều vào data cá nhân và rule cảnh báo. Auto FAQ là bài tốt nhưng có thể được xem là một output phụ của ticket triage, không bao quát vấn đề ticket khẩn cấp bị đọng queue.
```

Nếu có disagreement, nhóm xử lý thế nào:

```text
Nhóm thống nhất chọn ticket support triage làm scope chính, nhưng giữ checkpoint reminder và FAQ như future extension. Trong bài lab, nhóm không xây trợ lý toàn năng mà chỉ tập trung vào queue ticket.
```

---

# 02 - Quick Validation + Research

## Quick Validation

Giả định cần validate trong lớp trước khi xem đây là problem đủ mạnh:

- Vào đợt deadline/checkpoint, ticket tăng mạnh và nhiều câu hỏi trùng lặp.
- TA/mentor đang phải đọc và trả lời thủ công nhiều ticket giống nhau.
- Ticket lỗi kỹ thuật/quyền truy cập khẩn cấp có thể bị chậm 1-2 ngày.

| Nguồn | Số người / số mẫu | Tín hiệu cần tìm để xác nhận | Tín hiệu có thể phản bác | Nhóm sẽ sửa problem thế nào |
|---|---:|---|---|---|
| Quick interview với TA/mentor | 2-3 | Nhiều ticket lặp lại về deadline, bài nộp, attendance, quyền truy cập | Một số câu hỏi có thể giải bằng FAQ/dropdown | Thu hẹp scope thành phân loại/gom nhóm/ưu tiên, không tự động trả lời tất cả |
| Micro survey học viên | 5-10 | Học viên thường hỏi lại vì không tìm thấy thông tin đúng lúc | Một số học viên chỉ cần thông báo rõ hơn, không cần AI | Thêm non-AI alternative: FAQ, checklist, form có category |
| Log ticket/LMS/Discord | 1 tuần gần deadline | Có thể đếm số ticket theo chủ đề và ticket trùng lặp | Nếu ticket trùng lặp ít thì bài toán yếu | Cần đo baseline trước khi pilot |

Baseline tạm thời chưa có số liệu thật, cần kiểm chứng:

```text
Trong tuần cao điểm, queue có thể có hàng trăm ticket. Nhóm sẽ kiểm chứng tỷ lệ ticket trùng lặp, thời gian ticket khẩn cấp chờ xử lý, và số ticket TA phải trả lời thủ công.
```

## Research Giải Pháp Đã Có

| Nguồn / tool / case | Link | Họ giải quyết phần nào? | Điểm mạnh | Khoảng trống / rủi ro | Bài học cho nhóm |
|---|---|---|---|---|---|
| Zendesk ticket routing | https://www.zendesk.com/service/ticketing-system/ | Quản lý ticket, routing, macro, automation | Tốt cho queue support và rule workflow | Câu hỏi tự do vẫn cần cấu hình/AI để hiểu ngữ cảnh | Rule và macro nên là nền tảng đầu tiên |
| Intercom AI customer service | https://www.intercom.com/ai-customer-service | AI hỗ trợ support, trả lời và triage | Pattern AI support đã phổ biến | Cần guardrail, source, human handoff | Không nên để AI tự xử lý case nhạy cảm |
| Freshdesk automation | https://www.freshworks.com/freshdesk/automation/ | Auto assign, ticket rules, canned response | Tốt cho phân loại có rule rõ | Kém với nội dung mơ hồ hoặc nhiều ý | Kết hợp rule + AI tốt hơn |
| Slack Workflow/AI summary pattern | https://slack.com/help/articles/25076892548883-Guide-to-Slack-AI | Tóm tắt hội thoại và tìm thông tin | Hữu ích khi câu hỏi nằm trong kênh chat | Không thay thế ticket workflow đầy đủ | AI summary có thể là input cho TA, không phải decision cuối |

Research takeaway:

```text
Không nên bắt đầu bằng một agent tự động trả lời và xử lý mọi ticket. Hướng hợp lý hơn là Workflow: rule/form lấy metadata cố định, AI phân loại và gom nhóm câu hỏi tự do, AI draft reply, TA review/approve/escalate. Các ticket confidence thấp hoặc có rủi ro cao phải đẩy cho người thật.
```

---

# 03 - Workflow + Problem Statement

## Current Workflow Bản Nhóm

```text
CURRENT STATE - ticket support thủ công

[1 Học viên gặp vấn đề]
-> [2 Học viên tạo ticket với nội dung tự do]
-> [3 Ticket vào queue chung]
-> [4 TA đọc từng ticket]
-> [5 TA tự phân loại chủ đề và mức độ khẩn cấp]
-> [6 TA gõ câu trả lời thủ công hoặc hỏi thêm thông tin]  <-- bottleneck
-> [7 Nếu cần thì chuyển mentor/tech]
-> [8 Học viên nhận phản hồi]
```

| Bước | Actor | Input | Output | Thời gian/tần suất | Ghi chú |
|---|---|---|---|---|---|
| 1 | Học viên | Gặp vấn đề về bài tập/lịch/quyền/lỗi | Nhu cầu hỗ trợ | Cao vào deadline | Pain bắt đầu từ học viên |
| 2 | Học viên | Nội dung câu hỏi | Ticket tự do | 1-3 phút/ticket | Nội dung có thể thiếu ngữ cảnh |
| 3 | Hệ thống ticket | Ticket mới | Queue chung | Liên tục | Chưa có priority tốt |
| 4 | TA | Queue ticket | Ticket đã đọc | 2-5 phút/ticket | Mất công với ticket trùng lặp |
| 5 | TA | Nội dung ticket | Chủ đề/priority tạm thời | 1-2 phút/ticket | Dễ sai nếu quá tải |
| 6 | TA | Ticket + kiến thức khóa học | Câu trả lời | 3-7 phút/ticket | Bottleneck chính |
| 7 | TA/mentor/tech | Ticket cần escalate | Ticket được chuyển | Có thể chậm | Ticket khẩn cấp bị đọng lại |
| 8 | Học viên | Phản hồi | Tiếp tục học / hỏi lại | Có thể trễ 1-2 ngày | Ảnh hưởng tiến độ |

Bottleneck chính:

```text
TA phải đọc, phân loại và trả lời thủ công từng ticket, kể cả với ticket có nội dung trùng lặp. Khi queue tăng, ticket khẩn cấp bị lẫn với ticket thông thường.
```

## Future Workflow Bản Nhóm

```text
FUTURE STATE - workflow hỗ trợ triage ticket

[1 Học viên tạo ticket + chọn một số field cố định]
-> [2 Rule validate metadata: khóa, buổi, loại vấn đề nếu có]
-> [3 AI phân loại chủ đề: bài tập / deadline / attendance / quyền truy cập / lỗi kỹ thuật / khác]
-> [4 AI chấm priority và confidence]
-> [5 AI gom nhóm ticket trùng lặp]
-> [6 AI đề xuất reply template hoặc escalation path]
-> [7 TA review/approve/sửa/escalate]  <-- human boundary
-> [8 Học viên nhận phản hồi hoặc ticket được xử lý khẩn cấp]

Fallback:
- Confidence thấp -> đẩy vào queue TA đọc thủ công.
- Ticket có từ khóa lỗi nghiêm trọng/quyền truy cập/payment/privacy -> escalate, không auto reply.
- AI draft không có source -> TA không duyệt.
```

Before/after impact:

| Metric | Trước | Sau kỳ vọng | Ghi chú |
|---|---:|---:|---|
| Thời gian ticket khẩn cấp được nhận diện | 1-2 ngày | Dưới 2 giờ | Metric chính |
| Số ticket trùng lặp TA phải trả lời từng cái | Cao, chưa đo | Giảm 50-70% trong pilot | Cần validate bằng log ticket |
| Số bước thủ công của TA | Đọc, phân loại, trả lời, escalate | Review, approve, escalate | TA vẫn là người quyết định |
| Tỷ lệ ticket có category/priority | Chưa ổn định | 80%+ có label để TA lọc | Không tính ticket confidence thấp |
| Risk mới | Chậm do quá tải | AI phân loại sai / draft sai | Cần guardrail và human review |

## Problem Statement v0

| Field | Nội dung |
|---|---|
| **Actor** | TA/mentor phụ trách support học viên trong lớp hơn 1.000 học viên; học viên cần được hỗ trợ đúng lúc. |
| **Workflow** | Học viên tạo ticket -> ticket vào queue chung -> TA đọc từng ticket -> TA phân loại chủ đề/priority -> TA trả lời thủ công hoặc escalate. |
| **Bottleneck** | Bước TA đọc, phân loại và trả lời từng ticket giống nhau làm queue bị chậm; ticket khẩn cấp bị lẫn với ticket thông thường. |
| **Impact** | TA mất nhiều giờ cho câu hỏi lặp lại; ticket mới/khẩn cấp có thể bị trễ 1-2 ngày, làm học viên chậm tiến độ học tập. |
| **Success Metric** | Rút ngắn thời gian ticket khẩn cấp được nhận diện/chuyển xử lý xuống dưới 2 giờ; giảm số ticket trùng lặp phải trả lời thủ công. |
| **Boundary** | AI không tự động gửi câu trả lời cho ticket rủi ro cao; không tự cấp quyền/sửa điểm/thay đổi attendance; TA phải review và approve. |

---

# 04 - Rule / Workflow / Agent + Decision

## Ma Trận Độ Phù Hợp Với AI

Bài toán nằm ở ô:

```text
Độ mơ hồ cao + độ phức tạp vừa/cao.
```

Vì sao:

```text
Ticket là ngôn ngữ tự do, có nhiều cách hỏi khác nhau, có thể viết thiếu ngữ cảnh hoặc gom nhiều ý trong một ticket. Workflow có nhiều bước nhưng vẫn tuyến tính: nhận ticket -> phân loại -> gom nhóm -> draft -> TA review/escalate. AI cần hỗ trợ đọc hiểu ngôn ngữ và clustering, nhưng chưa cần agent tự lập kế hoạch phức tạp.
```

## So Sánh Rule / Workflow / Agent

| Mức | Phương án cho bài toán nhóm | Khi nào đủ | Rủi ro | Chọn? |
|---|---|---|---|---|
| **Rule** | Form ticket có dropdown, keyword routing, FAQ, macro reply | Đủ với câu hỏi rất rõ như deadline, link bài nộp, lỗi truy cập có keyword | Không hiểu được câu hỏi tự do, viết sai chính tả, ticket có nhiều ý | Dùng một phần, không đủ toàn bộ |
| **Workflow** | Rule lấy metadata -> AI classify/cluster/priority -> AI draft reply -> TA review/approve/escalate | Hợp khi cần xử lý nhiều ticket tự do nhưng vẫn có human boundary | AI phân loại sai, gom nhóm sai, draft sai nếu thiếu source | Chọn |
| **Agent** | Agent tự đọc ticket, hỏi thêm thông tin, truy cập LMS, sửa quyền, gửi reply, follow-up | Chỉ cần nếu hệ thống cần tự gọi nhiều tool và quyết định bước tiếp theo | Quá rộng, permission cao, rủi ro sai quyền/sai thông tin | Chưa chọn |

Mức chọn:

```text
Workflow.
```

Vì sao chọn:

```text
Workflow giải đúng bottleneck nhất: giảm công đọc-phân loại-gom nhóm-draft câu trả lời, nhưng vẫn để TA review nhằm đảm bảo chất lượng. Nó đủ nhỏ để pilot, có metric rõ và có rollback nếu AI sai.
```

Vì sao không chọn mức đơn giản hơn:

```text
Rule/dropdown/FAQ có ích nhưng không xử lý tốt câu hỏi tự do, ticket thiếu ngữ cảnh, viết khác nhau nhưng cùng một ý, hoặc ticket có nhiều vấn đề. Vì vậy chỉ dùng rule cho metadata và guardrail, không dùng làm solution duy nhất.
```

Vì sao không chọn Agent:

```text
Agent chưa cần thiết vì mục tiêu hiện tại không phải tự động xử lý tất cả ticket hay thay TA. Bài toán cần triage và gom nhóm trước, không cần AI tự sửa quyền, thay đổi attendance, gửi thông báo chính thức hay quyết định thay người thật.
```

## Problem Statement v1

| Field | Nội dung |
|---|---|
| **Actor** | TA/mentor support lớp hơn 1.000 học viên và học viên có ticket cần xử lý đúng lúc. |
| **Workflow** | Học viên tạo ticket -> rule lấy metadata -> AI classify chủ đề/priority/confidence -> AI cluster ticket trùng lặp -> AI draft reply/escalation suggestion -> TA review/approve/escalate. |
| **Bottleneck** | TA đang đọc, phân loại và gõ câu trả lời thủ công cho nhiều ticket lặp lại, làm ticket khẩn cấp bị đọng queue 1-2 ngày. |
| **Impact** | TA tốn nhiều giờ mỗi ngày vào câu hỏi lặp lại; học viên gặp lỗi khẩn cấp bị trễ tiến độ; chất lượng support giảm khi quy mô lớp tăng. |
| **Success Metric** | Trong pilot, ticket khẩn cấp được gắn priority/escalate trong dưới 2 giờ; giảm ít nhất 50% số ticket trùng lặp cần TA trả lời từng cái; giữ tỷ lệ AI label sai ticket khẩn cấp ở mức chấp nhận được qua review. |
| **Boundary** | AI chỉ phân loại, gom nhóm, đề xuất priority và draft reply. AI không tự động cấp quyền, sửa điểm, thay đổi attendance, gửi reply cho case rủi ro cao, hay đóng ticket nếu chưa có TA duyệt. |
| **AI intervention point** | Sau khi ticket được tạo và trước khi TA đọc queue: AI thêm label, priority, cluster và draft để TA xử lý nhanh hơn. |
| **Mức chọn** | Workflow. |
| **Rủi ro & người thật kiểm tra** | Rủi ro: phân loại sai ticket khẩn cấp, gom nhóm sai, draft câu trả lời thiếu source, leak thông tin cá nhân. Người kiểm tra: TA/mentor review queue, approve reply, escalate case khẩn cấp. |

## Final Decision

| Câu hỏi | Yes / Not Yet / No | Ghi chú |
|---|---|---|
| Actor và workflow đã rõ chưa? | Yes | Actor chính là TA/mentor và học viên raise ticket |
| Baseline và success metric đã đo được chưa? | Not Yet | Cần lấy log ticket 1 tuần cao điểm để chốt baseline |
| Có data/input đủ dùng chưa? | Not Yet | Cần ticket text, timestamp, category nếu có, status xử lý |
| Nếu AI sai, hậu quả có chấp nhận được không? | Yes, nếu có guardrail | Ticket rủi ro cao không auto reply, TA review bắt buộc |
| Có người review/owner vận hành không? | Yes | TA lead/mentor làm owner |
| Có cách non-AI đơn giản hơn không? | Yes, một phần | FAQ/dropdown/macro nên làm song song |

Decision:

```text
Go với pilot nhỏ, chưa Go production.
```

Lý do:

```text
Bài toán có actor, workflow, bottleneck và metric mục tiêu tương đối rõ. Tuy nhiên chưa nên xem là giải pháp đã chứng minh hiệu quả vì baseline ticket trùng lặp và độ chính xác phân loại chưa được validate. Nhóm chỉ Go với pilot nhỏ có TA review và có rollback.
```

Pilot nhỏ nhất:

```text
Lấy 1 tuần ticket gần deadline. Chạy bản workflow bán thủ công:
1. Export ticket text + timestamp + status.
2. AI gắn label chủ đề, priority, confidence.
3. AI gom nhóm ticket trùng lặp và draft reply mẫu cho từng cluster.
4. TA review 50-100 ticket đầu tiên.
5. Đo thời gian ticket khẩn cấp được nhận diện, tỷ lệ label sai, số cluster trùng lặp đúng, số reply draft dùng được.
```

Nếu Not Yet, cần validate gì trước:

```text
Cần đo baseline: số ticket/tuần, tỷ lệ ticket trùng lặp, thời gian phản hồi hiện tại, số ticket khẩn cấp bị trễ, và các chủ đề ticket phổ biến.
```

Nếu No-Go, nên làm gì thay AI:

```text
Làm form ticket có dropdown bắt buộc, FAQ theo top question, macro reply, rule keyword để escalate lỗi truy cập/lỗi kỹ thuật, và dashboard queue theo priority.
```
