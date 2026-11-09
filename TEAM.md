# Team

## Thông tin nhóm

- Tên nhóm: D1
- Candidate problem nhóm chọn (1 câu): Khi nhận hàng trăm tin nhắn Zalo lớp, phụ huynh muốn 1 bản tóm tắt việc học/tiền bạc duy nhất.
- Quyết định cuối (Go / Not Yet / No-Go): GO (Triển khai Pilot)

## Thành viên

| STT | Họ và tên | MSSV | Vai trò trong nhóm | Tài khoản GitHub |
|---:|---|---|---|---|
| 1 | Vũ Quang Minh |  | Điều phối thời gian, phụ trách research, vẽ quy trình hiện tại |  |
| 2 | Hoàng Minh Diệp |  | Người phản biện chính, phụ trách kiểm chứng, phân tích mức can thiệp AI |  |
| 3 | Nguyễn Hoàng Gia An |  | Ghi chép, phụ trách kiểm chứng, viết Problem Statement v0 & tiêu chí đánh giá |  |
| 4 |  |  |  |  |

Không ghi email hay số điện thoại vào bảng này, vì repo có thể để public.

Gợi ý vai trò (một người có thể giữ nhiều vai): điều phối thời gian, ghi chép, người phản biện chính, phụ trách kiểm chứng (phỏng vấn/survey), phụ trách research, vẽ quy trình, viết Problem Statement.

## Phân công theo checkpoint

| Checkpoint | Người chính | Người hỗ trợ | Sản phẩm |
|---|---|---|---|
| CP3 — Hội tụ nhóm | Nguyễn Hoàng Gia An | Vũ Quang Minh, Hoàng Minh Diệp | Cluster, cây OST, bảng chấm điểm |
| CP4 — Kiểm chứng | Hoàng Minh Diệp | Nguyễn Hoàng Gia An | Assumption map, snapshot phỏng vấn |
| CP4 — Research | Vũ Quang Minh | Nguyễn Hoàng Gia An | Bảng research có link (mục 3.3) |
| CP5 — Quy trình trước/sau | Vũ Quang Minh (quy trình hiện tại) + Hoàng Minh Diệp (quy trình tương lai) | Nguyễn Hoàng Gia An (boundary) | Quy trình + bảng before/after |
| CP5 — Problem Statement v0 | Nguyễn Hoàng Gia An | Hoàng Minh Diệp | Problem Statement v0 |
| CP6 — Mức can thiệp + Problem Statement v1 | Hoàng Minh Diệp (ma trận, so sánh 4 mức) + Vũ Quang Minh (AI Canvas, Google PAIR) + Nguyễn Hoàng Gia An (PS v1, eval) | Cả nhóm | Ma trận, AI Canvas, eval, Problem Statement v1 |
| CP6 — Quyết định | Nguyễn Hoàng Gia An (kết luận GO) + Hoàng Minh Diệp (4 rủi ro) + Vũ Quang Minh (ngưỡng dừng, pilot) | Cả nhóm | 4 rủi ro + Go/Not Yet/No-Go |

## Cá nhân

Mỗi thành viên thêm một mục theo mẫu dưới đây, tiêu đề là `HoVaTen-MSSV`.

### Vũ Quang Minh

**Phần việc phụ trách:**

- Điều phối thời gian, phụ trách research giải pháp đã có
- Vẽ quy trình hiện tại (mục 4.1)
- Xây dựng AI Canvas và trả lời 2 câu hỏi Google PAIR

**Đóng góp cụ thể** (mình đã làm gì, ra sản phẩm gì):

- Pitch 3 candidate #4 (So sánh giá xe), #5 (Matching Job & CV), #6 (Quản lý chi tiêu)
- Phản biện: đặt câu hỏi cho #8 ("chỉ cần PowerShell/Intune, có cần AI không?") và #4 ("có bị Grab/Gojek chặn API không?")
- Nhận phản biện cho #1 và #6 (chất lượng AC, rủi ro OTP/banking)
- Research 4 công cụ/case: Zalo 1 chiều, eNetViet/SMAS, quy tắc nhóm chat, ghim tin nhắn
- Xây dựng quy trình hiện tại 5 bước, xác định bottleneck bước 2 (10 phút/tối)
- Đóng góp Problem Statement v1 (Actor mở rộng: Phụ huynh + GVCN + Học sinh)
- Xây dựng AI Canvas (Prediction/Judgment/Action/Outcome) và chọn Augment, ưu tiên Recall
- Đề xuất ngưỡng dừng Pivot/Drop và phạm vi pilot (2–3 lớp, ~100 phụ huynh)

**Bằng chứng** (phần nào trong `group_report.md`, file nào trong `report/assets/`, commit nào):

- `group_report.md`: mục 2.1 (candidate #4–6), 2.4 (chấm điểm), 3.3 (bảng research), 4.1 (quy trình hiện tại), 6.3 (AI Canvas), 6.4 (Google PAIR), 7.1 (PS v1), 8.2 (ngưỡng dừng)

**Điều mình học được từ phần nhóm:**

- Cách phân biệt rõ "solution đội lốt opportunity" và opportunity thật
- Cách chọn giữa No AI / Rule / Workflow / Agent dựa trên bản chất dữ liệu đầu vào
- Tầm quan trọng của việc ưu tiên Recall khi sai sót gây hậu quả thật cho người dùng

---

### Hoàng Minh Diệp

**Phần việc phụ trách:**

- Người phản biện chính
- Phụ trách kiểm chứng (phỏng vấn phụ huynh, thu thập tín hiệu xác nhận/phản bác)
- Phân tích ma trận độ mơ hồ × độ phức tạp và so sánh 4 mức can thiệp AI
- Đánh giá 4 rủi ro (Value/Usability/Feasibility/Viability)

**Đóng góp cụ thể** (mình đã làm gì, ra sản phẩm gì):

- Pitch 3 candidate #1 (BA AC Generator), #2 (Meeting Minutes), #3 (Decision Finder)
- Phản biện: đặt câu hỏi cho #7 ("OCR chữ viết tay mờ có chính xác không?") và #9 ("app ngân hàng can thiệp cuộc gọi riêng tư?")
- Nhận phản biện cho #8 và #2 (PowerShell đủ chưa, khác gì Whisper/Notion AI)
- Đóng góp candidate vào Cluster A (BA Operations), xây dựng OST nhánh Opportunity B
- Phụ trách kiểm chứng: tham gia phỏng vấn 2 phụ huynh, cung cấp tín hiệu xác nhận pain point cho #7
- Xây dựng quy trình tương lai 7 bước (Rule → AI → Rule → Human)
- Phân tích ma trận Medium Ambiguity × Medium Complexity, so sánh 4 mức → chọn Workflow
- Đánh giá 4 rủi ro trong mục 8.1

**Bằng chứng** (phần nào trong `group_report.md`, file nào trong `report/assets/`, commit nào):

- `group_report.md`: mục 2.1 (candidate #1–3), 2.2 (Cluster A), 2.3 (OST Opportunity B), 2.4 (chấm điểm), 3.2 (kiểm chứng phỏng vấn), 4.2 (quy trình tương lai), 6.1–6.2 (ma trận, so sánh 4 mức), 8.1 (4 rủi ro)

**Điều mình học được từ phần nhóm:**

- Cách phản biện một candidate mà không phá vỡ không khí nhóm
- Cách xác định đúng mức can thiệp AI thay vì mặc định chọn Agent
- Cách đặt tiêu chí đánh giá (eval) gắn với rủi ro thực tế của người dùng

---

### Nguyễn Hoàng Gia An

**Phần việc phụ trách:**

- Ghi chép, phụ trách kiểm chứng (tổng hợp snapshot phỏng vấn)
- Viết Problem Statement v0 và tiêu chí đánh giá đầu ra AI (mục 7.2–7.3)
- Trình bày lý do chọn candidate #7 và kết luận GO

**Đóng góp cụ thể** (mình đã làm gì, ra sản phẩm gì):

- Pitch 3 candidate #7 (Zalo Parent Assistant), #8 (IT Setup Automation), #9 (Anti-Fraud Financial) — #7 đạt 34 điểm cao nhất
- Phản biện: đặt câu hỏi cho #2 ("khác gì Whisper/Notion AI?") và #5 ("khác gì bộ lọc TopCV?")
- Nhận phản biện cho #7 (rủi ro OCR chữ viết tay) → đưa vào tiêu chí đánh giá
- Đóng góp candidate vào Cluster C (Safety & Automation), xây dựng OST nhánh Opportunity A
- Phụ trách kiểm chứng: phỏng vấn Chị H.T.Hương, tổng hợp interview snapshot và insight "cần tách biệt thông báo chính thức khỏi luồng thảo luận"
- Viết Problem Statement v0
- Xây dựng bảng phân định trách nhiệm & boundary + 4 phương án fallback
- Xây dựng bảng thay đổi v0 → v1 và 4 tiêu chí đánh giá đầu ra AI
- Trình bày kết luận GO (Pilot) và lý do

**Bằng chứng** (phần nào trong `group_report.md`, file nào trong `report/assets/`, commit nào):

- `group_report.md`: mục 2.1 (candidate #7–9), 2.2 (Cluster C), 2.3 (OST Opportunity A), 2.4 (chấm điểm + lý do chọn #7), 3.2 (interview snapshot), 4.2 (boundary + fallback), 5 (PS v0), 7.2–7.3 (thay đổi v0→v1, eval), 8.2 (kết luận GO)

**Điều mình học được từ phần nhóm:**

- Cách chuyển insight phỏng vấn thành tiêu chí đánh giá cụ thể
- Cách viết Problem Statement có thể đo lường được (baseline → target)
- Cách xác định boundary AI vs con người (Human-in-the-loop) trong bài toán có yếu tố tiền bạc

---

## Ghi chú

- Slot STT 4 trong `TEAM.md` để trống vì báo cáo chỉ thể hiện 3 thành viên — nếu nhóm có thành viên thứ 4 thực tế (ví dụ "Thành viên 4" xuất hiện trong cột "ai hỏi" ở mục 2.1), cần bổ sung tên và chia lại phần "Nhận phản biện" cho người đó.
- Các câu hỏi phản biện ghi "Thành viên 4" trong báo cáo (về RBAC cho #3 và OTP/banking cho #6) hiện được gán cho nhóm chung, chưa gán riêng cho ai — nếu có thành viên 4, nên giao phần này cho họ để tránh trùng với 3 người trên.