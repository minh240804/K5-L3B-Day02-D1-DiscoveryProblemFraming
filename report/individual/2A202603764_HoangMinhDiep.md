# Báo cáo cá nhân — 2A202603764_HoangMinhDiep

> Đổi tên file theo quy tắc `MSSV_HoTen.md`, ví dụ `20241234_NguyenVanAn.md` (MSSV trước, dấu `_`, họ tên viết liền không dấu). Sửa cả dòng tiêu đề phía trên cho khớp.
> Template chi tiết và prompt mẫu cho từng mục: [docs/01-worksheet.md](../../docs/01-worksheet.md).
> Mỗi thành viên một file trong `report/individual/` trên repo nhóm: copy template này thành file mới, điền, rồi commit bằng tài khoản GitHub của bạn. Không viết hộ người khác.

## 1. Thông tin học viên

- Họ tên: Hoàng Minh Diệp
- MSSV: 2A202603764
- Email trường (không bắt buộc, repo có thể để public): hoangminhdiepnd2004@gmail.com
- Tên nhóm: D1
- Link repo nhóm: https://github.com/minh240804/K5-L3B-Day02-D1-DiscoveryProblemFraming

---

## 2. Scan problem (CP1)

Lăng kính: **Lặp lại** · **Tốn thời gian** · **Cần đọc, tổng hợp nhiều thông tin** · **Pain từ người khác**.

| # | Lăng kính | Job Story: Khi… tôi muốn… để… | Ai chịu ảnh hưởng? | Dấu hiệu thật (thời gian, tần suất, số người, bằng chứng) |
|---:|---|---|---|---|
| 1 |Tốn thời gian |Khi vừa họp xong với stakeholder, tôi muốn có sẵn user story và AC, để dev kịp đưa vào sprint planning | BA, dev | Bình thường mất khoảng 2 tiếng.|
| 2 | Lặp lại |Khi họp xong, tôi muốn gửi meeting minutes trong ngày, để stakeholder xác nhận kịp | BA, stakeholder | Khoảng 30 phút đến 1 tiếng để sắp xếp lại thông tin đã ghi chép và thực hiện gửi. |
| 3 | Cần đọc, tổng hợp nhiều thông tin| Khi nhận tài liệu 25–30 trang từ khách hàng, tôi muốn nắm nhanh các yêu cầu chính, để hỏi đúng chỗ ở buổi họp tới| BA | Tốn khoảng 2 tiếng để đọc qua. |
| 4 | Pain từ người khác |Khi dev nhận story, họ muốn hiểu đúng yêu cầu ngay lần đầu, để không phải hỏi lại |dev, BA |Ước tính số lần hỏi lại trong tin nhắn khoảng 1 lần/story. |
| 5 | Lặp lại |Khi stakeholder thay đổi yêu cầu, tôi muốn tự động xác định những tài liệu, user story và test case bị ảnh hưởng, để không phải kiểm tra thủ công từng phần. |BA, QA, dev | Mất 30–60 phút/lần thay đổi; có thể bỏ sót requirement liên quan. |
| 6 |Cần đọc, tổng hợp nhiều thông tin | Khi cần biết vì sao từng chốt phương án A, tôi muốn tìm lại quyết định cũ, để không họp lại từ đầu | BA, cả team | 20 - 30 phút hoặc có thể nhiều hơn mỗi lần tìm kiếm thông tin cũ. |
| 7 |Pain từ người khác |Khi QA test, họ muốn phát hiện sớm yêu cầu mâu thuẫn hoặc thiếu, để không sửa muộn | QA, dev| 2 Bug do hiểu sai yêu cầu/ sprint |
| 8 |Tốn thời gian |Khi phải phân tích nhiều yêu cầu trong backlog, tôi muốn hệ thống tự động phân loại và đánh giá mức độ ưu tiên, để tập trung vào những yêu cầu quan trọng nhất. | BA, PO| Backlog lớn, mất thời gian trao đổi và sắp xếp ưu tiên. |


**Nếu có dùng AI để gợi ý thêm:** ý nào AI gợi ý mà bạn giữ lại, ý nào bỏ và vì sao.

- Al gợi ý các ý số 06, 07, 08
- Giữ lại ý 06: Tìm kiếm lịch sử quyết định nghiệp vụ. Đây là vấn đề thực tế vì thông tin thường nằm rải rác trong meeting minutes, email, tài liệu và tin nhắn. BA mất thời gian tìm lại lý do đưa ra quyết định trước đó. Có thể ứng dụng AI để xây dựng trợ lý tra cứu tri thức dự án, cho phép đặt câu hỏi bằng ngôn ngữ tự nhiên và truy xuất thông tin liên quan.
- Với các ý không lựa chọn:
+ 07: Phát hiện yêu cầu mâu thuẫn hoặc thiếu sót trước khi QA kiểm thử. Ý tưởng có tiềm năng nhưng tương đối gần với hoạt động review và kiểm thử yêu cầu hiện tại. Cần khảo sát thêm để xác định mức độ phổ biến và giá trị thực tế.
+ 08: Tự động phân loại và đánh giá mức độ ưu tiên backlog. Việc ưu tiên yêu cầu phụ thuộc nhiều vào chiến lược kinh doanh, nguồn lực và quyết định của PO. AI có thể hỗ trợ đề xuất nhưng vẫn cần con người can thiệp vào đánh giá.
---

## 3. Top 3 Problem Cards + quy trình nháp (CP2)

### Bảng chọn top 3

| Rank | Problem | Vì sao chọn | Điều còn chưa chắc |
|---:|---|---|---|
| 1 | Ghi chú và tạo story + AC sau khi họp (#1)| Quy trình rõ, tốn thời gian |Chất lượng AC đo như thế nào? |
| 2 | Gửi thông tin meeting minutes (#2) | Quy trình lặp lại sau mỗi buổi họp |   |
| 3 |Tìm quyết định cũ (#6) |Nhiều người bị ảnh hưởng (impact rộng) | Quyền truy cập dữ liệu với từng đối tượng, phạm vi nguồn thông tin rộng. |

### Problem Card #1

| Trường | Nội dung |
|---|---|
| Job Story| Khi vừa họp xong với stakeholder, tôi muốn có sẵn user story và AC, để dev kịp đưa vào sprint planning |
| Actor |BA phụ trách ghi nhận và sắp xếp yêu cầu |
| Thời điểm / bối cảnh | 1 ngày sau buổi họp, trước khi sprint planning|
| Quy trình hiện tại (3–7 bước) | 1. Sắp xếp ghi chú / nghe lại recording. 2. Gom yêu cầu theo chủ đề. 3. Viết user story. 4. Viết AC (gồm edge case). 5. Đối chiếu tài liệu cũ, tìm mâu thuẫn. 6. Nhập vào Jira. 7. Gửi dev/stakeholder review. |
| Bottleneck (bước nào, mất bao nhiêu phút) |Bước 4, viết AC: khoảng 40 phút, hay thiếu edge case và bị dev hỏi lại |
| Impact (nếu không giải thì sao) | Khoảng 2 tiếng/buổi họp; 2 buổi/tuần thì cần 4 tiếng/tuần/BA|
| Success metric (baseline → target) | Tổng thời gian từ 2 tiếng xuống dưới 60 phút|
| Phương án không dùng AI | Tạo sẵn template cho user story + checklist AC (Given/When/Then) + checklist edge case: giảm thời gian format, chưa giảm thời gian nghĩ AC. |
| Giả thuyết về AI (nếu có) | AI soạn nháp user story + AC từ ghi chú đã dọn, BA kiểm tra, bổ sung edge case, rồi mới nhập Jira. |
| Cảm nhận nhanh | Workflow |

Quy trình nháp hiện tại:

```text
HIỆN TẠI - 120 phút
[1 Sắp xếp ghi chú: 10'] → [2 Gom theo chủ đề: 15'] → [3 Viết user story: 15']
→ [4 Viết AC (gồm edge case): 40'] ← BOTTLENECK → [5 Đối chiếu tài liệu cũ: 25'] 
→ [6 Nhập Jira: 10'] → [7 Gửi dev/stakeholder review: 5']
```

### Problem Card #2

| Trường | Nội dung |
|---|---|
| Job Story | Khi họp xong, tôi muốn gửi meeting minutes trong ngày, để stakeholder xác nhận kịp |
| Actor | BA phụ trách ghi chép, tổng hợp nội dung và gửi biên bản cuộc họp cho stakeholder. |
| Thời điểm / bối cảnh | Ngay sau khi kết thúc cuộc họp, thường trong ngày làm việc, khi các bên vẫn còn nhớ nội dung trao đổi. |
| Quy trình hiện tại (3–7 bước) |1. Tổng hợp ghi chú trong cuộc họp. 2. Nghe lại recording nếu có nội dung chưa rõ. 3. Phân loại nội dung theo chủ đề. 4. Tổng hợp các vấn đề đã thảo luận và quyết định được thống nhất. 5. Ghi nhận yêu cầu, người phụ trách và deadline. 6. Kiểm tra lại nội dung và định dạng meeting minutes. 7. Gửi email cho stakeholder xác nhận. |
| Bottleneck (bước nào, mất bao nhiêu phút) | Bước 2-5: Sắp xếp lại ghi chú, đối chiếu recording và tổng hợp nội dung. Mất khoảng 30–60 phút cho mỗi buổi họp.|
| Impact (nếu không giải thì sao) |Meeting minutes được gửi chậm, stakeholder có thể quên nội dung đã thống nhất hoặc hiểu khác nhau về trách nhiệm và deadline. BA mất thời gian cho công việc tổng hợp lặp lại sau mỗi cuộc họp. |
| Success metric (baseline → target) | Thời gian tạo và gửi meeting minutes từ 30–60 phút xuống dưới 15 phút/buổi họp; đảm bảo gửi trong ngày và không bỏ sót quyết định, Action Items quan trọng. |
| Phương án không dùng AI |Sử dụng template meeting minutes cố định, checklist các nội dung cần ghi nhận và công cụ ghi âm/chuyển giọng nói thành văn bản. |
| Giả thuyết về AI (nếu có) | AI tiếp nhận ghi chú cuộc họp, tự động phân loại nội dung, trích xuất quyết định, người phụ trách và deadline, sau đó tạo bản nháp meeting minutes. BA kiểm tra và gửi stakeholder xác nhận. |
| Cảm nhận nhanh | Workflow |

Quy trình nháp hiện tại:

```text
HIỆN TẠI - 30 - 60 phút
[1. Tổng hợp ghi chú trong cuộc họp: 5-10'] → [2. Nghe lại recording: 0-5'] → [3. Phân loại nội dung theo chủ đề: 5']
→ [4. Tổng hợp các vấn đề đã thảo luận và quyết định được thống nhất: 5'] → [5. Ghi nhận yêu cầu, người phụ trách và deadline: 5-25'] ← BOTTLENECK
→ [6. Kiểm tra lại nội dung và định dạng meeting minutes: 5'] → [7. Gửi email cho stakeholder xác nhận: 5']
```

### Problem Card #3

| Trường | Nội dung |
|---|---|
| Job Story | Khi cần biết vì sao từng chốt phương án A, tôi muốn tìm lại quyết định cũ, để không họp lại từ đầu |
| Actor |BA, Dev, QA và các thành viên liên quan đến dự án cần tra cứu thông tin nghiệp vụ đã được thống nhất. |
| Thời điểm / bối cảnh | Khi phát sinh yêu cầu mới, cần kiểm tra logic nghiệp vụ cũ, có thành viên mới tham gia dự án hoặc cần giải thích lý do lựa chọn một phương án trước đây.|
| Quy trình hiện tại (3–7 bước) | 1. Xác định vấn đề hoặc quyết định nghiệp vụ cần tìm hiểu. 2. Nhớ lại thời điểm hoặc những người tham gia thảo luận. 3. Tìm kiếm trong meeting minutes, email, chat hoặc tài liệu dự án. 4. Đọc và đối chiếu các thông tin tìm được. 5. Xác định quyết định cuối cùng và lý do lựa chọn. 6. Nếu không tìm được, hỏi BA hoặc stakeholder từng tham gia. 7. Tổng hợp lại thông tin để sử dụng.|
| Bottleneck (bước nào, mất bao nhiêu phút) | Bước 3–4: Tìm kiếm và đối chiếu thông tin từ nhiều nguồn khác nhau. Mất khoảng 20–30 phút hoặc lâu hơn cho mỗi lần tìm kiếm, đặc biệt khi thông tin nằm rải rác hoặc không được ghi nhận đầy đủ.|
| Impact (nếu không giải thì sao) | BA và các thành viên phải mất thời gian tìm kiếm hoặc hỏi lại người cũ. Có thể phải tổ chức họp lại để làm rõ những vấn đề đã từng được thống nhất. Nguy cơ đưa ra quyết định không nhất quán với logic nghiệp vụ trước đó.|
| Success metric (baseline → target) |Thời gian tìm kiếm thông tin từ 30–60 phút xuống dưới 15 phút/lần; tăng tỷ lệ truy xuất được quyết định kèm nguồn tham chiếu và lý do lựa chọn. |
| Phương án không dùng AI | Xây dựng kho lưu trữ tập trung cho meeting minutes, email và tài liệu dự án; chuẩn hóa cách đặt tên file, gắn tag theo dự án, module, chủ đề và ngày tháng; lập Decision Log ghi nhận quyết định, lý do và người phê duyệt.|
| Giả thuyết về AI (nếu có) | Xây dựng AI Business Knowledge Assistant sử dụng RAG để tìm kiếm thông tin từ meeting minutes, email và tài liệu dự án. Người dùng đặt câu hỏi bằng ngôn ngữ tự nhiên, hệ thống tìm các thông tin liên quan và tổng hợp câu trả lời kèm nguồn trích dẫn, thời điểm và bối cảnh quyết định.|
| Cảm nhận nhanh | Agent |

Quy trình nháp hiện tại:

```text
HIỆN TẠI - 20 - 30 phút
[1. Xác định vấn đề hoặc quyết định nghiệp vụ cần tìm hiểu: 2'] → [2. Nhớ lại thời điểm hoặc những người tham gia thảo luận: 3'] → [3. Tìm kiếm trong meeting minutes, email, chat hoặc tài liệu dự án: 10-15'] → [4. Đọc và đối chiếu các thông tin tìm được: 10-15'] ← BOTTLENECK → [5. Xác định quyết định cuối cùng và lý do lựa chọn: 3'] → [6. Hỏi BA hoặc stakeholder từng tham gia nếu không tìm được: 2'] → [7. Tổng hợp lại thông tin để sử dụng: 2']
```

### Card muốn pitch nhất

- Card số: #1
- Vì sao: 
Đây là công việc BA phải thực hiện thường xuyên sau mỗi buổi họp, có quy trình rõ ràng và dễ chuẩn hóa.
Có bottleneck cụ thể là viết AC, đặc biệt là phân tích edge case, mất thời gian soạn thảo và thường phải chỉnh sửa khi dev review.
AI có thể hỗ trợ trực tiếp bằng cách chuyển ghi chú cuộc họp thành bản nháp User Story và AC theo format Given/When/Then. BA vẫn giữ vai trò kiểm tra và phê duyệt.
Có khả năng triển khai thành workflow tự động hóa, tích hợp với Jira và mở rộng trong quy trình phát triển phần mềm.

- Câu hỏi muốn nhóm phản biện: Làm thế nào để kiểm soát hallucination, tránh AI tự suy diễn thêm business rules không có trong ghi chú cuộc họp?

### AI đã phản biện card thế nào

| Điểm yếu AI chỉ ra | Đồng ý? | Đã sửa gì |
|---|---|---|
| Baseline 120' chỉ dựa trên trí nhớ |Đồng ý |Bấm giờ thật 2 buổi họp |
| AC do AI viết nghe hợp lý nhưng có thể thêm yêu cầu stakeholder chưa hề nói|Đồng ý |Thêm boundary "không đưa nội dung không có trong ghi chú" |
| Gợi ý agent tự tạo ticket Jira |Đồng ý |Giữ "BA duyệt trước khi tạo ticket" làm boundary |

---

## 4. Tôi đã tham gia phần nào (CP3 → CP7)


| Hoạt động | Tôi đã làm gì? | Kết quả / ảnh hưởng tới bài nhóm |
|---|---|---|
| Pitch Problem Card | Chia sẻ 3 card cá nhân (#1 BA AC Generator, #2 Meeting Minutes, #3 Decision Finder) và nghe 6 card của các thành viên còn lại. | Cùng thảo luận điểm mạnh, điểm yếu từng card và đi đến thống nhất. |
| Phản biện bài của bạn khác | Hỏi #7: "OCR chữ viết tay mờ có chính xác không?" Hỏi #9: "App ngân hàng có can thiệp được cuộc gọi riêng tư không?" | Làm rõ rủi ro kỹ thuật (OCR) và tính khả thi của #9. |
| Nhận phản biện | Nhận câu hỏi cho #8 (PowerShell đã đủ chưa?) và #2 (khác gì Whisper/Notion AI?). Tôi đã sửa: nêu rõ giá trị thặng dư của #2 là bước từ transcript sang minutes có cấu trúc và đối chiếu quyết định. | Định vị lại giá trị của candidate so với công cụ có sẵn. |
| Gom cluster / cây OST | Đóng góp candidate vào Cluster A (BA Operations), xây dựng OST nhánh Opportunity B. | Nhóm có cây OST hai nhánh để so sánh cơ hội. |
| Chọn candidate problem | Tham gia chấm điểm 9 candidate theo 7 tiêu chí (mục 2.4). | #7 đạt 34 điểm, cao nhất nhóm, nên được chọn. |
| Kiểm chứng / research | Phỏng vấn 2 phụ huynh, cung cấp tín hiệu xác nhận pain point cho #7. | Xác nhận pain point thật, củng cố quyết định chọn #7. |
| Quy trình nhóm | Xây dựng quy trình tương lai 7 bước (Rule → AI → Rule → Human). | Có quy trình "sau" rõ ràng để so với quy trình hiện tại. |
| Problem Statement | Hỗ trợ An chỉnh sửa Problem Statement v0 và v1. | PS rõ hơn về phạm vi và tiêu chí. |
| Mức can thiệp AI | Phân tích ma trận Medium Ambiguity × Medium Complexity, so sánh 4 mức (No AI / Rule / Workflow / Agent). | Chọn Workflow thay vì mặc định Agent. |
| Quyết định | Đánh giá 4 rủi ro (Value/Usability/Feasibility/Viability) ở mục 8.1. | Căn cứ để nhóm chốt GO (Pilot). |

---

## 5. Dùng AI

| Checkpoint | Tôi dùng AI để làm gì? | AI hữu ích ở đâu? | AI sai hoặc hời hợt ở đâu? | Tôi sửa gì bằng nhận định của mình? |
|---|---|---|---|---|
| CP1 Scan | Tôi dùng AI để gợi ý thêm về các pain point trong công việc của BA | AI truy vấn được lượng lớn thông tin và đề xuất thêm được nhiều góc nhìn | Nhiều problem AI đưa ra chưa thật sự phù hợp | Tôi loại các ý quá rộng hoặc không có quy trình thật chỉ giữ ý lặp lại được, có người chịu ảnh hưởng rõ và bấm giờ được |
| CP2 Problem Card | Tôi nhờ AI đóng vai dev/QA hoài nghi để phản biện Problem Card #1 | AI chỉ ra baseline thời gian mới dựa trên trí nhớ, và AC do AI viết có thể thêm yêu cầu mà stakeholder chưa hề nói | AI gợi ý để agent tự tạo ticket Jira, vượt quá nhu cầu và làm tăng rủi ro | Tôi bấm giờ thật ở các buổi họp để lấy baseline, và giữ nguyên boundary "BA duyệt trước khi tạo ticket" |
| CP4 Research | Tôi nhờ AI tìm các công cụ và case đã giải quyết bài toán tương tự (Agent transcript cuộc họp, công cụ ghi biên bản) | AI tìm nhanh được nhiều giải pháp có sẵn, giúp tôi đổi hướng từ "tự xây công cụ" sang "dùng công cụ có sẵn" | Mô tả tính năng thường nói chung chung là tạo được story kèm AC, trong khi thảo luận người dùng cho thấy AC có thể bị đổ hết vào mục Description vì Rovo chưa sửa được custom field. Một số tính năng và chi phí cũng cần kiểm lại | Tôi tự mở từng link, đối chiếu thêm thảo luận cộng đồng, thêm bước BA kiểm ticket sau khi tạo, và đưa chi phí theo credit vào rủi ro Viability |
| CP5 Quy trình | Tôi nhờ AI chuyển mô tả quy trình thành sơ đồ trước/sau và bảng so sánh chỉ số | AI làm nhanh, trình bày rõ từng bước, tự tính được số bước và số bước thủ công trước/sau | Thời gian từng bước chỉ là ước lượng chứ chưa phải số đo; sơ đồ dễ gộp bước viết AC với bước kiểm | Tôi thay bằng số bấm giờ thật, tách riêng bước viết AC để thể hiện đúng bottleneck, và chỉnh lại các bước còn lại cho khớp cách tôi làm |
| CP5–6 Problem Statement | Tôi nhờ AI soạn Problem Statement v0 và góp ý để nâng lên v1 | AI chỉ ra metric v0 chỉ đo tốc độ, gợi ý thêm metric chất lượng (tỉ lệ viết lại, số lần dev hỏi lại) và bộ tiêu chí đánh giá bản nháp | Bản v0 còn chung chung ở phần Actor, chưa nói rõ điều kiện team nào thì mới cần giải pháp này | Tôi thu hẹp Actor theo kết quả phỏng vấn, chọn metric đo được trong 4 buổi pilot, và rút gọn tiêu chí đánh giá về 4 điểm tôi thật sự kiểm được |
| CP6 Mức can thiệp / quyết định | Tôi nhờ AI lập ma trận 4 mức (No AI / Rule / Workflow / Agent), AI Canvas, câu hỏi PAIR và bảng đánh giá rủi ro | AI buộc tôi so sánh đủ 4 mức, và giúp nhìn ra "sai kiểu nào tệ hơn" | AI có xu hướng nghiêng về giải pháp phức tạp hơn| Tôi chọn Workflow dựa trên phỏng vấn, giữ No AI cho team yêu cầu đơn giản và đặt ngưỡng dừng cho pilot |

---

## 6. Reflection (CP7)

Trả lời bằng trải nghiệm thật của bạn, tối thiểu 200 từ cho các câu 6.1–6.6 (không tính 6.7, câu này được chấm riêng ở tiêu chí C5). **Không dùng AI để viết thay.**

**6.1. Tôi học được gì khi nghe top 3 problems của các bạn khác?** Tôi thấy thêm nhiều lĩnh vực, nhiều công việc gặp khó khăn trong quy trình bình thường. 

**6.2. Nhóm có lúc nào bị "solution-first" (nghĩ giải pháp trước khi hiểu vấn đề) không? Lúc đó nhóm nhận ra và xử lý thế nào?** Có. Ban đầu nhóm khá tập trung vào việc áp dụng Al và tự động hóa workflow trong giải quyết vấn đề. Sau đó, nhóm nhận ra cần hiểu rõ quy trình hiện tại, xác định công đoạn mất nhiều thời gian nhất rồi mới lựa chọn giải pháp phù hợp. Giải pháp phức tạp nhất chưa chắc đã giải quyết được bài toán.

**6.3. Tôi có đổi ý sau khi bị phản biện không? Kể một lần cụ thể.** Có. Ban đầu tôi nghĩ AI có thể tự động tạo hoàn chỉnh User Story và Acceptance Criteria. Tuy nhiên, sau khi thảo luận, tôi nhận ra AI có thể bỏ sót edge case hoặc suy diễn sai business rules. Vì vậy, tôi đồng ý với hướng AI tạo bản nháp và cần con người phê duyệt.

**6.4. Kết quả kiểm chứng (phỏng vấn/survey/research) có làm tôi bất ngờ không? Điều gì?** Kết quả kiểm chứng không khiến tôi bất ngờ vì hiện trạng vấn đề xảy ra nhiều, tình huống quá tải tin nhắn xảy ra với đa số con người. Tuy nhiên tôi khá bất ngờ với các giải pháp hiện có trên thị trường.

**6.5. Điều khó nhất khi viết Problem Statement là gì?** Khó nhất là xác định đúng vấn đề cốt lõi và bottleneck thay vì chỉ mô tả công việc đang mất thời gian. Ngoài ra, việc xác định được target sao cho cụ thể, có thể đo lường được cũng là thách thức.

**6.6. Nếu làm lại, tôi sẽ đổi gì? Tôi sẽ phản biện nhóm mạnh hơn ở điểm nào?** Tôi sẽ dành nhiều thời gian hơn để tìm hiểu và kiểm chứng quy trình thực tế, thay vì dựa nhiều vào giả định và phỏng đoán. Tôi cũng sẽ phản biện nhóm kỹ hơn về tính chính xác của AI, các trường hợp ngoại lệ.

**6.7. Hiểu bài:** giải thích bằng 5–8 câu, không nhìn tài liệu, chuỗi *problem → quy trình → metric → boundary → mức can thiệp AI → quyết định* của bài nhóm mình.
1. Problem: Phụ huynh phải đọc hàng trăm tin nhắn từ nhiều nhóm Zalo để tìm thông tin quan trọng về bài tập, lịch thi và các khoản phí.

2. Quy trình: Hiện tại phụ huynh phải lọc tin nhắn, tìm ảnh bài tập, ghi chú công việc và tìm lại thông tin chuyển khoản.

3. Metric: Mục tiêu giảm thời gian cập nhật thông tin từ 32 phút xuống dưới 2 phút mỗi tối, đồng thời giảm tỷ lệ bỏ sót Action Items từ 15–20% xuống 0%.

4. Boundary: AI chỉ xử lý và tổng hợp thông tin được giáo viên cung cấp, không tự ý thay đổi nội dung hoặc đưa ra thông báo chưa được xác nhận.

5. Mức can thiệp AI: Sử dụng LLM kết hợp OCR để đọc tin nhắn, nhận diện chữ viết tay, trích xuất thông tin quan trọng và tổng hợp các công việc cần làm.

6. Human-in-the-loop: Giáo viên cung cấp và xác nhận thông tin, AI xử lý và gửi bản tổng hợp riêng cho phụ huynh.

7. Quyết định: Nhóm lựa chọn giải pháp Workflow kết hợp LLM và Document Extraction nhằm giảm thời gian tìm kiếm thủ công, giúp phụ huynh không bỏ lỡ những thông tin quan trọng của con.
---

## 7. Tài liệu tham khảo

- Google PAIR (People + AI Research). People + AI Guidebook. Google LLC.


