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
| **Actor** | Phụ huynh học sinh là người tiếp nhận thông tin, giáo viên chủ nhiệm là người phát tin, con cái sẽ bị phạt nếu phụ huynh quên hoặc bỏ lỡ thông tin quan trọng |
| **Quy trình** | 1. (1 phút) Mở Zalo, duyệt qua 3–5 nhóm lớp (Lớp chính, Bán trú, Tiếng Anh liên kết...) <br> 2. (15 phút) Lướt qua hàng loạt tin tán gẫu, icon cảm ơn, sticker thả tim. <br> 3. (8 phút) Tìm bài tập về nhà nằm rải rác ở tin nhắn văn bản hoặc ảnh chụp đề cương viết tay. <br> 4. (5 phút) Tự nhớ hoặc chép tay ra giấy/app ghi chú cá nhân. <br> 5. (1 phút) Tìm thông tin số tài khoản và cú pháp để chuyển tiền học/tiền quỹ. |
| **Bottleneck** | **Bước 2 (Mất 15 phút):** Lọc tin rác thủ công bằng mắt trên luồng chat phân mảnh. |
| **Impact** | Con bị phạt/thiếu đồ dùng học tập; đóng muộn tiền học; phụ huynh căng thẳng, trút giận lên con cái sau ngày làm việc kiệt sức. |
| **Success Metric** (baseline → target, cách đo) | Thời gian cập nhật việc học: cần về dưới 6 phút/tối. <br> Tỷ lệ bỏ sót việc cần làm: về 0%. |
| **Boundary** (AI không được làm gì; khi nào cần con người kiểm tra — HITL) | 1. AI không tự động xác thực kế toán <br> 2. AI không tự phát hành chế tài / Công khai danh sách học sinh nợ học phí <br> 3. AI không tự suy diễn dữ liệu mập mờ <br> 4. AI không lưu trữ/chia sẻ hình ảnh biên lai, thông tin ngân hàng cá nhân trái phép |

Phản biện nhận được (từ AI hoặc nhóm khác) và nhóm có đồng ý không:

- **Phản biện 1:** Giáo viên là người phải bỏ công nhập/duyệt dữ liệu vào Bot, nhưng Phụ huynh lại là người hưởng lợi. Giáo viên vốn đã cực kỳ quá tải, tại sao họ phải tốn thêm thao tác để làm hài lòng phụ huynh nếu hệ thống không giải quyết nỗi đau của chính họ?
    + Nhóm đồng ý, sản phẩm sẽ thất bại ở khâu triển khai (Onboarding) nếu không có động lực cho người phát tin. 
    + Nhóm bổ sung giá trị trực tiếp cho Giáo viên: Bot AI không chỉ tóm tắt cho phụ huynh, mà còn tự động bóc tách biên lai, lập danh sách thu chi và tự động gửi tin nhắn nhắc nộp tiền 1-1. Giáo viên dùng hệ thống vì nó giúp chính họ tiết kiệm 2–3 tiếng làm sổ sách thủ công mỗi tuần. 
- **Phản biện 2:** Nếu các phần mềm Sổ liên lạc điện tử hiện có (vnEdu, eNetViet) hoặc chính Zalo cập nhật một tính năng tóm tắt thông báo đơn giản, dự án của bạn sẽ bị đè bẹp như thế nào?
    + Nhóm đồng ý, tính năng tóm tắt bằng AI thuần túy không phải là rào cản công nghệ bền vững. 
    + Yếu tố phòng thủ của sản phẩm nằm ở khả năng xử lý dữ liệu phi cấu trúc thực tế tại Việt Nam (đề cương chép tay mờ, teencode, file ghi âm giọng địa phương) kết hợp với luồng đối soát tài chính tự động (OCR biên lai ngân hàng). Hơn nữa, định vị dự án không phải là một ứng dụng độc lập cạnh tranh với các 'ông lớn', mà là một mô-đun tích hợp (Plugin/White-label API) có thể bán lại cho chính các hệ thống Sổ liên lạc điện tử hiện hữu.

---

## 6. Mức can thiệp AI (CP6)

### 6.1. Ma trận độ mơ hồ × độ phức tạp

Bài của nhóm nằm ở ô: **Độ mơ hồ trung bình × Độ phức tạp trung bình (Medium Ambiguity × Medium Complexity)**

**Vì sao:**
- **Độ mơ hồ (Medium Ambiguity):** Dữ liệu đầu vào từ GVCN rất đa dạng và không có cấu trúc cố định: văn bản gõ vội, ảnh chụp đề cương viết tay, file ghi âm dặn dò, ảnh chụp bill chuyển khoản từ phụ huynh. AI cần phối hợp LLM + OCR để đọc hiểu ngữ cảnh và trích xuất đúng thực thể (bài tập, lịch thi, khoản phí, số tiền).
- **Độ phức tạp (Medium Complexity):** Quy trình gồm nhiều bước liên hoàn (Trigger tag `@BOT` / gửi ảnh bill → OCR & LLM phân tích, trích xuất dữ liệu → Soạn nháp bản tóm tắt / Cập nhật bảng đối soát quỹ → Gửi bản tóm tắt cá nhân hóa cho phụ huynh trong chat riêng với BOT), có sự xác nhận của con người (Human-in-the-loop).

---

### 6.2. So sánh 4 mức

| Mức | Phương án cho bài của nhóm | Đủ khi nào | Rủi ro | Chọn? |
|---|---|---|---|---|
| **No AI** (sửa quy trình) | GVCN bật cài đặt Zalo "chỉ Admin nhắn tin" (tạo 1 kênh thông báo 1 chiều + 1 nhóm thảo luận riêng). | Phụ huynh 100% tuân thủ quy tắc; GVCN có thời gian dò tay từng ảnh bill chuyển tiền và phụ huynh chấp nhận tự lội kênh 1 chiều. | Phụ huynh vẫn phải tự lội kênh thông báo; GVCN quá tải thủ công đối soát hàng chục ảnh chuyển khoản. | ❌ |
| **Rule** | Dùng từ khóa/Hashtag cố định (`#thongbao`, `#noptien`, cú pháp chuyển khoản cố định). | Tất cả GVCN và phụ huynh gõ đúng 100% cú pháp mẫu không sai một ký tự. | Phụ huynh ghi sai cú pháp chuyển khoản sẽ bị bỏ sót; không thể dùng Rule để đọc ảnh đề cương viết tay hay file ghi âm. | ❌ |
| **Workflow** *(Rule + LLM/OCR + Human)* | Tag `@BOT` trigger → LLM + OCR xử lý văn bản/ảnh bill/đề cương viết tay → Trích xuất danh sách công việc & đối soát quỹ → Gửi bản tóm tắt riêng cho từng phụ huynh (có bước duyệt nháp). | Cần xử lý linh hoạt dữ liệu đa phương tiện (văn bản, hình ảnh, âm thanh) nhưng đảm bảo 100% độ chính xác nhờ con người duyệt. | Cần tối ưu thời gian xử lý OCR và giao diện duyệt nháp 1-click cho GVCN/Phụ huynh. | ✅ **CHỌN** |
| **Agent** | AI tự động quản lý hoàn toàn: Tự duyệt tiền vào tài khoản ngân hàng thật, tự động nhắn tin nhắc nhở/phạt học sinh mà không qua con người. | AI có độ tin cậy tuyệt đối 100% và được ủy quyền pháp lý đại diện nhà trường. | Rủi ro cực lớn nếu OCR đọc nhầm số tiền chuyển khoản hoặc nhầm lịch thi gây hậu quả trực tiếp cho học sinh. | ❌ |

**Mức chọn:** **Workflow (Rule + LLM/OCR + Human-in-the-loop)**

**Vì sao không chọn mức đơn giản hơn (No AI / Rule):**
- **Rule đơn thuần** hoàn toàn bất lực trước ảnh chụp đề cương viết tay, file ghi âm dặn dò hoặc ảnh chụp bill chuyển khoản bị ghi sai cú pháp.
- **No AI** chỉ giải quyết được việc khóa nhóm chat chứ không giúp phụ huynh giảm thời gian tổng hợp việc học từ 32 phút xuống 2 phút, đồng thời tạo thêm gánh nặng thủ công cho GVCN khi kiểm tra tiền quỹ.

---

### 6.3. AI Canvas rút gọn

| Thành phần | Nội dung |
|---|---|
| **Prediction** — AI dự đoán / tạo ra gì? | **1.** OCR trích xuất dữ liệu từ ảnh bill chuyển tiền (Tên, Số tiền, Cú pháp).<br>**2.** OCR/LLM trích xuất bài tập, lịch thi từ ảnh đề cương viết tay, file ghi âm và văn bản dặn dò.<br>**3.** Tạo bản tóm tắt duy nhất (Single Digest) chứa danh sách việc cần làm (Action items) cá nhân hóa cho từng phụ huynh. |
| **Judgment** — con người cân nhắc, quyết định gì? | **GVCN:** Duyệt bảng đối soát nộp quỹ và kiểm tra bản tóm tắt dặn dò chung trước khi phát hành.<br>**Phụ huynh:** Duyệt checklist việc cần làm của con vào cuối ngày trên chat riêng với BOT. |
| **Action** — hành động cuối cùng là gì, ai làm? | Hệ thống tự động cập nhật danh sách nộp tiền lớp và gửi **Bản tóm tắt duy nhất (chiều tối)** kèm nút 1-click "Hoàn thành" trực tiếp vào chat riêng của từng phụ huynh với BOT. |
| **Outcome** — đo kết quả bằng gì? | **1.** Thời gian phụ huynh cập nhật việc học: **32 phút/tối → dưới 2 phút/tối**.<br>**2.** Tỷ lệ bỏ sót việc cần làm (action items): **15–20% → 0%**.<br>**3.** Thời gian GVCN đối soát quỹ lớp: giảm 90%. |
| **Input** — AI cần dữ liệu đầu vào gì mỗi lần chạy? Có sẵn không? | Ảnh chụp bill chuyển tiền, ảnh chụp đề cương viết tay, file ghi âm, tin nhắn gõ vội có tag `@BOT`. Có sẵn 100% từ nhóm chat Zalo. |
| **Feedback** — lấy phản hồi ở đâu để cải thiện? | Nút **"Báo sai thông tin"** (khi OCR đọc nhầm bill/đề cương) hoặc **"Xác nhận chuẩn"** 1-click từ phụ huynh/GVCN để liên tục cập nhật prompt và mô hình OCR. |

---

### 6.4. Hai câu hỏi của Google PAIR

- **Người dùng muốn được hỗ trợ (augment) hay giao hẳn việc (automate)? Bằng chứng:**
  - **Người dùng muốn được HỖ TRỢ (Augment).**
  - **Bằng chứng:** Việc học tập và đóng phí của con trẻ gắn liền với trách nhiệm gia đình và nhà trường. Phụ huynh và GVCN không chấp nhận giao 100% việc đối soát tiền bạc hay nhắc lịch thi cho AI tự quyết định mà cần AI **soạn nháp tóm tắt và tự động trích xuất**, con người giữ quyền kiểm tra/xác nhận cuối cùng.

- **AI sai kiểu nào tệ hơn, báo nhầm (False Positive) hay bỏ sót (False Negative)? Vì sao, và thiết kế đã xử lý thế nào:**
  - **BỎ SÓT (False Negative) TỆ HƠN RẤT NHIỀU.**
  - **Vì sao:** Nếu AI bỏ sót một bài tập về nhà, lịch thi hoặc khoản phí cần đóng, con sẽ bị phạt, thiếu đồ dùng học tập hoặc đóng muộn tiền học. Nếu báo nhầm (đưa một tin nhắn thảo luận vào nháp), phụ huynh chỉ tốn 2 giây để lướt qua bỏ chọn.
  - **Thiết kế đã xử lý:** Đặt cấu hình AI ưu tiên tối đa chỉ số **Recall** (thà trích xuất thừa còn hơn bỏ sót). Mọi tin nhắn/hình ảnh có tag `@BOT` hoặc chứa thông tin dặn dò đều được đưa vào bản nháp để người dùng xác nhận.

---

## 7. Problem Statement v1 + tiêu chí đánh giá (CP6)

### 7.1. Bảng Problem Statement v1

| Trường | Nội dung |
|---|---|
| **Actor** | **Phụ huynh học sinh** (người tiếp nhận thông tin & đóng phí), **Giáo viên chủ nhiệm** (người phát tin & quản lý quỹ lớp), **Học sinh** (đối tượng bị ảnh hưởng trực tiếp nếu phụ huynh quên/bỏ lỡ công việc). |
| **Quy trình** | Chiều tối các ngày trong tuần: Phụ huynh mở 3–5 nhóm chat Zalo → Lội qua tin tán gẫu/sticker (mất 10 phút) → Tìm bài tập rải rác trong tin nhắn/ảnh đề cương viết tay → Tìm STK/cú pháp chuyển tiền → Chuyển tiền và gửi ảnh bill lên nhóm → GVCN dò tay từng bill. |
| **Bottleneck** | **Lọc tin rác thủ công bằng mắt (bước 2 - mất 10 phút/tối)** trên luồng chat phân mảnh và **đối soát thủ công ảnh bill chuyển tiền** của GVCN. |
| **Impact** | Con bị phạt/thiếu đồ dùng học tập; đóng muộn tiền học; phụ huynh căng thẳng, trút giận lên con cái sau ngày làm việc kiệt sức; GVCN kiệt sức vì kiểm tra bill thủ công. |
| **Success Metric** (baseline → target, cách đo) | - **Thời gian cập nhật việc học:** 32 phút/tối → dưới 2 phút/tối.<br>- **Tỷ lệ bỏ sót việc cần làm (action items):** 15–20% → 0%.<br>- **Cách đo:** Log thời gian tương tác trên chat riêng với BOT & thống kê phản hồi bỏ sót việc của phụ huynh/GVCN hàng tuần. |
| **Boundary** | Không thay thế ứng dụng quản lý học bạ/điểm số chính thức của nhà trường; chỉ tập trung vào luồng giao tiếp dặn dò hàng ngày và tự động hóa đối soát thu phí qua nhóm chat. |
| **AI intervention point** | OCR đọc ảnh bill chuyển tiền & ảnh đề cương viết tay + LLM phân loại tin nhắn, trích xuất dặn dò từ văn bản/ghi âm và gửi bản tóm tắt cá nhân hóa trong chat riêng với BOT. |
| **Mức chọn** | **Workflow (Rule + LLM/OCR + Human-in-the-loop)** |
| **Rủi ro & người kiểm tra** | **Rủi ro:** AI OCR đọc nhầm nét chữ đề cương quá xấu hoặc đọc sai số tiền trên bill.<br>**Người kiểm tra:** GVCN (duyệt bảng quỹ) & Phụ huynh (duyệt bản tóm tắt cá nhân trên BOT). |

---

### 7.2. Thay đổi so với v0 và lý do

| Trường | v0 | v1 | Vì sao đổi |
|---|---|---|---|
| **Actor** | Chỉ có Phụ huynh. | Phụ huynh + GVCN + Học sinh. | GVCN cũng chịu gánh nặng đối soát bill tiền quỹ thủ công; Học sinh là đối tượng gánh chịu hậu quả nếu phụ huynh bỏ lỡ thông tin. |
| **AI Solution** | Chỉ tóm tắt tin nhắn văn bản chung trong group. | LLM + OCR xử lý đa phương tiện (văn bản, ảnh đề cương viết tay, file ghi âm, ảnh bill chuyển tiền). | Đúng thực tế giao tiếp: GVCN thường chụp đề cương viết tay, gửi ghi âm hoặc yêu cầu phụ huynh gửi ảnh bill chuyển tiền. |
| **Kênh đầu ra (Output)** | Phát thông báo chung lại vào nhóm chat lớp. | Gửi **Bản tóm tắt duy nhất** vào chat riêng giữa BOT và từng Phụ huynh. | Phụ huynh không phải vào nhóm chat lội tin nữa; giải quyết tận gốc vấn đề phân mảnh thông tin. |
| **Success Metric** | Giảm thời gian lội tin nhắn chung chung. | Thời gian cập nhật việc học (32p => <2p/tối) & Tỷ lệ bỏ sót action items (15-20% => 0%). | Bám sát đúng các chỉ số đo lường hiệu quả cụ thể trong Job Story của Problem Card #1. |

---

### 7.3. Tiêu chí đánh giá đầu ra của AI (3–5 tiêu chí)

| # | Tiêu chí | Đạt khi | Không đạt khi |
|---:|---|---|---|
| **1** | **Độ chính xác OCR Bill chuyển tiền (Financial OCR Accuracy)** | Trích xuất chính xác 100% các trường: Số tiền, Tên người chuyển, Cú pháp/Nội dung chuyển khoản từ ảnh chụp bill. | Trích xuất sai số tiền, đọc nhầm tên người chuyển hoặc bỏ sót bill chuyển khoản của phụ huynh. |
| **2** | **Độ chính xác trích xuất dặn dò (Action Item Extraction Accuracy)** | Trích xuất đầy đủ và đúng 100% các mục: Bài tập về nhà, Lịch thi/học, Đồ dùng cần chuẩn bị từ ảnh đề cương viết tay, ghi âm hoặc tin nhắn. | Trích xuất sai hạn nộp bài, đọc thiếu bài tập trong ảnh đề cương hoặc nhầm lẫn giữa các môn học. |
| **3** | **Tỷ lệ bỏ lỡ thông tin dặn dò (Recall Rate)** | 100% tin nhắn/hình ảnh/ghi âm được GVCN tag `@BOT` đều được xử lý và đưa vào bản nháp tóm tắt. | Bỏ sót tin nhắn có tag `@BOT`, khiến dặn dò quan trọng không xuất hiện trong bản tóm tắt của phụ huynh. |
| **4** | **Định dạng & Tính cá nhân hóa của bản tóm tắt (Digest Quality)** | Bản tóm tắt gửi riêng cho phụ huynh ngắn gọn (< 100 từ), phân rõ 3 phần (Bài tập - Lịch thi - Khoản phí) kèm checklist 1-click. | Bản tóm tắt dài dòng, giữ nguyên tin nhắn rác hoặc không phân chia rõ ràng các mục hành động cần làm. |

---

## 8. Quyết định (CP6)

### 8.1. Bốn rủi ro

| Rủi ro | Câu hỏi | Mức độ rủi ro (Thấp = an toàn / TB / Cao = nguy hiểm) | Lý do / bằng chứng |
|---|---|---|---|
| **Value** | Người dùng có thật sự cần và sẽ dùng không? | **Thấp (An toàn)** | Phụ huynh mất tới 32 phút/tối để lội tin nhắn phân mảnh; GVCN kiệt sức vì kiểm tra từng bill tiền quỹ. Nhu cầu có 1 bản tóm tắt duy nhất và tự động hóa đọc bill là cực kỳ cấp thiết. |
| **Usability** | Người dùng có dùng được, có hiểu và sửa được đầu ra của AI không? | **Trung bình** | Phụ huynh chỉ cần nhận 1 tin nhắn tóm tắt trong chat riêng với BOT và bấm nút 1-click. Tuy nhiên, rủi ro nằm ở việc GVCN phải kiểm tra bản nháp nếu ảnh đề cương viết tay quá mờ/xấu. |
| **Feasibility** | Có đủ dữ liệu, công cụ, kỹ năng để làm không? | **Thấp (An toàn)** | Công nghệ LLM và OCR hiện tại (như Gemini 1.5 Flash / GPT-4o / Cloud Vision API) xử lý rất tốt tiếng Việt, đọc được nét chữ viết tay và ảnh chụp giao diện ngân hàng Việt Nam. |
| **Viability** | Có hợp chi phí, pháp lý, quy định tổ chức không? Ai vận hành? | **Trung bình** | Phụ thuộc vào chính sách API Zalo OA / Bot Telegram và quy định bảo mật hình ảnh chuyển tiền/thông tin cá nhân của học sinh. Chi phí gọi API OCR + LLM cần được tối ưu. |

---

### 8.2. Kết luận

**Quyết định:** **GO (Triển khai Pilot)**

**Lý do:**
Bài toán giải quyết trực tiếp nỗi đau lớn của cả Phụ huynh (tốn 32 phút/tối) và GVCN (đối soát bill thủ công). Đã xác định rõ phương án không dùng AI (chỉ khóa nhóm 1 chiều) không giải quyết tận gốc vấn đề, trong khi mô hình Workflow (LLM + OCR + Human-in-the-loop) hoàn toàn khả thi về mặt kỹ thuật.

**Nếu Go — pilot nhỏ nhất:**
- **Quy mô:** Thử nghiệm trên **2–3 lớp học** (khoảng 100 phụ huynh, 3 GVCN).
- **Hình thức:** Triển khai 1 Zalo OA Bot / Telegram Bot vào nhóm chat lớp.
- **Tính năng core:**
  1. Phụ huynh/GVCN tag `@BOT` khi gửi ảnh đề cương viết tay, file ghi âm hoặc dặn dò → BOT trích xuất danh sách công việc.
  2. Phụ huynh gửi ảnh bill chuyển tiền có tag `@BOT` → BOT tự động OCR và đối soát danh sách nộp quỹ cho GVCN.
  3. Gửi **Bản tóm tắt duy nhất** tự động vào chat riêng với từng phụ huynh vào 19h00 hằng ngày.

**Ngưỡng dừng (Pivot / Drop Threshold):**
> *Nếu sau **3 tuần pilot** mà **> 20% ảnh bill chuyển tiền** bị OCR đọc sai phải sửa tay, HOẶC **> 15% phụ huynh** phản ánh bản tóm tắt vẫn bỏ sót bài tập của con, nhóm sẽ dừng mô hình Workflow AI này và chuyển về giải pháp **Rule đơn thuần + Google Form/Sheet** tự động đơn giản.*

---

## 9. Hạn chế và hướng tiếp theo

### 9.1. Hạn chế hiện tại của dự án
1. **Chất lượng hình ảnh đầu vào:** Ảnh chụp đề cương viết tay quá mờ, chữ quá xấu hoặc ảnh bill chuyển khoản bị che mờ có thể làm giảm độ chính xác của OCR.
2. **Phụ thuộc nền tảng:** Phụ thuộc vào chính sách tích hợp Bot và giới hạn API của Zalo / Messenger.
3. **Bảo mật dữ liệu tài chính & riêng tư:** Xử lý ảnh bill chuyển khoản yêu cầu cam kết bảo mật cao về thông tin tài khoản ngân hàng và số điện thoại cá nhân.

---

### 9.2. Hướng tiếp theo (Next Steps)

1. **Giai đoạn 1 — Tối ưu OCR & LLM Prompt (Tuần 1–3):**
   - Xây dựng bộ dataset 100+ ảnh bill chuyển tiền ngân hàng (VietQR, Momo, ZaloPay...) và 50+ ảnh đề cương viết tay thực tế để fine-tune prompt cho OCR và LLM.
   - Thử nghiệm các kịch bản báo sai để đảm bảo chỉ số Recall đạt 100%.

2. **Giai đoạn 2 — Triển khai MVP Pilot (Tuần 4–6):**
   - Triển khai thử nghiệm 3 tuần tại 3 lớp mục tiêu.
   - Đo lường chỉ số thực tế: Thời gian cập nhật việc học của phụ huynh (mục tiêu < 2 phút/tối) và tỷ lệ bỏ sót action items (mục tiêu 0%).

3. **Giai đoạn 3 — Mở rộng tính năng (Giai đoạn tiếp theo):**
   - Tự động đồng bộ checklist bài tập và lịch thi vào Google Calendar / Apple Reminders của phụ huynh.
   - Tích hợp tính năng tự động nhắc nộp tiền quỹ/học phí riêng cho từng phụ huynh chưa hoàn thành trước hạn.


## 10. Tài liệu tham khảo

-
