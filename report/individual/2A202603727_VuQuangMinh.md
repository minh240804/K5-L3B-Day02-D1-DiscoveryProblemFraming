# Báo cáo cá nhân — MSSV_HoTen

> Đổi tên file theo quy tắc `MSSV_HoTen.md`, ví dụ `20241234_NguyenVanAn.md` (MSSV trước, dấu `_`, họ tên viết liền không dấu). Sửa cả dòng tiêu đề phía trên cho khớp.
> Template chi tiết và prompt mẫu cho từng mục: [docs/01-worksheet.md](../../docs/01-worksheet.md).
> Mỗi thành viên một file trong `report/individual/` trên repo nhóm: copy template này thành file mới, điền, rồi commit bằng tài khoản GitHub của bạn. Không viết hộ người khác.

## 1. Thông tin học viên

- Họ tên: VuQuangMinh
- MSSV: 2A202603727
- Email trường (không bắt buộc, repo có thể để public): 26ai.minhvq3@vinuni.edu.vn
- Tên nhóm: D1
- Link repo nhóm: https://github.com/minh240804/K5-L3B-Day02-D1-DiscoveryProblemFraming

---

## 2. Scan problem (CP1)

Lăng kính: **Lặp lại** · **Tốn thời gian** · **Cần đọc, tổng hợp nhiều thông tin** · **Pain từ người khác**.

| # | Lăng kính | Job Story: Khi… tôi muốn… để… | Ai chịu ảnh hưởng? | Dấu hiệu thật (thời gian, tần suất, số người, bằng chứng) |
|---:|---|---|---|---|
| 1 | **Tốn thời gian** | Khi nhận yêu cầu từ khách hàng, tôi muốn tổng hợp và phân tích các yêu cầu thành tài liệu thống nhất để Developer và Tester có thể hiểu đúng phạm vi công việc. | BA, Dev, Tester | Theo nghiên cứu của Carnegie Mellon Software Engineering Institute (SEI), khoảng 35,25% lỗi trong quá trình phát triển phần mềm liên quan đến Requirements. |
| 2 | **Tốn thời gian** | Khi muốn kiểm tra giá cước xe, tôi muốn một cách tiện lợi hơn tổng hợp từ nhiều nguồn để thuân tiện trong việc tìm kiếm | Người đặt, Chủ đại lý | Giá dịch vụ gọi xe thay đổi theo cung cầu, thời tiết và thời điểm. Người dùng phải kiểm tra nhiều ứng dụng để tìm giá phù hợp. |
| 3 | **Cần đọc, tổng hợp nhiều thông tin** | Khi tìm kiếm ciệc trên các nền tảng, tôi muốn tìm các công việc phù hợp cả về yêu cầu trình độ và mức lương để việc tìm kiếm chính xác | Ứng viên |  |
| 4 | **Lặp lại** | Khi nhận một Bug mới, tôi muốn hệ thống tự động phân loại Bug theo mức độ nghiêm trọng, module và người phụ trách để giảm thao tác phân loại thủ công. | Tester, Developer, PM | Mỗi ngày có nhiều Bug; các bước phân loại gần như giống nhau; phải nhập lại thông tin trên Jira. |
| 5 |  **Cần đọc, tổng hợp nhiều thông tin** | Khi muốn kiểm soát chi tiêu cuối tháng, tôi muốn tổng hợp giao dịch từ hóa đơn, ví điện tử và tài khoản ngân hàng để hiểu tiền đã được sử dụng như thế nào. | Cá nhân, gia đình | Giao dịch phát sinh hằng ngày; dữ liệu phân tán ở nhiều ứng dụng; khó nhớ các khoản chi nhỏ. |



**Nếu có dùng AI để gợi ý thêm:** ý nào AI gợi ý mà bạn giữ lại, ý nào bỏ và vì sao.

-

---

## 3. Top 3 Problem Cards + quy trình nháp (CP2)

### Bảng chọn top 3

| Rank | Problem | Vì sao chọn | Điều còn chưa chắc |
|---:|---|---|---|
| 1 | Tra cứu giá cước | Nhu cầu thường xuyên, nhiều nhà cung cấp và mức giá có thể thay đổi theo thời gian. | Cần nhiều yếu tố quyết định hơn chỉ là giá |
| 2 | TÌm việc| Vấn đề phổ biến, Các nền tảng lớn có nhiều công viẹc | Khó đánh giá độ tin cậy tuyệt đối. Nhiều công việc cũng không phải do công ty đăng |
| 3 | Quản lý chi tiêu| Nhiều người gặp, phổ biến | Sử dụng nhiều thông tin, Không thể chắc ở tiền mặt, Phụ thuộc nhiều vào quyền cũng như bên thứ 3 |

### Problem Card #1

| Trường | Nội dung |
|---|---|
| Job Story | Khi muốn kiểm tra giá cước xe, tôi muốn một cách tiện lợi hơn tổng hợp từ nhiều nguồn để thuân tiện trong việc tìm kiếm |
| Actor | Người dùng ( đặt xe) |
| Thời điểm / bối cảnh | Mọi thời điểm /  Người cân di chuyển  |
| Quy trình hiện tại (3–7 bước) |1. Xác định điểm đi và điểm đến. 2. Mở từng ứng dụng. 3. Nhập thông tin hành trình. 4. Chờ hiển thị giá. 5. So sánh và lựa chọn. |
| Bottleneck (bước nào, mất bao nhiêu phút) | Bước 2–4: Phải chuyển đổi giữa nhiều ứng dụng, nhập lại thông tin và chờ kết quả. Bạn ước tính mất 3 phút/app, tổng cộng khoảng 10 phút khi kiểm tra 3–4 ứng dụng. Cần đo thực tế để xác nhận. |
| Impact (nếu không giải thì sao) | Mất thời gian tìm kiếm; có thể bỏ lỡ mức giá hoặc lựa chọn phù hợp hơn. Đặc biệt bất tiện khi cần đặt xe nhanh.  |
| Success metric (baseline → target) | muốn giảm thời gian thực tế so sánh tương đương với việc tìm từng app (10p -  3p)  |
| Phương án không dùng AI | Xây dựng hệ thống tích hợp dữ liệu/API từ các nhà cung cấp, truy vấn đồng thời và hiển thị bảng so sánh. |
| Giả thuyết về AI (nếu có) | AI có thể phân tích nhu cầu người dùng, đánh giá các phương án theo giá, thời gian chờ, thời gian di chuyển và đưa ra đề xuất phù hợp. |
| Cảm nhận nhanh | Workflow + Agent |
Quy trình nháp hiện tại:
 
```text

```

### Problem Card #2

| Trường | Nội dung |
|---|---|
| Job Story | Khi tìm kiếm ciệc trên các nền tảng, tôi muốn tìm các công việc phù hợp cả về yêu cầu trình độ và mức lương để việc tìm kiếm chính xác |
| Actor | Ứng viên |
| Thời điểm / bối cảnh | Mọi thời điểm   |
| Quy trình hiện tại (3–7 bước) | 1. Truy cập các nền tảng tuyển dụng. 2. Nhập từ khóa và thiết lập bộ lọc. 3. Đọc mô tả công việc và yêu cầu tuyển dụng. 4. Đối chiếu yêu cầu với CV và năng lực bản thân. 5. So sánh mức lương, phúc lợi và các điều kiện khác. 6. Chọn công việc phù hợp và gửi hồ sơ. |
| Bottleneck (bước nào, mất bao nhiêu phút) |Bước 3–5: Ứng viên phải đọc và phân tích từng JD, đối chiếu với năng lực cá nhân, sau đó tự so sánh giữa các công việc. Các công ty có cách mô tả yêu cầu khác nhau nên khó đánh giá mức độ phù hợp một cách nhất quán.|
| Impact (nếu không giải thì sao) | Tốn nhiều thời gian tìm kiếm; có thể bỏ lỡ công việc phù hợp, ứng tuyển vào vị trí không đáp ứng yêu cầu hoặc không phù hợp với mong muốn về lương và phúc lợi.  |
| Success metric (baseline → target) | 	Đo thời gian từ lúc bắt đầu tìm kiếm đến khi có danh sách công việc phù hợp. Ví dụ: giảm từ baseline đo thực tế xuống không quá 10 phút. Đồng thời theo dõi tỷ lệ công việc được đề xuất mà ứng viên đánh giá là phù hợp.  |
| Phương án không dùng AI | Thiết lập bộ lọc và nhiều tiêu chí, khóa theo từ khóa |
| Giả thuyết về AI (nếu có) | Sự dụng mô hình ngôn ngữ kết hợp sematic |
| Cảm nhận nhanh | Rule  |

### Problem Card #3

| Trường | Nội dung |
|---|---|
| Job Story | Khi muốn kiểm soát chi tiêu cuối tháng, tôi muốn tổng hợp giao dịch từ hóa đơn, ví điện tử và tài khoản ngân hàng để hiểu tiền đã được sử dụng như thế nào. |
| Actor | Người có khoản chi tiêu  |
| Thời điểm / bối cảnh | Mọi thời điểm /  Người sử dụng  |
| Quy trình hiện tại (3–7 bước) |1. Mở app ngân hàng / thanh toán 2. Vòa phần lịch sủ. 3. QUan sát và ghi lại các thanh toán 4. Lặp tương tự với các app khác 5. toonge kết | Bước 2–4: Phải chuyển đổi giữa nhiều ứng dụng, nhập lại thông tin và chờ kết quả. Bạn ước tính mất 3 phút/app, tổng cộng khoảng 10 phút khi kiểm tra 3–4 ứng dụng. Cần đo thực tế để xác nhận. |
| Impact (nếu không giải thì sao) | Mất thời gian tìm kiếm; Có thể thiếu các thanh toán  |
| Success metric (baseline → target) | muốn giảm thời gian thực tế so sánh tương đương với việc tìm từng app (10p -> 3p)  |
| Phương án không dùng AI | Xây dựng hệ thống tích hợp dữ liệu/API từ các nhà cung cấp, truy vấn đồng thời và hiển thị bảng so sánh. |
| Giả thuyết về AI (nếu có) | AI có thể phân tích nhu cầu người dùng, đánh giá các phương án theo giá, thời gian chờ, thời gian di chuyển và đưa ra đề xuất phù hợp. |
| Cảm nhận nhanh | Workflow + Agent |

### Card muốn pitch nhất

- Card số: #2
- Vì sao: Vì nó luôn là yêu cầu thiết yếu, Càng khi AI phát triển đây sẽ là bài toán mà mọi nền tảng cần phải giải
- Câu hỏi muốn nhóm phản biện: Tính tin cậy của các thông tin 

### AI đã phản biện card thế nào

| Điểm yếu AI chỉ ra | Đồng ý? | Đã sửa gì |
|---|---|---|
| | | |

---

## 4. Tôi đã tham gia phần nào (CP3 → CP7)

| Hoạt động | Tôi đã làm gì? | Kết quả / ảnh hưởng tới bài nhóm |
|---|---|---|
| Pitch Problem Card | Chia sẻ 3 card cá nhân (#4 So sánh giá xe, #5 Matching Job & CV, #6 Quản lý chi tiêu) và nghe 6 card của các thành viên còn lại. | Cùng nhóm thảo luận điểm mạnh, điểm yếu từng card để đi đến thống nhất. |
| Phản biện bài của bạn khác | Hỏi #8: "Chỉ cần PowerShell/Intune thì có cần AI không?" Hỏi #4: "Có bị Grab/Gojek chặn API không?" | Làm rõ giá trị thật của AI và rủi ro phụ thuộc bên thứ ba. |
| Nhận phản biện | Nhận câu hỏi cho #1 (chất lượng AC) và #6 (rủi ro OTP/banking). Tôi đã sửa: `[điền]`. | Bổ sung giới hạn và rủi ro vào phần đánh giá. |
| Gom cluster / cây OST | Tham gia gom 9 candidate thành 3 cluster. | Nhóm có cấu trúc cluster và OST để chọn hướng. |
| Chọn candidate problem | Tham gia chấm điểm 9 candidate (mục 2.4). | #7 đạt 34 điểm, cao nhất nhóm, nên được chọn. |
| Kiểm chứng / research | Research 4 nguồn: Zalo 1 chiều, eNetViet/SMAS, quy tắc nhóm chat, ghim tin nhắn (bảng 3.3). | Giúp hiểu giải pháp hiện có và đưa ra hướng workflow 1 chiều. |
| Quy trình nhóm | Vẽ quy trình hiện tại 5 bước, xác định bottleneck ở bước 2 (~10 phút/tối). | Làm cơ sở cho bảng before/after. |
| Problem Statement | Đóng góp v1, mở rộng Actor thành Phụ huynh + GVCN + Học sinh. | PS v1 phản ánh đủ các bên liên quan. |
| Mức can thiệp AI | Xây dựng AI Canvas (Prediction/Judgment/Action/Outcome), trả lời 2 câu Google PAIR. Chọn Augment, ưu tiên Recall. | Nhóm chốt hướng Augment, ưu tiên không bỏ sót tin quan trọng. |
| Quyết định | Đề xuất ngưỡng dừng Pivot/Drop và phạm vi pilot (2-3 lớp, ~100 phụ huynh). | Pilot có điều kiện dừng và quy mô rõ ràng. |

---

## 5. Dùng AI

| Checkpoint | Tôi dùng AI để làm gì? | AI hữu ích ở đâu? | AI sai hoặc hời hợt ở đâu? | Tôi sửa gì bằng nhận định của mình? |
|---|---|---|---|---|
| CP1 Scan | | | | |
| CP2 Problem Card | | | | |
| CP4 Research | | | | |
| CP5 Quy trình | | | | |
| CP5–6 Problem Statement | | | | |
| CP6 Mức can thiệp / quyết định | | | | |

---

## 6. Reflection (CP7)

Trả lời bằng trải nghiệm thật của bạn, tối thiểu 200 từ cho các câu 6.1–6.6 (không tính 6.7, câu này được chấm riêng ở tiêu chí C5). **Không dùng AI để viết thay.**

**6.1. Tôi học được gì khi nghe top 3 problems của các bạn khác?**
Các problems các bạn có nhiều phần liên quan đến nghiệp vụ làm việc. Nó cho thấy các vấn đề khác nhau và cách nhìn khi giải quyết nó

**6.2. Nhóm có lúc nào bị "solution-first" (nghĩ giải pháp trước khi hiểu vấn đề) không? Lúc đó nhóm nhận ra và xử lý thế nào?**
Nhóm tôi đã từng rơi vào bẫy "solution-first" rất nặng ở giai đoạn đầu của CP5. Khi vừa chọn xong bài toán nhóm chat phụ huynh, phản xạ đầu tiên của cả nhóm là: "Hãy xây một con Bot AI Telegram/Zalo tự động nhảy vào nhóm chat cá nhân của lớp để cào tin nhắn và tóm tắt mỗi ngày!". Nhóm đã dành gần nửa buổi thảo luận chỉ để bàn xem nên dùng model LLM nào, dùng RAG ra sao để bot không bị trôi tin.

Nhóm chỉ sực tỉnh khi đặt ra câu hỏi kiểm chứng bối cảnh: "Zalo có cho phép một con bot tự do vào đọc lén tin nhắn nhóm cá nhân của 40 phụ huynh không? Giáo viên có đồng ý cho bot vào nhóm không?". Lúc này, nhóm mới nhận ra mình chưa hề hiểu kỹ rào cản nền tảng (Platform Lock-in) và nỗi đau của Giáo viên. Nhóm đã lập tức dừng việc thảo luận giải pháp công nghệ, quay lại phân tích lại quy trình tương tác thực tế và phát hiện ra rằng giải pháp phải đi từ gốc: Giáo viên nạp dữ liệu thô vào Zalo OA riêng tư, AI bóc tách và gửi 1-1, đồng thời hỗ trợ Giáo viên đối soát thu chi để tạo động lực Win-Win cho cả hai bên.

**6.3. Tôi có đổi ý sau khi bị phản biện không? Kể một lần cụ thể.**
Có đổi ý. Khi được nhận câu "Rủi ro bảo mật OTP/Banking API là cực cao, liệu người dùng dám cấp quyền?" Đã khiến vấn đè nổi rõ rnag hơn. Việc biết rõ người dùng và khỏa chi cực dễ khiên họ là mục tiêu tán công. Khác với các giải pháp trên thị trường lớn mạnh có thể đầu tư vào bảo mật

**6.4. Kết quả kiểm chứng (phỏng vấn/survey/research) có làm tôi bất ngờ không? Điều gì?**
Không quá bất ngờ. Vấn đề này sec gặp nhiều ở các lớp thật sự đông. 

**6.5. Điều khó nhất khi viết Problem Statement là gì?**
Mức can thiệp AI — chọn Workflow nhưng vẫn phải giải thích "tại sao không phải Rule"

**6.6. Nếu làm lại, tôi sẽ đổi gì? Tôi sẽ phản biện nhóm mạnh hơn ở điểm nào?**
Tôi nghĩ mình sẽ ít nói về vấn đề khả thi. Tập trung nhiều hơn về khía cạnh nó có thật sự giả quyết vấn đề không. Vì zalo hoạt động trên 1 kênh duy nhất tool hoàn toàn có thể làm vấn đề nhiều hơn 

**6.7. Hiểu bài:** giải thích bằng 5–8 câu, không nhìn tài liệu, chuỗi *problem → quy trình → metric → boundary → mức can thiệp AI → quyết định* của bài nhóm mình.
Phụ huynh học sinh mỗi tối phải mở 3–5 nhóm Zalo lớp, lội qua hàng trăm tin nhắn tán gẫu/sticker để nhặt ra bài tập, lịch thi và khoản phí cần đóng — mất khoảng 32 phút/tối và vẫn có nguy cơ bỏ sót 15–20% việc cần làm, trong khi GVCN cũng kiệt sức vì phải dò tay từng ảnh bill chuyển khoản của phụ huynh. Quy trình hiện tại gồm 5 bước: mở nhóm → lọc tin rác bằng mắt (bottleneck chính, ~10 phút) → tìm bài tập rải rác trong văn bản/ảnh viết tay → ghi nhớ/ghi chú → tìm STK và chuyển tiền; quy trình tương lai thay bước lọc thủ công bằng chuỗi Rule (tag @BOT) → AI (OCR ảnh đề cương/bill + LLM trích xuất) → Rule (kiểm tra định dạng, độ tin cậy) → Human duyệt → BOT gửi bản tóm tắt cá nhân hóa vào chat riêng từng phụ huynh. Metric đặt ra là thời gian cập nhật việc học giảm từ 32 phút/tối xuống dưới 2 phút/tối, tỷ lệ bỏ sót action items từ 15–20% xuống 0%, đo qua log tương tác với BOT và phản hồi hàng tuần — đây là mục tiêu kỳ vọng, chưa phải kết quả đã kiểm chứng. Boundary xác định rõ AI chỉ đọc–phân loại–trích xuất–tổng hợp, không tự suy đoán thông tin thiếu (STK, số tiền, hạn nộp), GVCN giữ quyền xác nhận thông tin quan trọng và phụ huynh là người quyết định hành động cuối cùng, đặc biệt với chuyển khoản; hệ thống cũng không thay thế app học bạ chính thức của trường. Mức can thiệp AI được chọn là Workflow (Rule + LLM/OCR + Human-in-the-loop) vì dữ liệu đầu vào đa phương tiện (văn bản gõ vội, ảnh viết tay, ghi âm, ảnh bill) khiến Rule thuần bất lực, còn để Agent tự quyết là rủi ro quá cao với tiền bạc và lịch học của trẻ; thiết kế ưu tiên Recall (thà báo thừa còn hơn bỏ sót). Quyết định cuối cùng là GO (Pilot) trên 2–3 lớp (~100 phụ huynh, 3 GVCN) với 3 tính năng core, kèm ngưỡng dừng rõ ràng: nếu sau 3 tuần có >20% bill OCR sai phải sửa tay hoặc >15% phụ huynh phản ánh bỏ sót bài tập thì dừng mô hình AI và chuyển về Rule + Google Form/Sheet.
---

## 7. Tài liệu tham khảo

-
