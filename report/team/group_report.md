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



| Công cụ / case | Link | Giải bước nào? | Điểm mạnh | Khoảng trống / rủi ro | Bài học |
|---|---|---|---|---|---|
| **Chế độ nhóm Zalo/Messenger 1 chiều** (GVCN khóa chat) | Feature có sẵn trên Zalo/Messenger | **Bước 1 & 2:** Ngăn tin nhắn rác ("vâng ạ", sticker) làm trôi dặn dò quan trọng từ GVCN | Có sẵn trên ứng dụng quen dùng, không tốn chi phí, phụ huynh nhận thông báo tức thì | Phụ huynh thắc mắc phải nhắn 1-on-1 khiến GVCN bị quá tải tin nhắn cá nhân; thiếu tính năng tự động nhắc lịch thi/bài tập | Giữ luồng thông báo 1 chiều chuẩn hóa, nhưng **cần có kênh/nút phản hồi (1-click confirmation & FAQ tự động)** để tránh gây quá tải cho GVCN |
| **Sổ liên lạc điện tử & App quản lý nhà trường** (eNetViet, SMAS, K12Online...) | Nền tảng chuyên dụng của nhà trường | **Bước 1–4:** Phân luồng thông báo chính thức, quản lý điểm số, lịch học và thu phí | Thông báo chính thống, bảo mật thông tin gia đình | Giao diện phức tạp, tính năng tương tác 2 chiều hạn chế; phụ huynh và giáo viên ngại cài thêm ứng dụng thứ 3 | **Không nên tự xây ứng dụng/mạng xã hội mới** bắt phụ huynh rời bỏ Zalo/Messenger; nên xây giải pháp nhẹ tích hợp trực tiếp |
| **Quy tắc ứng xử nhóm chat & Nhóm phụ huynh tự quản** (Tách nhóm có GVCN và nhóm tự do) | Thỏa thuận quy ước trong lớp | **Bước 2 & 3:** Phân loại mục đích sử dụng (nhóm thông tin chính vs nhóm thảo luận tự do) | Không tốn chi phí, tôn trọng không gian riêng của giáo viên | Phụ thuộc hoàn toàn vào ý thức cá nhân; dễ bị phá vỡ quy tắc khi có tranh luận gay gắt hoặc spam | Quy tắc bằng lời nói/văn bản là chưa đủ, **cần công cụ kỹ thuật tự động phân luồng** tin nhắn rác khỏi bài đăng chính |
| **Tính năng ghim tin nhắn & Bộ lọc thủ công Zalo** | Utility có sẵn trên Zalo | **Bước 3:** Phụ huynh tự ghim bài dặn dò, tắt thông báo nhóm phụ huynh riêng | Phụ huynh chủ động quản lý thiết bị cá nhân | Vẫn tốn thời gian lội tin nhắn thủ công; không giải quyết tận gốc nguyên nhân gây nổ thông báo | Cần một **bộ lọc thông minh (Notification Filter)** giúp tự động trích xuất & ghim dặn dò/lịch thi mà phụ huynh không phải lội tin nhắn |

**Kết luận research:**

```text
Phần lớn các giải pháp hiện tại (khóa nhóm 1 chiều hoặc dùng App nhà trường) đều gặp nghịch lý: hoặc làm quá tải tin nhắn riêng của GVCN, hoặc tạo rào cản thao tác vì phụ huynh ngại cài app mới.
Hướng hợp lý: Không tự xây ứng dụng/mạng xã hội độc lập.
Giải pháp tối ưu: Xây dựng Bộ lọc thông báo tự động (Notification Filter Extension / Chatbot Assistant) chạy trực tiếp trên Zalo/Messenger → Tự động ghim dặn dò/lịch thi + Nút xác nhận 1-click "Đã đọc" + Trả lời tự động câu hỏi thường gặp (FAQ) cho GVCN.
```

## 4. Quy trình trước/sau (CP5)

### 4.1. Quy trình hiện tại

Sơ đồ (ASCII, Mermaid hoặc link ảnh trong `report/assets/`):

```text

```

## 4.1. Quy trình hiện tại 

| Bước | Actor | Input | Output | Thời gian / tần suất | Ghi chú |
|---:|---|---|---|---|---|
| 1 | Phụ huynh | Điện thoại, các nhóm Zalo của lớp | Mở và truy cập 3–5 nhóm Zalo liên quan | Mỗi tối, hằng ngày | Bao gồm nhóm lớp chính, nhóm bán trú, nhóm tiếng Anh liên kết... |
| 2 | Phụ huynh | Hàng loạt tin nhắn trong các nhóm | Lọc được những tin nhắn có khả năng chứa thông tin quan trọng | Khoảng 10 phút/lần | **Bottleneck chính:** phải đọc và bỏ qua nhiều tin nhắn trò chuyện, cảm ơn, sticker... bằng mắt. |
| 3 | Phụ huynh | Tin nhắn văn bản, ảnh chụp giáo án viết tay | Thông tin bài tập, lịch kiểm tra, lời nhắc của giáo viên | Mỗi tối, hằng ngày | Thông tin phân tán ở nhiều tin nhắn và định dạng khác nhau, khó tổng hợp đầy đủ. |
| 4 | Phụ huynh | Thông tin vừa tìm được | Ghi nhớ hoặc ghi lại công việc vào giấy / ứng dụng ghi chú cá nhân | Mỗi tối, hằng ngày | Phụ huynh phải tự chuyển thông tin thành các việc cần làm, dễ quên hoặc bỏ sót. |
| 5 | Phụ huynh | Tin nhắn đóng tiền, số tài khoản, cú pháp chuyển khoản | Thực hiện chuyển khoản học phí hoặc quỹ lớp | Khi có thông báo thu tiền | Phải tìm lại đúng thông tin tài khoản và nội dung chuyển khoản trong lịch sử tin nhắn. |

**Bottleneck chính:** Bước 2 – Phụ huynh phải tự lọc lượng lớn tin nhắn không liên quan trong 3–5 nhóm Zalo để tìm thông tin quan trọng. Công đoạn này mất khoảng 10 phút và tạo thêm gánh nặng trước khi phụ huynh có thể tổng hợp bài tập, lịch kiểm tra và các khoản cần đóng.

## 4.2. Quy trình tương lai

```text
[1. Giáo viên gửi thông tin lên Zalo / Chatbot]
                  |
                  v
[2. Rule: Kiểm tra tin nhắn có được giáo viên
gắn thẻ bot hoặc gửi vào chatbot hay không]
                  |
                  v
[3. AI: Tiếp nhận và xử lý dữ liệu]
    - OCR ảnh giáo án, thông báo chuyển khoản
    - Speech-to-Text với ghi âm
    - LLM trích xuất bài tập, lịch kiểm tra,
      hạn nộp và thông tin học phí
                  |
                  v
[4. Rule: Kiểm tra định dạng, trường dữ liệu,
trùng lặp và mức độ tin cậy]
                  |
          +-------+-------+
          |               |
     Đủ tin cậy       Thiếu / không chắc chắn
          |               |
          v               v
 [5. Tổng hợp thông tin] [Giáo viên xác nhận
          |               hoặc chỉnh sửa]
          |               |
          +-------<-------+
          |
          v
[6. Bot gửi thông tin riêng cho từng phụ huynh]
                  |
                  v
[7. Phụ huynh kiểm tra và thực hiện công việc]
                  |
                  v
       [Hoàn tất / Phản hồi]
```

### Phân định trách nhiệm và boundary

| Thành phần | Loại | Trách nhiệm |
|---|---|---|
| Tiếp nhận thông tin được giáo viên gửi hoặc gắn thẻ | Rule | Chỉ xử lý những nội dung được chủ động gửi cho bot, tránh tự động thu thập toàn bộ hội thoại riêng tư. |
| OCR, Speech-to-Text | AI | Chuyển ảnh và ghi âm thành dữ liệu văn bản để xử lý. |
| Trích xuất và phân loại thông tin | AI | Nhận diện bài tập, lịch kiểm tra, hạn nộp, thông tin học phí và các thông báo quan trọng. |
| Kiểm tra dữ liệu bắt buộc, trùng lặp, mức độ tin cậy | Rule | Kiểm tra cấu trúc, trường dữ liệu thiếu và các trường hợp cần xác nhận. |
| Xác nhận thông tin không chắc chắn | Con người | Giáo viên kiểm tra và chỉnh sửa trước khi thông tin được gửi đi. |
| Tổng hợp và gửi thông báo | Rule + AI | Rule xác định người nhận và thời điểm gửi; AI hỗ trợ tạo nội dung tóm tắt dễ đọc. |
| Kiểm tra và thực hiện công việc | Con người | Phụ huynh kiểm tra thông báo, chuẩn bị bài tập hoặc tự thực hiện chuyển khoản. |

**Boundary – Ranh giới giữa AI và con người:**

- AI chịu trách nhiệm đọc, phân loại, trích xuất và tổng hợp thông tin.
- Giáo viên vẫn là người chịu trách nhiệm xác nhận những thông tin quan trọng hoặc có độ tin cậy thấp.
- Phụ huynh là người quyết định và thực hiện hành động cuối cùng, đặc biệt đối với việc chuyển khoản.
- Hệ thống không tự suy đoán thông tin còn thiếu, chẳng hạn như số tài khoản, số tiền hoặc hạn nộp.

**Phương án quay về khi AI sai (Fallback):**

1. Nếu OCR hoặc trích xuất thất bại: thông báo cho giáo viên và yêu cầu gửi lại ảnh rõ hơn hoặc nhập nội dung bằng văn bản.
2. Nếu thông tin có độ tin cậy thấp hoặc thiếu dữ liệu quan trọng: chuyển cho giáo viên xác nhận, không tự động gửi thông tin chưa được xác thực.
3. Nếu chatbot gặp sự cố: giáo viên tiếp tục gửi thông báo qua nhóm Zalo như quy trình hiện tại.
4. Nếu phụ huynh phát hiện thông tin sai: có thể đối chiếu với tin nhắn gốc và báo lại giáo viên để chỉnh sửa.

## 4.3. Before / After

| Chỉ số | Trước | Sau (kỳ vọng) | Ghi chú |
|---|---:|---:|---|
| Số bước | 5 bước | 7 bước trong quy trình hệ thống | Quy trình mới có thêm các bước xử lý tự động và kiểm tra độ tin cậy. |
| Tổng thời gian | Khoảng 32 phút / buổi tối | Dưới 2 phút / buổi tối | Mục tiêu là thời gian phụ huynh cần để cập nhật và kiểm tra thông tin, không tính thời gian xử lý nền của hệ thống. |
| Số bước thủ công | 5 bước | 1–2 bước chính | Phụ huynh chủ yếu kiểm tra thông báo và thực hiện công việc; giáo viên vẫn gửi và xác nhận thông tin khi cần. |
| Bottleneck chính | Lọc thủ công hàng loạt tin nhắn, khoảng 10 phút | Chờ giáo viên xác nhận thông tin AI không chắc chắn | Đây là bottleneck mới cần theo dõi và đo lường sau khi triển khai. |
| Rủi ro mới phát sinh | Bỏ sót thông tin, quên lịch hoặc chậm đóng tiền | AI đọc sai chữ viết tay, trích xuất sai ngày / số tiền / tài khoản, gửi thiếu hoặc nhầm thông tin | Cần cơ chế xác nhận của giáo viên, đối chiếu tin nhắn gốc và fallback về Zalo. |

**Lưu ý khi trình bày:** Mốc 32 phút → dưới 2 phút và tỷ lệ bỏ sót 15–20% → 0% là các mục tiêu kỳ vọng nhóm đã đặt ra, chưa phải kết quả đã được kiểm chứng. Số bước của quy trình tương lai cũng phụ thuộc vào cách nhóm định nghĩa một bước nghiệp vụ; 7 bước ở đây tính cả các nhánh xử lý lỗi và xác nhận.

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

Bài của nhóm nằm ở ô: **Độ mơ hồ trung bình × Độ phức tạp trung bình (Medium Ambiguity × Medium Complexity)**

**Vì sao:**
- **Độ mơ hồ (Medium Ambiguity):** Tin nhắn trong nhóm chat phụ huynh hoàn toàn là ngôn ngữ tự nhiên không có cấu trúc cố định (tin dặn dò, câu hỏi, câu cảm ơn, sticker, thảo luận ngoài lề). AI cần hiểu ngữ cảnh để phân biệt chính xác đâu là "dặn dò/lịch thi/khoản thu" và đâu là "tin nhắn rác/trò chuyện".
- **Độ phức tạp (Medium Complexity):** Quy trình gồm nhiều bước liên hoàn (nhận luồng tin nhắn → phân loại & trích xuất dữ liệu → soạn nháp bản tóm tắt/lịch nhắc → trình GVCN/Phụ huynh duyệt → phát thông báo ghim & cập nhật lịch), nhưng chưa đến mức cần một hệ thống tự động hoàn toàn không có con người kiểm soát.

---

### 6.2. So sánh 4 mức

| Mức | Phương án cho bài của nhóm | Đủ khi nào | Rủi ro | Chọn? |
|---|---|---|---|---|
| **No AI** (sửa quy trình) | Thỏa thuận quy tắc lớp: Khóa chat 1 chiều, GVCN tự ghim bài, phụ huynh tự tắt thông báo. | Phụ huynh 100% tuân thủ quy tắc; GVCN có đủ thời gian nhắn tin trả lời riêng 1-on-1 cho từng phụ huynh. | Quy tắc dễ bị phá vỡ khi có vụ việc nóng; GVCN bị quá tải tin nhắn riêng. | ❌ |
| **Rule** | Dùng từ khóa cố định (`#thongbao`, `lịch thi`, `nộp tiền`) hoặc Regex để lọc tin nhắn. | Tất cả thông báo của GVCN đều soạn theo đúng cú pháp mẫu và chứa từ khóa cố định. | Bỏ sót các dặn dò viết tự nhiên không chứa từ khóa; báo nhầm khi phụ huynh thảo luận có chứa từ khóa. | ❌ *(Chỉ dùng làm trigger)* |
| **Workflow** *(Rule + AI + Human)* | Rule bắt trigger tin nhắn → AI (LLM) phân loại, trích xuất sự kiện/dặn dò & soạn nháp Tóm tắt → Con người (GVCN/Phụ huynh) duyệt 1-click → Tự động tạo sự kiện lịch & phát thông báo. | Cần xử lý ngôn ngữ tự nhiên linh hoạt nhưng bắt buộc đảm bảo 100% độ chính xác của thông tin dặn dò. | Cần giao diện duyệt nhanh (1-click) để không làm chậm luồng truyền tin. | ✅ **CHỌN** |
| **Agent** | AI tự động quản lý nhóm: Tự xóa tin nhắn rác, tự động trả lời phụ huynh, tự ra thông báo mới mà không cần duyệt. | AI có độ tin cậy 100% và được ủy quyền đại diện cho GVCN. | AI trả lời sai thông tin nhạy cảm (quỹ lớp, lịch thi); tự can thiệp gây bức xúc hoặc vi phạm riêng tư. | ❌ |

**Mức chọn:** **Workflow (Rule + AI + Human-in-the-loop)**

**Vì sao không chọn mức đơn giản hơn (No AI / Rule):**
- **Rule đơn thuần** thất bại vì tin nhắn trong group chat hoàn toàn là văn bản tự do. Nếu GVCN nhắn *"Mai các con nhớ mang kéo thủ công nhé"* mà không dùng từ khóa `#thongbao`, Rule sẽ bỏ sót hoàn toàn.
- **No AI** (chỉ khóa chat 1 chiều bằng quy trình) sẽ đẩy toàn bộ thắc mắc của phụ huynh sang tin nhắn riêng 1-on-1, khiến GVCN quá tải công việc trả lời lặp đi lặp lại.
---

### 6.3. AI Canvas rút gọn

| Thành phần | Nội dung |
|---|---|
| **Prediction** — AI dự đoán / tạo ra gì? | **1.** Phân loại tin nhắn (Thông báo/Dặn dò vs. Tin nhắn rác/Thảo luận).<br>**2.** Trích xuất thông tin có cấu trúc (Thời gian, Môn học, Nhiệm vụ cần làm).<br>**3.** Soạn nháp bản Tóm tắt ngắn gọn và câu trả lời FAQ cho GVCN. |
| **Judgment** — con người cân nhắc, quyết định gì? | **GVCN / Phụ huynh:** Xát nhận bản tóm tắt/lịch nhắc AI soạn nháp đã chuẩn xác chưa (1-click Approve/Edit) trước khi cập nhật vào bảng tin chung. |
| **Action** — hành động cuối cùng là gì, ai làm? | Hệ thống tự động tạo **Thẻ thông báo ghim**, tự động thêm **Sự kiện vào Lịch (Calendar Event)** và gửi nút xác nhận 1-click **"Đã đọc/Đã nắm"** cho phụ huynh. |
| **Outcome** — đo kết quả bằng gì? | **1.** Giảm thời gian lội tin nhắn của phụ huynh từ 30 phút xuống < 3 phút/ngày.<br>**2.** Giảm 80% tin nhắn rác xác nhận ("vâng ạ", sticker).<br>**3.** 0% phụ huynh bị bỏ lỡ lịch thi/bài tập quan trọng. |
| **Input** — AI cần dữ liệu đầu vào gì mỗi lần chạy? Có sẵn không? | **Input:** Luồng tin nhắn văn bản từ nhóm chat (Zalo/Messenger), dữ liệu thời gian thực. Có sẵn 100% từ luồng chat của lớp. |
| **Feedback** — lấy phản hồi ở đâu để cải thiện? | Phản hồi 1-click từ người dùng: Nút **"Báo sai thông tin"**, **"Chỉnh sửa tóm tắt"** hoặc **"Đánh dấu là tin rác"** để cập nhật prompt/few-shot examples cho AI. |

---

### 6.4. Hai câu hỏi của Google PAIR

- **Người dùng muốn được hỗ trợ (augment) hay giao hẳn việc (automate)? Bằng chứng:**
  - **Người dùng muốn được HỖ TRỢ (Augment).**
  - **Bằng chứng:** Kết quả kiểm chứng (CP4) cho thấy thông báo học tập của con trẻ gắn liền với trách nhiệm và kết quả học tập thực tế. Phụ huynh và GVCN không tin tưởng để AI tự động giao tiếp hay tự ra quyết định thay mình. Họ cần AI **soạn nháp tóm tắt và trích xuất thông tin**, còn con người giữ quyền duyệt cuối cùng (Human-in-the-loop) để đảm bảo độ chính xác 100%.

- **AI sai kiểu nào tệ hơn, báo nhầm (False Positive) hay bỏ sót (False Negative)? Vì sao, và thiết kế đã xử lý thế nào:**
  - **BỎ SÓT (False Negative) TỆ HƠN RẤT NHIỀU.**
  - **Vì sao:** Nếu AI bỏ sót một dặn dò quan trọng (ví dụ: lịch thi giữa kỳ, đổi lịch học, chuẩn bị dụng cụ học tập), phụ huynh sẽ không nhận được nhắc nhở → con bị phạt hoặc thiếu chuẩn bị. Ngược lại, nếu báo nhầm (chuyển một thảo luận thường thành thông báo nháp), phụ huynh chỉ tốn 2 giây để lướt qua bỏ qua.
  - **Thiết kế đã xử lý:** Đặt ngưỡng nhạy (Sensitivity Threshold) của AI nghiêng hẳn về **Recall** (ưu tiên trích xuất thà thừa còn hơn bỏ sót). Tất cả các nội dung có dấu hiệu là dặn dò đều được trích xuất nháp và hiển thị nổi bật cho GVCN/Phụ huynh xác nhận 1-click, đảm bảo tỷ lệ bỏ sót = 0%.

---

## 7. Problem Statement v1 + tiêu chí đánh giá (CP6)

### 7.1. Bảng Problem Statement v1

| Trường | Nội dung |
|---|---|
| **Actor** | Phụ huynh có con học Tiểu học/THCS và Giáo viên chủ nhiệm (GVCN). |
| **Quy trình** | Nhà trường/GVCN phát thông báo vào nhóm chat lớp (Zalo/Messenger) → Phụ huynh đọc, nhắn tin xác nhận ("vâng ạ"), đặt câu hỏi và thảo luận → GVCN giải đáp thắc mắc. |
| **Bottleneck** | Tin nhắn phản hồi hàng loạt ("vâng ạ", sticker) và thảo luận lan man làm trôi dặn dò chính; phụ huynh phải lội hàng trăm tin nhắn; GVCN bị ngập trong thắc mắc trùng lặp. |
| **Impact** | Phụ huynh căng thẳng, bỏ lỡ lịch thi/bài tập của con (mất 20–30 phút/ngày lội tin); GVCN quá tải tâm lý và mệt mỏi ngoài giờ làm việc. |
| **Success Metric** (baseline → target, cách đo) | - **Baseline:** Mất 20–30 phút/ngày lội tin; 70% phụ huynh stress; lỡ 1–2 dặn dò/tháng.<br>- **Target:** Giảm thời gian lội tin xuống < 3 phút/ngày; 0% trôi dặn dò; giảm 80% tin nhắn rác xác nhận.<br>- **Cách đo:** Log thời gian tương tác trên ứng dụng/bộ lọc & khảo sát phụ huynh sau 1 tháng sử dụng. |
| **Boundary** | Không thay thế ứng dụng quản lý học bạ/điểm số chính thức của nhà trường; không can thiệp vào cuộc trò chuyện cá nhân ngoài mục đích học tập. |
| **AI intervention point** | Phân loại tin nhắn quan trọng vs. tin rác + Trích xuất & tóm tắt tự động dặn dò/lịch thi + Soạn nháp câu trả lời FAQ cho GVCN. |
| **Mức chọn** | **Workflow (Rule + AI + Human-in-the-loop)** |
| **Rủi ro & người kiểm tra** | **Rủi ro:** AI hiểu sai ngữ cảnh hoặc trích xuất sai ngày/giờ.<br>**Người kiểm tra:** GVCN và Phụ huynh duyệt 1-click trước khi lưu/ghim thông báo. |

---

### 7.2. Thay đổi so với v0 và lý do

| Trường | v0 | v1 | Vì sao đổi |
|---|---|---|---|
| **Actor** | Chỉ có Phụ huynh. | Phụ huynh + Giáo viên chủ nhiệm (GVCN). | Kiểm chứng cho thấy GVCN cũng là nạn nhân chịu quá tải tin nhắn và là người nắm nguồn tạo thông tin chính. |
| **Scope Giải pháp** | Xây dựng ứng dụng mạng xã hội học tập độc lập hoàn toàn mới. | Xây dựng Bộ lọc thông báo tự động (Notification Filter Extension / Bot Assistant) tích hợp trên Zalo/Messenger. | Phụ huynh và giáo viên ngại cài thêm app mới; tích hợp trực tiếp giúp loại bỏ rào cản thói quen sử dụng. |
| **Mức can thiệp AI** | Autonomous Agent (AI tự động quản lý và trả lời trong nhóm). | Workflow (Rule + AI + Human-in-the-loop). | Người dùng cần sự an toàn tuyệt đối với thông tin học tập của con, không chấp nhận rủi ro AI tự ra quyết định. |
| **Success Metric** | Số lượng người dùng tải và đăng ký app mới. | Thời gian lội tin nhắn giảm (30p → 3p) & Tỷ lệ trôi dặn dò quan trọng = 0%. | Tập trung giải quyết trực tiếp giá trị cốt lõi (Value & Efficiency) thay vì chạy theo chỉ số tăng trưởng ảo. |

---

### 7.3. Tiêu chí đánh giá đầu ra của AI (3–5 tiêu chí)

| # | Tiêu chí | Đạt khi | Không đạt khi |
|---:|---|---|---|
| **1** | **Độ chính xác trích xuất thực thể** | Trích xuất đúng các trường: Ngày/Giờ, Môn học, Nhiệm vụ cần làm, Khoản phí từ tin nhắn của GVCN. | Trích xuất sai ngày/giờ, nhầm lẫn giữa lịch học và lịch thi, hoặc bỏ sót thông tin khoản thu. |
| **2** | **Tỷ lệ bỏ lỡ thông báo ** | các tin nhắn dặn dò/thông báo chính thức từ GVCN đều được gắn nhãn và trích xuất thành công vào bản nháp. | Bỏ sót tin nhắn có chứa dặn dò của GVCN, khiến thông báo không được đưa vào luồng tóm tắt. |
| **3** | **Độ ngắn gọn của bản tóm tắt** | Bản tóm tắt ngắn gọn dưới 50 từ, định dạng danh sách kèm nút bấm hành động rõ ràng. | Bản tóm tắt dài dòng, giữ nguyên các câu từ thừa mứa ("vâng ạ", chúc) hoặc thiếu hướng dẫn hành động. |


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
