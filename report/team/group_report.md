# Báo cáo nhóm — Day 02 Discovery & Problem Framing

> Bản chung của nhóm, viết trên repo do nhóm trưởng fork. Không copy file này sang repo cá nhân.
> Template chi tiết và prompt mẫu: [docs/01-worksheet.md](../../docs/01-worksheet.md). Bài mẫu: [docs/02-deliverable-example.md](../../docs/02-deliverable-example.md).

## 1. Thông tin nhóm

- Tên nhóm:
- Thành viên: xem `TEAM.md`
- Candidate problem được chọn (1 câu):
- Quyết định cuối: Go / Not Yet / No-Go

---

## 2. Hội tụ nhóm (CP3)

### 2.1. Pitch

| # | Người đưa ra | Candidate (Job Story ngắn) | Actor | Bottleneck | Câu hỏi phản biện nhận được (ai hỏi) |
|---:|---|---|---|---|---|
| 1 | Võ Trần Công | Khi nhận yêu cầu xây dựng chatbot AI, tôi muốn hiểu cấu trúc dữ liệu Odoo nhanh hơn để xác định nguồn dữ liệu và phương án tích hợp | AI Engineer, BA, khách hàng | Khảo sát model, field và quan hệ dữ liệu mất 2–4 giờ/dự án | Chưa ghi nhận trong hồ sơ cá nhân |
| 2 | Võ Trần Công | Khi xây dựng pipeline RAG, tôi muốn xử lý bộ tài liệu PDF, DOCX, Excel nhanh hơn để giảm thời gian chuẩn bị dữ liệu | AI Engineer, Data Engineer | Đọc, phân loại, làm sạch và chia nhỏ tài liệu mất 3–5 giờ/bộ | Chưa ghi nhận trong hồ sơ cá nhân |
| 3 | Võ Trần Công | Khi AI Agent chạy sai, tôi muốn truy vết từng bước reasoning, tool call và API để tìm đúng nguyên nhân | AI Engineer, Backend Engineer, QA | Tái hiện lỗi và đọc log mất khoảng 30–60 phút/lỗi | Chưa ghi nhận trong hồ sơ cá nhân |
| 4 | Hà Văn Khánh Đạt | Khi thêm theme bàn phím mới, tôi muốn biết đủ asset cần chuẩn bị để không bị thiếu file khi build | Dev, designer | Rà tay từng file khoảng 30 phút/theme; vẫn có thể sót | Chưa ghi nhận trong hồ sơ cá nhân |
| 5 | Hà Văn Khánh Đạt | Khi theme bị báo thiếu file, tôi muốn biết ngay file và theme lỗi để không phải rà cả catalog 160 theme | Dev | Đối chiếu đường dẫn thủ công, có lỗi id 48, 87 và 97 đã ghi nhận | Chưa ghi nhận trong hồ sơ cá nhân |
| 6 | Hà Văn Khánh Đạt | Khi đóng gói ZIP, tôi muốn mỗi theme có đủ folder và reference để không phải gom file rời | Dev | Gom và copy thủ công mất khoảng 1–2 giờ/đợt 160 theme | Chưa ghi nhận trong hồ sơ cá nhân |
| 7 | Phan Đào Minh Quân | Khi gần deadline bài nhóm, tôi muốn biết ai đã làm gì và phần nào còn thiếu để hoàn thiện báo cáo đúng hạn | Thành viên điều phối, cả nhóm | Hỏi lại phần thiếu mất khoảng 15–30 phút/lần | Chưa ghi nhận trong hồ sơ cá nhân |
| 8 | Phan Đào Minh Quân | Khi chuẩn bị nộp bài, tôi muốn đối chiếu báo cáo với rubric để tránh thiếu mục hoặc sai format | Người kiểm tra cuối | Tìm phần tương ứng trong báo cáo mất khoảng 20–30 phút | Chưa ghi nhận trong hồ sơ cá nhân |
| 9 | Phan Đào Minh Quân | Khi cần nhớ quyết định cũ, tôi muốn tìm được quyết định và lý do để không tranh luận lại từ đầu | Cả nhóm | Mở và đọc nhiều thread mất khoảng 10–20 phút/lần | Chưa ghi nhận trong hồ sơ cá nhân |

### 2.2. Cluster

| Cluster | Các candidate | Pattern chung |
|---|---|---|
| A — Chuẩn bị và hiểu dữ liệu cho hệ thống AI | Công #1, Công #2, Đạt #1 | Nhiều nguồn dữ liệu/field/tài liệu cần đọc, phân loại và chuẩn hóa trước khi xây dựng hoặc tích hợp |
| B — Kiểm tra và vận hành asset/workflow kỹ thuật | Công #3, Đạt #2, Đạt #3 | Lỗi phát sinh trong workflow; cần truy vết, đối chiếu reference hoặc kiểm tra output trước khi giao |
| C — Điều phối và truy hồi thông tin nhóm | Quân #1, Quân #2, Quân #3 | Thông tin phân tán, phải tổng hợp hoặc tìm lại thủ công trước deadline |

### 2.3. Opportunity Solution Tree rút gọn

Gốc là **1 outcome**. Nhánh là **opportunity** (nhu cầu, pain), không phải tính năng hay công cụ.

```text
OUTCOME: Giảm thời gian xử lý thủ công và giảm lỗi trước khi hệ thống hoặc bài nộp được giao
├── Opportunity A: Nguồn dữ liệu và tài liệu đầu vào chưa được chuẩn hóa, khiến bước khảo sát/chuẩn bị kéo dài
├── Opportunity B: Lỗi trong workflow, reference hoặc log khó được phát hiện và truy nguyên sớm
└── Opportunity C: Thông tin nhóm phân tán, khiến việc tổng hợp, đối chiếu và tìm quyết định bị lặp lại
```

Những ý đã gạch bỏ vì là solution đội lốt opportunity:

- “Dùng AI để tự khảo sát Odoo”
- “Xây pipeline RAG tự động”
- “Tạo dashboard log cho Agent”
- “Viết script kiểm tra file asset”
- “Tạo chatbot quản lý tiến độ nhóm”

Đây là các hướng giải pháp; nhóm giữ lại pain và quy trình tương ứng để so sánh trước khi chọn công cụ.

### 2.4. Chấm điểm shortlist (1–5)

| Candidate | Actor rõ | Quy trình rõ | Pain có bằng chứng | Impact đo được | Vừa sức lab | So sánh được No AI/Rule/Workflow/Agent | Nhóm hiểu domain | Tổng |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Công #2 — Chuẩn bị tài liệu hỗn hợp cho RAG | 5 | 5 | 4 | 4 | 4 | 5 | 4 | 31 |
| Đạt #2 — Chẩn đoán file thiếu trong catalog | 5 | 5 | 5 | 5 | 5 | 5 | 5 | 35 |
| Quân #1 — Tổng hợp tiến độ và phần thiếu trước deadline | 5 | 4 | 2 | 4 | 5 | 4 | 4 | 28 |

Điểm “Pain có bằng chứng” được chấm theo nội dung hiện có trong ba báo cáo cá nhân: các lỗi asset của Đạt có ví dụ cụ thể; Công có baseline thời gian nhưng còn ghi cần xác nhận; Quân ghi rõ các số liệu là ước tính chưa có log.

**Candidate được chọn:** Tạm chọn **Đạt #2 — Khi một theme bị báo lỗi thiếu file, tôi muốn biết ngay file nào và theme nào để không phải rà cả catalog 160 theme**.

**Vì sao chọn:** Candidate có actor rõ, quy trình 3–7 bước, bottleneck cụ thể ở bước đối chiếu reference, impact đo được bằng thời gian và số lỗi, đồng thời có bằng chứng cụ thể về id 48, id 87 và id 97. Phương án No AI/Rule cũng rõ nên nhóm có thể kiểm tra giả thuyết đơn giản trước khi cân nhắc Workflow hoặc Agent.

**Vì sao loại các candidate còn lại:** Công #2 có pain đáng kể nhưng bottleneck “làm sạch” còn là giả thuyết và tiêu chí “đủ sạch” chưa chốt. Quân #1 có quy trình phù hợp nhưng số liệu hiện mới là ước tính, chưa có log hoặc kiểm chứng. Các card còn lại được giữ làm candidate dự phòng; Công #1 và Đạt #1 có thể gộp vào nhóm chuẩn hóa đầu vào, còn Đạt #3 gần cùng workflow với Đạt #2.

**Xử lý bất đồng (nếu có):** Chưa có biên bản bất đồng hoặc câu hỏi phản biện được ghi nhận trong các file cá nhân. Vì vậy, lựa chọn trên là quyết định tạm thời theo bảng điểm, cần xác nhận lại với cả ba thành viên trước CP4; không coi các câu hỏi ở cột Pitch là câu hỏi đã thực sự được hỏi.

---

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
