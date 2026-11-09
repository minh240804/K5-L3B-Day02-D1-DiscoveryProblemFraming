# Báo cáo nhóm — Day 02 Discovery & Problem Framing

> Bản chung của nhóm, viết trên repo do nhóm trưởng fork. Không copy file này sang repo cá nhân.
> Template chi tiết và prompt mẫu: [docs/01-worksheet.md](../../docs/01-worksheet.md). Bài mẫu: [docs/02-deliverable-example.md](../../docs/02-deliverable-example.md).

## 1. Thông tin nhóm

- Tên nhóm: D1
- Thành viên: xem `TEAM.md`
- Candidate problem được chọn (1 câu): Khi nhận hàng trăm tin nhắn Zalo lớp, phụ huynh muốn 1 bản tóm tắt việc học/tiền bạc duy nhất. | Phụ huynh học sinh | Cuộn đọc tin tán gẫu để nhặt tin nhắn cô dặn (15') & dịch ảnh bài tập mờ (8')
- Quyết định cuối: Go / Not Yet / No-Go

---

## 2. Hội tụ nhóm (CP3)

### 2.1. Pitch

| # | Người đưa ra | Candidate (Job Story ngắn) | Actor | Bottleneck | Câu hỏi phản biện nhận được (ai hỏi) |
|---:|---|---|---|---|---|
| 1 | Hoàng Minh Diệp | Khi vừa họp xong, BA muốn có sẵn User Story + AC để kịp Sprint Planning. | BA phụ trách ghi nhận | Viết AC + edge cases mất 40' | Chất lượng AC đo như thế nào? Edge cases AI sinh ra có đúng business logic không? (Vũ Quang Minh) |
| 2 | Hoàng Minh Diệp | Khi họp xong, BA muốn gửi Meeting Minutes trong ngày để stakeholder xác nhận. | BA tổng hợp biên bản | Sắp xếp ghi chú + đối chiếu recording (30–60') | Nếu đã có Whisper/Notion AI thì giá trị thặng dư là gì? (Nguyễn Hoàng Gia An) |
| 3 | Hoàng Minh Diệp | Khi phát sinh logic cũ, BA/Dev Muốn tìm lại quyết định cũ để không họp lại từ đầu. | BA, Dev, QA | Tìm kiếm & đối chiếu thông tin từ nhiều nguồn (20–30') | Phân quyền truy cập dữ liệu (RBAC) xử lý thế nào? (Thành viên 4) |
| 4 | Vũ Quang Minh | Khi muốn đặt xe, người dùng muốn so sánh giá cước giữa nhiều app tiện lợi. | Người dùng đặt xe | Chuyển đổi giữa 3-4 app, nhập lại thông tin (10') | Có bị Grab/Gojek chặn API/Anti-scraping không? (Hoàng Minh Diệp) |
| 5 | Vũ Quang Minh | Khi tìm việc, ứng viên muốn đối chiếu JD với CV và mức lương nhanh chóng. | Ứng viên | Đọc & phân tích thủ công từng JD, so sánh năng lực (15-20') | Khác gì các bộ lọc từ khóa nâng cao của TopCV? (Nguyễn Hoàng Gia An) |
| 6 | Vũ Quang Minh | Khi quản lý tài chính, người dùng muốn tổng hợp chi tiêu từ ngân hàng & ví điện tử. | Người tiêu dùng | Đăng nhập từng app, chép thủ công lịch sử giao dịch (10') | Rủi ro bảo mật OTP/Banking API là cực cao, liệu người dùng dám cấp quyền? (Thành viên 4) |
| 7 | Nguyễn Hoàng Gia An | Khi nhận hàng trăm tin nhắn Zalo lớp, phụ huynh muốn 1 bản tóm tắt việc học/tiền bạc duy nhất. | Phụ huynh học sinh | Cuộn đọc tin tán gẫu để nhặt tin nhắn cô dặn (15') & dịch ảnh bài tập mờ (8') | Chữ viết tay của cô giáo mờ/xấu AI có bóc tách (OCR) chính xác không? (Hoàng Minh Diệp) |
| 8 | Nguyễn Hoàng Gia An | Khi onboard nhân sự, IT Support muốn máy tự động cài đặt ứng dụng theo vai trò. | IT Support | Tải file, gõ pass Admin, click thủ công từng bước (18') | Bài này chỉ cần PowerShell script / Intune MDM, có thực sự cần AI không? (Vũ Quang Minh) |
| 9 | Nguyễn Hoàng Gia An | Khi nghe điện thoại lạ đe dọa, người già muốn chặn giao dịch chuyển tiền hoảng loạn. | Người cao tuổi, Con cái | Bị lừa đảo thao túng tâm lý cô lập hoàn toàn (25') | App ngân hàng có can thiệp được vào cuộc gọi thoại riêng tư không (vi phạm quyền riêng tư)? (Hoàng Minh Diệp) |


### 2.2. Cluster


| Cluster | Các candidate | Pattern chung |
|---|---|---|
| **A: BA Operations** | Candidate #1, #2, #3 | Tổng hợp, trích xuất thông tin nghiệp vụ và kiến thức dự án từ tài liệu/cuộc họp un-structured. |
| **B: Consumer Utility** | Candidate #4, #5, #6 | Aggregator (tổng hợp dữ liệu đa nguồn) hỗ trợ người tiêu dùng ra quyết định (xe, việc làm, tài chính). |
| **C: Safety & Automation** | Candidate #7, #8, #9 | Tự động hóa tác vụ lặp lại, bóc tách dữ liệu thông báo và bảo vệ an toàn thông tin/tài sản cho người dùng. |


### 2.3. Opportunity Solution Tree rút gọn


```text
OUTCOME: Giảm thời gian xử lý thông tin lặp lại & tăng hiệu suất sinh hoạt/làm việc hàng ngày lên trên 70%
├── Opportunity A: Phụ huynh mất quá nhiều thời gian lọc tin rác Zalo để tìm dặn dò của cô giáo
│   ├── Solution Candidate 7: AI Parsing Zalo Chat + OCR bài tập viết tay -> Dashboard Action Items
├── Opportunity B: BA mất nhiều giờ soạn thảo AC & biên bản họp từ ghi chú thô
│   ├── Solution Candidate 1: AI Auto-drafting Story/AC & Edge Cases
│   └── Solution Candidate 2: AI Meeting Minutes Extractor
├── Opportunity C: IT Support tiêu tốn thời gian cài đặt máy tính thủ công cho nhân viên mới
│   └── Solution Candidate 8: Zero-touch Onboarding Script/Bot
└── Opportunity D: Người tiêu dùng mất thời gian chuyển đổi nhiều app để so sánh dữ liệu
    ├── Solution Candidate 4: Multi-app Ride Comparison
    └── Solution Candidate 6: Multi-bank Expense Aggregator
```


**Những ý đã gạch bỏ vì là solution đội lốt opportunity:**
- Xây dựng Chatbot RAG kiến thức dự án(Solution cho việc tìm quyết định cũ).
- Viết PowerShell Script tự cài phần mềm (Solution cho IT Onboarding).
- Tích hợp API ngân hàng để quét lịch sử giao dịch (Solution cho tổng hợp chi tiêu).


### 2.4. Chấm điểm shortlist (1–5)


| Candidate | Actor rõ | Quy trình rõ | Pain có bằng chứng | Impact đo được | Vừa sức lab | So sánh được No AI/Rule/Workflow/Agent | Nhóm hiểu domain | Tổng |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| 1. BA AC Generator | 4 | 5 | 4 | 4 | 4 | 4 | 4 | **29** |
| 2. BA Meeting Minutes | 4 | 4 | 4 | 3 | 5 | 4 | 4 | **28** |
| 3. Decision Finder (RAG) | 4 | 3 | 4 | 4 | 3 | 4 | 3 | **25** |
| 4. So sánh giá xe | 5 | 4 | 3 | 3 | 2 | 3 | 4 | **24** |
| 5. Matching Job & CV | 4 | 3 | 3 | 3 | 3 | 4 | 3 | **23** |
| 6. Quản lý chi tiêu | 4 | 4 | 4 | 3 | 2 | 3 | 3 | **23** |
| **7. Zalo Parent Assistant** | **5** | **5** | **5** | **5** | **4** | **5** | **5** | **34** |
| 8. IT Setup Automation | 4 | 5 | 3 | 4 | 4 | 2 (Rule đủ) | 4 | **26** |
| 9. Anti-Fraud Financial | 4 | 3 | 5 | 5 | 2 | 4 | 2 | **25** |


**Candidate được chọn:** **Candidate #7 - Zalo Parent Assistant (Tổng hợp thông báo & bài tập từ nhóm chat Zalo phụ huynh)**


**Vì sao chọn:**
1. **Pain point cực kỳ nhức nhối & phổ biến:** Phụ huynh nào cũng gặp tình trạng "ngợp" tin nhắn Zalo lớp học mỗi tối (100–200 tin/ngày/lớp).
2. **Quy trình & Bottleneck rõ ràng:** Mất 32 phút mỗi tối chỉ để cuộn màn hình, nhặt tin dặn dò và đọc ảnh chữ viết tay mờ.
3. **Phù hợp công nghệ (Feasibility & Value):** Kết hợp hoàn hảo giữa LLM (phân loại, tóm tắt) và OCR (đọc chữ viết tay), vừa sức triển khai trong khuôn khổ Lab nhưng đem lại impact cực cao.
4. **Phân biệt rõ mức độ AI:** Thể hiện rõ sự khác biệt giữa No AI (khóa chat), Rule (bộ lọc từ khóa đơn thuần) và AI Workflow (LLM + OCR).


**Vì sao loại các candidate còn lại:**
- *Candidate #8 (IT Setup):* No AI/Rule (PowerShell Script / MDM Intune) đã giải quyết 95% bài toán, đưa AI vào là over-engineering.
- *Candidate #4 & #6 (Giá xe, Chi tiêu):* Vướng rào cản kỹ thuật/bảo mật lớn (chống scraping API của Grab, bảo mật ngân hàng, OTP), feasibility thấp trong bài tập lab.
- *Candidate #9 (Anti-fraud):* Rất khó mô phỏng dữ liệu cuộc gọi thực tế và rào cản pháp lý/quyền riêng tư trên di động.
- *Candidate #1, #2, #3 (BA domain):* Tiềm năng tốt nhưng phạm vi hẹp hơn, người dùng cuối (Target Audience) không rộng lớn và cảm nhận pain trực quan bằng phụ huynh học sinh.

## 3. Kiểm chứng + research giải pháp đã có (CP4)

### 3.1. Assumption Map

| # | Giả định | Loại (Value / Usability / Feasibility / Viability) | Quan trọng (1–5) | Đã có bằng chứng (1–5) | Kiểm chứng trước? |
|---:|---|---|---:|---:|---|
| 1 | Phụ huynh khác cũng bị quá tải tin nhắn| Value | 5 | 5 | ✅ |
| 2 | Bước tốn thời gian nhất là đọc tất cả tin nhắn | Value | 5 | 5 | ✅ |
| 3 | Tool có đọc được trên Zalo | Feasibility | 5 |  | ✅ |
| 4 | Giáo viên chủ nhiệm sẵn sàng áp dụng giải pháp mới nếu không làm gia tăng khối lượng công việc tổng hợp bài nộp hay trả lời tin nhắn riêng | 4 | 3 | |
| 5 | Phụ huynh chấp nhận chuyển sang kênh thông báo phân luồng/1 chiều để tránh bỏ lỡ thông tin quan trọng Usability | 4 | 3 | |

Giả định nhóm kiểm chứng trong buổi này:
### 3.2. Kiểm chứng

Cách đã dùng: Phỏng vấn, Log

Nhóm phỏng vấn 2 Phụ Huynh quen biết.

Interview snapshot — người thứ 1:

| Trường | Nội dung |
|---|---|
| Người được hỏi | Chị H.T.Hương (Nhân viên kế toán, 2 con học tiểu học tại Đà Nẵng) |
| Câu nói đáng nhớ | "Mỗi tối về nhà, việc đầu tiên của t là ngồi học với con xong check nhóm zalo lớp nó .	Lắm hôm 99+ tin nhắn kh biết đọc từ đâu” |
| Lần gần nhất | Thứ Sáu tuần trước, viết update tháng, mất khoảng 2 tiếng |
| Workaround hiện tại | Chỉ đọc thông báo từ giáo viên, lướt qua hoặc bỏ qua mấy cái trao đổi lan man  |
| Mất bao lâu, bao lần | 20-30 phút buổi tối |
| Insight | Phụ huynh cần giải pháp lọc: Tách biệt hoàn toàn thông báo chính thức của GVCN khỏi luồng thảo luận phụ huynh  |
Tổng hợp:

| Nguồn | Số người / số mẫu | Tín hiệu xác nhận | Tín hiệu phản bác |
|---|---:|---|---|
| | | | |

Log: https://giaoduc.net.vn/nhung-cau-chuyen-cuoi-ra-nuoc-mat-khi-giao-vien-phu-huynh-tuong-tac-qua-zalo-post223479.gd

**Nhóm đã sửa problem thế nào sau kiểm chứng:**

### 3.3. Research giải pháp đã có

| Công cụ / case / pattern | Link | Giải bước nào trong quy trình? | Điểm mạnh | Khoảng trống / rủi ro | Bài học cho nhóm |
|---|---|---|---|---|---|
| | | | | | |
| | | | | | |
| | | | | | |

---

## 4. Quy trình trước/sau (CP5)

### 4.1. Quy trình hiện tại

Sơ đồ (ASCII, Mermaid hoặc link ảnh trong `report/assets/`):

```text

```

| Bước | Actor | Input | Output | Thời gian / tần suất | Ghi chú |
|---:|---|---|---|---|---|
| 1 | | | | | |
| 2 | | | | | |
| 3 | | | | | |
| 4 | | | | | |
| 5 | | | | | |

**Bottleneck chính:**

### 4.2. Quy trình tương lai

Ghi rõ bước nào **Rule**, bước nào **AI**, bước nào **con người**, **boundary** ở đâu, **phương án quay về** khi AI sai.

```text

```

### 4.3. Before / after

| Chỉ số | Trước | Sau (kỳ vọng) | Ghi chú |
|---|---:|---:|---|
| Số bước | | | |
| Tổng thời gian | | | |
| Số bước thủ công | | | |
| Bottleneck chính | | | |
| Rủi ro mới phát sinh | | | |

---

## 5. Problem Statement v0 (CP5)

| Trường | Nội dung |
|---|---|
| **Actor** | |
| **Quy trình** | |
| **Bottleneck** | |
| **Impact** | |
| **Success Metric** (baseline → target, cách đo) | |
| **Boundary** (AI không được làm gì; khi nào cần con người kiểm tra — HITL) | |

Phản biện nhận được (từ AI hoặc nhóm khác) và nhóm có đồng ý không:

-

---

## 6. Mức can thiệp AI (CP6)

### 6.1. Ma trận độ mơ hồ × độ phức tạp

Bài của nhóm nằm ở ô:

Vì sao:

### 6.2. So sánh 4 mức

| Mức | Phương án cho bài của nhóm | Đủ khi nào | Rủi ro | Chọn? |
|---|---|---|---|---|
| **No AI** (sửa quy trình) | | | | |
| **Rule** | | | | |
| **Workflow** | | | | |
| **Agent** | | | | |

**Mức chọn:**

**Vì sao không chọn mức đơn giản hơn:**

### 6.3. AI Canvas rút gọn

| Thành phần | Nội dung |
|---|---|
| **Prediction** — AI dự đoán / tạo ra gì? | |
| **Judgment** — con người cân nhắc, quyết định gì? | |
| **Action** — hành động cuối cùng là gì, ai làm? | |
| **Outcome** — đo kết quả bằng gì? | |
| **Input** — AI cần dữ liệu đầu vào gì mỗi lần chạy? Có sẵn không? | |
| **Feedback** — lấy phản hồi ở đâu để cải thiện? | |

### 6.4. Hai câu hỏi của Google PAIR

- Người dùng muốn **được hỗ trợ (augment)** hay **giao hẳn việc (automate)**? Bằng chứng:
- AI sai kiểu nào tệ hơn, **báo nhầm** hay **bỏ sót**? Vì sao, và thiết kế đã xử lý thế nào:

---

## 7. Problem Statement v1 + tiêu chí đánh giá (CP6)

| Trường | Nội dung |
|---|---|
| **Actor** | |
| **Quy trình** | |
| **Bottleneck** | |
| **Impact** | |
| **Success Metric** (baseline → target, cách đo) | |
| **Boundary** | |
| **AI intervention point** | |
| **Mức chọn** | No AI / Rule / Workflow / Agent |
| **Rủi ro & người kiểm tra** | |

**Thay đổi so với v0 và lý do:**

| Trường | v0 | v1 | Vì sao đổi |
|---|---|---|---|
| | | | |

**Tiêu chí đánh giá đầu ra của AI (3–5 tiêu chí):**

| # | Tiêu chí | Đạt khi | Không đạt khi |
|---:|---|---|---|
| 1 | | | |
| 2 | | | |
| 3 | | | |

---

## 8. Quyết định (CP6)

### 8.1. Bốn rủi ro

| Rủi ro | Câu hỏi | Mức độ rủi ro (Thấp = an toàn / TB / Cao = nguy hiểm) | Lý do / bằng chứng |
|---|---|---|---|
| **Value** | Người dùng có thật sự cần và sẽ dùng không? | | |
| **Usability** | Người dùng có dùng được, có hiểu và sửa được đầu ra của AI không? | | |
| **Feasibility** | Có đủ dữ liệu, công cụ, kỹ năng để làm không? | | |
| **Viability** | Có hợp chi phí, pháp lý, quy định tổ chức không? Ai vận hành? | | |

### 8.2. Kết luận

**Quyết định:** Go / Not Yet / No-Go

**Lý do:**

**Nếu Go — pilot nhỏ nhất:**

**Nếu Not Yet — cần kiểm chứng gì trước:**

**Nếu No-Go — nên làm gì thay AI:**

**Ngưỡng dừng** (nếu sau … mà … thì quay về …):

---

## 9. Hạn chế và hướng tiếp theo

-

## 10. Tài liệu tham khảo

-
