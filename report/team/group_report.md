# Báo cáo nhóm — Day 02 Discovery & Problem Framing

> Bản chung của nhóm, viết trên repo do nhóm trưởng fork. Không copy file này sang repo cá nhân.
> Template chi tiết và prompt mẫu: [docs/01-worksheet.md](../../docs/01-worksheet.md). Bài mẫu: [docs/02-deliverable-example.md](../../docs/02-deliverable-example.md).

## 1. Thông tin nhóm

- Tên nhóm:
- Thành viên: xem `TEAM.md`
- Candidate problem được chọn (1 câu):
- Quyết định cuối: Go / Not Yet / No-Go

---

# 2. HỘI TỤ NHÓM (CP3)

## 2.1. Pitch

| **#** | **Người đưa ra** | **Candidate (Job Story ngắn)**                                                                                           | **Actor**       | **Bottleneck**                                                                | **Câu hỏi phản biện nhận được (ai hỏi)**                                |
| ----- | ---------------- | ------------------------------------------------------------------------------------------------------------------------ | --------------- | ----------------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| 1     | Thành viên nhóm  | Khi họp xong, tôi muốn tạo User Story và AC từ ghi chú để Dev có thể triển khai kịp sprint.                              | BA, Dev         | Mất khoảng 2 tiếng để tổng hợp và viết tài liệu; riêng AC mất khoảng 40 phút. | Làm thế nào đánh giá chất lượng AC do AI tạo ra?                        |
| 2     | Thành viên nhóm  | Khi họp xong, tôi muốn gửi Meeting Minutes trong ngày để stakeholder xác nhận kịp thời.                                  | BA, Stakeholder | Mất 30–60 phút để sắp xếp ghi chú và tổng hợp nội dung.                       | Làm sao đảm bảo AI không bỏ sót quyết định hoặc phân công sai người?    |
| 3     | Thành viên nhóm  | Khi nhận tài liệu dài từ khách hàng, tôi muốn nhanh chóng nắm được các yêu cầu chính để chuẩn bị cho buổi họp tiếp theo. | BA              | Mất khoảng 2 tiếng đọc tài liệu 25–30 trang.                                  | Tóm tắt thế nào để không bỏ sót yêu cầu quan trọng?                     |
| 4     | Thành viên nhóm  | Khi Dev nhận User Story, tôi muốn họ hiểu đúng yêu cầu ngay lần đầu để hạn chế việc hỏi lại BA.                          | Dev, BA         | Dev phải hỏi lại để làm rõ yêu cầu, ước tính khoảng 1 lần/story.              | Có thể đo lường mức độ hiểu đúng yêu cầu như thế nào?                   |
| 5     | Thành viên nhóm  | Khi stakeholder thay đổi yêu cầu, tôi muốn xác định các tài liệu và Test Case bị ảnh hưởng để tránh bỏ sót.              | BA, QA, Dev     | Mất 30–60 phút/lần thay đổi để kiểm tra thủ công.                             | Làm sao xác định chính xác các thành phần có liên quan?                 |
| 6     | Thành viên nhóm  | Khi cần biết lý do của một quyết định cũ, tôi muốn tìm lại thông tin đã thống nhất để không phải họp lại từ đầu.         | BA, Dev, QA     | Mất 20–30 phút hoặc lâu hơn để tìm kiếm thông tin từ nhiều nguồn.             | Dữ liệu nằm ở nhiều nguồn và có phân quyền khác nhau thì xử lý thế nào? |
| 7     | Thành viên nhóm  | Khi QA kiểm thử, tôi muốn phát hiện sớm yêu cầu mâu thuẫn hoặc thiếu sót để tránh sửa lỗi muộn.                          | QA, Dev, BA     | Phát sinh khoảng 2 bug/sprint do hiểu sai yêu cầu (cần xác minh).             | Làm sao phân biệt lỗi do yêu cầu thiếu với lỗi do lập trình?            |
| 8     | Thành viên nhóm  | Khi backlog có nhiều yêu cầu, tôi muốn phân loại và đánh giá mức độ ưu tiên để tập trung vào các yêu cầu quan trọng.     | BA, PO          | Tốn thời gian trao đổi và sắp xếp backlog.                                    | AI dựa trên tiêu chí nào để đánh giá mức độ ưu tiên?                    |
| 9     | Chưa xác định    | Chưa bổ sung                                                                                                             | Chưa xác định   | Chưa xác định                                                                 | Chưa xác định                                                           |

**Nhận xét sau Pitch:**

Các ý tưởng tập trung vào ba nhóm công việc chính:

- Tạo lập và chuẩn hóa tài liệu nghiệp vụ.
- Tìm kiếm, quản lý và khai thác thông tin dự án.
- Kiểm soát chất lượng và quản lý yêu cầu.

## 2.2. Cluster

Sau khi tổng hợp các ý tưởng, nhóm chia thành 3 cụm theo nhu cầu nghiệp vụ thay vì chia theo công nghệ hoặc giải pháp AI.

| **Cluster**                                        | **Các candidate** | **Pattern chung**                                                                                                                                              |
| -------------------------------------------------- | ----------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| A. Requirement Documentation                       | #1, #2, #3        | BA phải đọc, tổng hợp và chuyển đổi thông tin từ cuộc họp hoặc tài liệu thành các đầu ra nghiệp vụ. Công việc lặp lại, tốn thời gian và cần kiểm tra thủ công. |
| B. Requirement Traceability & Knowledge Management | #5, #6            | Thông tin dự án nằm rải rác, khó truy xuất và khó xác định mối liên hệ giữa các yêu cầu, quyết định và tài liệu.                                               |
| C. Requirement Quality & Delivery                  | #4, #7, #8        | Dev, QA và PO gặp khó khăn trong việc hiểu đúng, kiểm soát chất lượng và ưu tiên các yêu cầu.                                                                  |

**Pattern chung của cả 3 Cluster:**

BA và các thành viên dự án đang dành nhiều thời gian cho việc xử lý thông tin thủ công, trong khi thông tin thường phân tán, thiếu liên kết và cần được kiểm tra qua nhiều bước trước khi có thể sử dụng.

## 2.3. Opportunity Solution Tree rút gọn

**Outcome:**

Giảm thời gian xử lý thông tin và hạn chế sai sót trong quy trình quản lý yêu cầu của BA.

```
OUTCOME:
Giảm thời gian xử lý thông tin và hạn chế sai sót trong
quy trình quản lý yêu cầu của BA.
│
├── Opportunity A: Giảm thời gian chuyển đổi thông tin
│   thành tài liệu nghiệp vụ
│   ├── Tạo User Story và Acceptance Criteria sau họp (#1)
│   ├── Tổng hợp và gửi Meeting Minutes (#2)
│   └── Đọc, tổng hợp yêu cầu từ tài liệu dài (#3)
│
├── Opportunity B: Tăng khả năng truy xuất và liên kết
│   thông tin dự án
│   ├── Xác định ảnh hưởng khi yêu cầu thay đổi (#5)
│   └── Tìm kiếm lịch sử và lý do quyết định cũ (#6)
│
└── Opportunity C: Nâng cao chất lượng và hiệu quả
    quản lý yêu cầu
    ├── Giúp Dev hiểu đúng yêu cầu (#4)
    ├── Phát hiện yêu cầu mâu thuẫn hoặc thiếu sót (#7)
    └── Hỗ trợ phân loại và ưu tiên Backlog (#8)
```

**Những ý đã gạch bỏ vì là solution đội lốt opportunity:**

- Sử dụng LLM để tạo User Story và Acceptance Criteria.
- Xây dựng chatbot AI để tìm kiếm quyết định cũ.
- Sử dụng RAG để truy xuất tài liệu dự án.
- Xây dựng Agent tự động phân loại và ưu tiên Backlog.

**Lý do:** Đây là các giải pháp hoặc công nghệ được đề xuất để giải quyết vấn đề, không phải nhu cầu hay nỗi đau thực tế của người dùng.

## 2.4. Chấm điểm shortlist (1–5)

Nhóm chọn 3 candidate đại diện cho 3 hướng bài toán khác nhau để đánh giá sâu hơn.

| **Candidate**            | **Actor rõ** | **Quy trình rõ** | **Pain có bằng chứng** | **Impact đo được** | **Vừa sức lab** | **So sánh được No AI/Rule/Workflow/Agent** | **Nhóm hiểu domain** | **Tổng**  |
| ------------------------ | ------------ | ---------------- | ---------------------- | ------------------ | --------------- | ------------------------------------------ | -------------------- | --------- |
| #1 – Tạo User Story + AC | 5            | 5                | 4                      | 4                  | 5               | 5                                          | 5                    | **33/35** |
| #2 – Tạo Meeting Minutes | 5            | 5                | 4                      | 3                  | 5               | 5                                          | 5                    | **32/35** |
| #6 – Tìm quyết định cũ   | 5            | 3                | 3                      | 4                  | 3               | 4                                          | 4                    | **26/35** |

*Điểm số là đánh giá sơ bộ của nhóm dựa trên thông tin hiện có, chưa phải kết quả khảo sát định lượng.*

**Candidate được chọn:**

\#1 – Tự động hỗ trợ BA tạo User Story và Acceptance Criteria sau cuộc họp.

**Vì sao chọn:**

- Actor rõ ràng: BA là người trực tiếp thực hiện công việc.
- Quy trình hiện tại đã được mô tả cụ thể với 7 bước, xác định được bottleneck ở bước viết Acceptance Criteria.
- Có baseline tương đối rõ: khoảng 120 phút cho một buổi họp, trong đó viết AC mất khoảng 40 phút.
- Có thể đo lường hiệu quả bằng thời gian hoàn thành tài liệu và tỷ lệ AC đạt yêu cầu sau khi review.
- Phạm vi triển khai phù hợp với thời gian của lab: có thể sử dụng transcript hoặc ghi chú đầu vào để tạo bản nháp User Story và AC, sau đó BA kiểm tra.

**Vì sao loại các candidate còn lại:**

- **#2 – Meeting Minutes:** Có tính lặp lại và dễ triển khai, nhưng có phần trùng lặp với #1 về dữ liệu đầu vào và quy trình xử lý sau cuộc họp. Có thể xem xét tích hợp thành đầu ra bổ sung của cùng một workflow.
- **#6 – Tìm quyết định cũ:** Có tiềm năng ứng dụng AI và ảnh hưởng đến nhiều thành viên, nhưng phạm vi dữ liệu rộng, nằm ở nhiều nguồn khác nhau và cần giải quyết bài toán phân quyền truy cập. Khó triển khai đầy đủ trong thời gian lab.
- **Các candidate còn lại:** Có giá trị nhưng cần thêm dữ liệu thực tế để chứng minh mức độ ảnh hưởng, xác định tiêu chí đánh giá hoặc giới hạn phạm vi triển khai.

**Xử lý bất đồng (nếu có):**

Nhóm thống nhất sử dụng các tiêu chí chấm điểm chung gồm: độ rõ ràng của Actor, quy trình, bằng chứng về pain point, khả năng đo lường impact và tính khả thi khi triển khai. Các thành viên đánh giá từng candidate, so sánh tổng điểm và thảo luận những tiêu chí có sự khác biệt. Cuối cùng, nhóm ưu tiên bài toán có quy trình rõ, dữ liệu đầu vào khả thi và có thể đo lường hiệu quả sau triển khai.

*Nếu nhóm chưa thực sự có bất đồng, có thể ghi: Không phát sinh bất đồng lớn; các thành viên thống nhất lựa chọn dựa trên bảng tiêu chí đánh giá.*



---



## 2.5. Liên kết CP3 với Top 3 Problem Cards ở CP2

| **Rank** | **Candidate**            | **Cluster** | **Vai trò trong nhóm bài toán**            |
| -------- | ------------------------ | ----------- | ------------------------------------------ |
| 1        | #1 – Tạo User Story + AC | A           | Bài toán ưu tiên triển khai                |
| 2        | #2 – Tạo Meeting Minutes | A           | Bài toán có thể tích hợp cùng workflow #1  |
| 3        | #6 – Tìm quyết định cũ   | B           | Bài toán mở rộng về quản lý tri thức dự án |

**Định hướng tổng thể:**

Nhóm lựa chọn #1 làm bài toán triển khai chính trong lab. #2 và #6 vẫn được giữ trong Top 3 vì có giá trị thực tế, nhưng chưa nhất thiết phải triển khai đồng thời.

## 3. Liên kết với Top 3 Problem Cards (CP2)

### Problem Card #1 – Tạo User Story và Acceptance Criteria sau cuộc họp

| **Trường**              | **Nội dung**                                                                                                                                                                                                 |
| ----------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Job Story               | Khi vừa họp xong với stakeholder, tôi muốn có sẵn User Story và AC, để Dev kịp đưa vào sprint planning.                                                                                                      |
| Actor                   | BA phụ trách ghi nhận và sắp xếp yêu cầu.                                                                                                                                                                    |
| Thời điểm / bối cảnh    | Trong vòng 1 ngày sau buổi họp, trước khi sprint planning.                                                                                                                                                   |
| Quy trình hiện tại      | 1. Sắp xếp ghi chú/nghe lại recording. 2. Gom yêu cầu theo chủ đề. 3. Viết User Story. 4. Viết AC (gồm edge case). 5. Đối chiếu tài liệu cũ, tìm mâu thuẫn. 6. Nhập vào Jira. 7. Gửi Dev/stakeholder review. |
| Bottleneck              | Bước 4, viết AC: khoảng 40 phút, hay thiếu edge case và bị Dev hỏi lại.                                                                                                                                      |
| Impact                  | Khoảng 2 tiếng/buổi họp; 2 buổi/tuần thì cần 4 tiếng/tuần/BA.                                                                                                                                                |
| Success metric          | Tổng thời gian từ 2 tiếng xuống dưới 60 phút.                                                                                                                                                                |
| Phương án không dùng AI | Tạo sẵn template cho User Story + checklist AC (Given/When/Then) + checklist edge case.                                                                                                                      |
| Giả thuyết về AI        | AI soạn nháp User Story + AC từ ghi chú đã dọn, BA kiểm tra, bổ sung edge case rồi mới nhập Jira.                                                                                                            |
| Cảm nhận nhanh          | Workflow                                                                                                                                                                                                     |

**Quy trình nháp hiện tại:**

```
HIỆN TẠI - 120 phút

[1. Sắp xếp ghi chú: 10']
          ↓
[2. Gom theo chủ đề: 15']
          ↓
[3. Viết User Story: 15']
          ↓
[4. Viết AC (gồm edge case): 40'] ← BOTTLENECK
          ↓
[5. Đối chiếu tài liệu cũ: 25']
          ↓
[6. Nhập Jira: 10']
          ↓
[7. Gửi Dev/stakeholder review: 5']
```

### Problem Card #2 – Tạo và gửi Meeting Minutes

| **Trường**              | **Nội dung**                                                                                                                                                                                                                                                                                                                             |
| ----------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Job Story               | Khi họp xong, tôi muốn gửi Meeting Minutes trong ngày, để stakeholder xác nhận kịp.                                                                                                                                                                                                                                                      |
| Actor                   | BA phụ trách ghi chép, tổng hợp nội dung và gửi biên bản cuộc họp cho stakeholder.                                                                                                                                                                                                                                                       |
| Thời điểm / bối cảnh    | Ngay sau khi kết thúc cuộc họp, thường trong ngày làm việc, khi các bên vẫn còn nhớ nội dung trao đổi.                                                                                                                                                                                                                                   |
| Quy trình hiện tại      | 1. Tổng hợp ghi chú trong cuộc họp. 2. Nghe lại recording nếu có nội dung chưa rõ. 3. Phân loại nội dung theo chủ đề. 4. Tổng hợp các vấn đề đã thảo luận và quyết định được thống nhất. 5. Ghi nhận yêu cầu, người phụ trách và deadline. 6. Kiểm tra lại nội dung và định dạng Meeting Minutes. 7. Gửi email cho stakeholder xác nhận. |
| Bottleneck              | Bước 2–5: Sắp xếp lại ghi chú, đối chiếu recording và tổng hợp nội dung. Mất khoảng 30–60 phút cho mỗi buổi họp.                                                                                                                                                                                                                         |
| Impact                  | Meeting Minutes được gửi chậm, stakeholder có thể quên nội dung đã thống nhất hoặc hiểu khác nhau về trách nhiệm và deadline. BA mất thời gian cho công việc tổng hợp lặp lại sau mỗi cuộc họp.                                                                                                                                          |
| Success metric          | Thời gian tạo và gửi Meeting Minutes từ 30–60 phút xuống dưới 15 phút/buổi họp; đảm bảo gửi trong ngày và không bỏ sót quyết định, Action Items quan trọng.                                                                                                                                                                              |
| Phương án không dùng AI | Sử dụng template Meeting Minutes cố định, checklist các nội dung cần ghi nhận và công cụ ghi âm/chuyển giọng nói thành văn bản.                                                                                                                                                                                                          |
| Giả thuyết về AI        | AI tiếp nhận ghi chú cuộc họp, tự động phân loại nội dung, trích xuất quyết định, người phụ trách và deadline, sau đó tạo bản nháp Meeting Minutes. BA kiểm tra và gửi stakeholder xác nhận.                                                                                                                                             |
| Cảm nhận nhanh          | Workflow                                                                                                                                                                                                                                                                                                                                 |

**Quy trình nháp hiện tại:**

```
HIỆN TẠI - 30–60 phút

[1. Tổng hợp ghi chú: 10']
          ↓
[2. Nghe lại recording nếu cần: 10']
          ↓
[3. Phân loại nội dung: 10']
          ↓
[4. Tổng hợp quyết định và Action Items: 15']
          ↓
[5. Kiểm tra, định dạng Meeting Minutes: 10']
          ↓
[6. Gửi Stakeholder xác nhận: 5']
```

*Lưu ý: Phân bổ thời gian trên là giả định minh họa, cần đo thực tế để xác nhận.*

### Problem Card #3 – Tìm kiếm lịch sử quyết định nghiệp vụ

| **Trường**              | **Nội dung**                                                                                                                                                                                                                                                                                                                                                                                 |
| ----------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Job Story               | Khi cần biết vì sao từng chốt phương án A, tôi muốn tìm lại quyết định cũ, để không phải họp lại từ đầu.                                                                                                                                                                                                                                                                                     |
| Actor                   | BA, Dev, QA và các thành viên liên quan đến dự án cần tra cứu thông tin nghiệp vụ đã được thống nhất.                                                                                                                                                                                                                                                                                        |
| Thời điểm / bối cảnh    | Khi phát sinh yêu cầu mới, cần kiểm tra logic nghiệp vụ cũ, có thành viên mới tham gia dự án hoặc cần giải thích lý do lựa chọn một phương án trước đây.                                                                                                                                                                                                                                     |
| Quy trình hiện tại      | 1. Xác định vấn đề hoặc quyết định nghiệp vụ cần tìm hiểu. 2. Nhớ lại thời điểm hoặc những người tham gia thảo luận. 3. Tìm kiếm trong Meeting Minutes, email, chat hoặc tài liệu dự án. 4. Đọc và đối chiếu các thông tin tìm được. 5. Xác định quyết định cuối cùng và lý do lựa chọn. 6. Nếu không tìm được, hỏi BA hoặc stakeholder từng tham gia. 7. Tổng hợp lại thông tin để sử dụng. |
| Bottleneck              | Bước 3–4: Tìm kiếm và đối chiếu thông tin từ nhiều nguồn khác nhau. Mất khoảng 20–30 phút hoặc lâu hơn cho mỗi lần tìm kiếm.                                                                                                                                                                                                                                                                 |
| Impact                  | BA và các thành viên phải mất thời gian tìm kiếm hoặc hỏi lại người cũ. Có thể phải tổ chức họp lại để làm rõ những vấn đề đã từng được thống nhất. Nguy cơ đưa ra quyết định không nhất quán với logic nghiệp vụ trước đó.                                                                                                                                                                  |
| Success metric          | Thời gian tìm kiếm thông tin từ 30–60 phút xuống dưới 15 phút/lần; tăng tỷ lệ truy xuất được quyết định kèm nguồn tham chiếu và lý do lựa chọn.                                                                                                                                                                                                                                              |
| Phương án không dùng AI | Xây dựng kho lưu trữ tập trung cho Meeting Minutes, email và tài liệu dự án; chuẩn hóa cách đặt tên file, gắn tag theo dự án, module, chủ đề và ngày tháng; lập Decision Log ghi nhận quyết định, lý do và người phê duyệt.                                                                                                                                                                  |
| Giả thuyết về AI        | Xây dựng AI Business Knowledge Assistant sử dụng RAG để tìm kiếm thông tin từ Meeting Minutes, email và tài liệu dự án. Người dùng đặt câu hỏi bằng ngôn ngữ tự nhiên, hệ thống tìm các thông tin liên quan và tổng hợp câu trả lời kèm nguồn trích dẫn, thời điểm và bối cảnh quyết định.                                                                                                   |
| Cảm nhận nhanh          | Agent                                                                                                                                                                                                                                                                                                                                                                                        |

**Quy trình nháp hiện tại:**

```
HIỆN TẠI - 20–30 phút hoặc lâu hơn

[1. Xác định quyết định cần tìm]
          ↓
[2. Xác định thời gian / người tham gia]
          ↓
[3. Tìm kiếm trong Email / Chat / Documents]
          ↓
[4. Đọc và đối chiếu thông tin]
          ↓
[5. Xác định quyết định cuối cùng]
          ↓
     Tìm thấy thông tin?
        /         \
      Có           Không
      ↓              ↓
[6. Tổng hợp]   [7. Hỏi BA / Stakeholder cũ]
      ↓     
```


## 3. Kiểm chứng + research giải pháp đã có (CP4)

### 3.1. Assumption Map

| # | Giả định | Loại (Value / Usability / Feasibility / Viability) | Quan trọng (1–5) | Đã có bằng chứng (1–5) | Kiểm chứng trước? |
|---:|---|---|---:|---:|---|
| 1 | | | | | |
| 2 | | | | | |
| 3 | | | | | |
| 4 | | | | | |
| 5 | | | | | |
| 6 | | | | | |

*Điền 4–6 giả định; xóa dòng thừa.*

Giả định nhóm kiểm chứng trong buổi này:

### 3.2. Kiểm chứng

Cách đã dùng: Phỏng vấn / Survey / Log, ticket, review

Interview snapshot (mỗi buổi phỏng vấn một bảng, hoặc đặt file trong `report/assets/cp4-interview-snapshot-N.md`):

| Trường | Nội dung |
|---|---|
| Người được hỏi (vai trò, không ghi tên thật) | |
| Câu nói đáng nhớ nhất (nguyên văn) | |
| Lần gần nhất gặp vấn đề này: chuyện gì đã xảy ra? | |
| Hiện đang xử lý bằng cách nào (workaround)? | |
| Mất bao lâu, bao lần? | |
| Insight / opportunity rút ra | |

Tổng hợp:

| Nguồn | Số người / số mẫu | Tín hiệu xác nhận | Tín hiệu phản bác |
|---|---:|---|---|
| | | | |

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
