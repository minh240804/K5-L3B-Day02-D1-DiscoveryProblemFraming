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
| Pitch Problem Card | Trình bày các ý tưởng của bản thân, Tham gia phản biện và chấm điểm | Đưa ra được điểm số và kêt quả  |
| Phản biện bài của bạn khác | Câu hỏi tôi đã đặt: Chất lượng AC đo như thế nào? Edge cases AI sinh ra có đúng business logic không?, Phân quyền truy cập dữ liệu (RBAC) xử lý thế nào? | Đóng góp vào ý kiến của bài, đưa ra được 1 vài vấn đề  |
| Nhận phản biện | Câu hỏi tôi nhận được: Có bị Grab/Gojek chặn API/Anti-scraping không?, Khác gì các bộ lọc từ khóa nâng cao của TopCV, Rủi ro bảo mật OTP/Banking API là cực cao, liệu người dùng dám cấp quyền?| Tôi đã sửa gì: Cần phải xem xét về khả năng của các phương án, tuy mới chỉ là xác định bài toán nhưng cần cân nhác thêm  |
| Gom cluster / cây OST | Phân loại:   | |
| Chọn candidate problem |  |  |
| Kiểm chứng / research |  |  |
| Quy trình nhóm |  |  |
| Problem Statement |  |  |
| Mức can thiệp AI |  |  |
| Quyết định | Tổng hợp Value, Usability, Feasibility và Viability. Đưa kết quả cho dự án | Nhóm chọn được bài toán phù hợp |

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

**6.3. Tôi có đổi ý sau khi bị phản biện không? Kể một lần cụ thể.**

**6.4. Kết quả kiểm chứng (phỏng vấn/survey/research) có làm tôi bất ngờ không? Điều gì?**

**6.5. Điều khó nhất khi viết Problem Statement là gì?**

**6.6. Nếu làm lại, tôi sẽ đổi gì? Tôi sẽ phản biện nhóm mạnh hơn ở điểm nào?**

**6.7. Hiểu bài:** giải thích bằng 5–8 câu, không nhìn tài liệu, chuỗi *problem → quy trình → metric → boundary → mức can thiệp AI → quyết định* của bài nhóm mình.

---

## 7. Tài liệu tham khảo

-
