# Báo cáo cá nhân — 2A202604026_VoTranCong

> Đổi tên file theo quy tắc `MSSV_HoTen.md`, ví dụ `20241234_NguyenVanAn.md` (MSSV trước, dấu `_`, họ tên viết liền không dấu). Sửa cả dòng tiêu đề phía trên cho khớp.
> Template chi tiết và prompt mẫu cho từng mục: [docs/01-worksheet.md](../../docs/01-worksheet.md).
> Mỗi thành viên một file trong `report/individual/` trên repo nhóm: copy template này thành file mới, điền, rồi commit bằng tài khoản GitHub của bạn. Không viết hộ người khác.

## 1. Thông tin học viên

- Họ tên: Võ Trần Công
- MSSV: 2A202604026
- Email trường (không bắt buộc, repo có thể để public):
- Tên nhóm: T075
- Link repo nhóm: https://github.com/Shirou191/K5-L3B-DAY02-T075-DiscoveryProblemFraming

---

## 2. Scan problem (CP1)

Lăng kính: **Lặp lại** · **Tốn thời gian** · **Cần đọc, tổng hợp nhiều thông tin** · **Pain từ người khác**.

| # | Lăng kính | Job Story | Ai chịu ảnh hưởng? | Dấu hiệu thật (thời gian, tần suất, số người, bằng chứng) |
|---:|---|---|---|---|
| 1 | Lặp lại | Khi nhận yêu cầu xây dựng hệ thống trả lời khách hàng dựa trên dữ liệu Odoo, tôi muốn hiểu cấu trúc dữ liệu Odoo nhanh hơn để xác định nguồn dữ liệu và phương án tích hợp | AI Engineer, BA, khách hàng | Mỗi dự án mất 2–4 giờ khảo sát model, field và quan hệ dữ liệu Odoo. |
| 2 | Tốn thời gian | Khi chuẩn bị bộ tài liệu PDF, DOCX, Excel để hệ thống tìm kiếm theo nội dung, tôi muốn xử lý chúng nhanh hơn để giảm thời gian chuẩn bị dữ liệu | AI Engineer, Data Engineer | Mất 3–5 giờ xử lý một bộ tài liệu hỗn hợp PDF, DOCX, Excel. |
| 3 | Tốn thời gian | Khi một quy trình tự động chạy sai, tôi muốn truy vết từng bước xử lý, lời gọi công cụ và kết quả API để tìm đúng nguyên nhân | AI Engineer, Backend Engineer, QA | Mất 30–60 phút để tái hiện và tìm nguyên nhân một lỗi Agent khó tái hiện. |
| 4 | Cần đọc, tổng hợp nhiều thông tin | Khi khách hàng muốn tra cứu dữ liệu nội bộ qua một hệ thống trả lời, tôi muốn xác định chính xác quyền truy cập của từng người dùng và phòng ban, để thông tin không bị trả ra ngoài phạm vi được phép. | AI Engineer, khách hàng, IT Admin | Phải xử lý nhiều trường hợp phân quyền theo user, department và role; một lỗi phân quyền có thể làm lộ dữ liệu nội bộ. Ước tính: 3–5 dự án có phân quyền, mỗi dự án mất 4–8 giờ cấu hình. |
| 5 | Lặp lại | Khi tích hợp hệ thống tự động với Odoo và các ứng dụng bên ngoài, tôi muốn không phải viết lại logic gọi API, xác thực, thử lại và ghi log cho từng dự án, để tiết kiệm thời gian tích hợp. | AI Engineer, Backend Engineer, khách hàng | Nhiều dự án phải viết lại các đoạn code gọi API, xử lý token và retry. Ước tính: 1–3 dự án phải viết lại, mỗi dự án mất 6–10 giờ. |
| 6 | Cần đọc, tổng hợp nhiều thông tin | Khi cần chọn mô hình ngôn ngữ cho một dự án, tôi muốn so sánh được độ chính xác, độ trễ và chi phí trên dữ liệu và phần cứng thực tế, để chọn mô hình phù hợp mà không phải chạy nhiều thử nghiệm thủ công. | AI Engineer, Tech Lead, khách hàng | Mỗi lần đánh giá model phải chạy nhiều thử nghiệm thủ công; kết quả chưa được chuẩn hóa giữa các dự án. Ước tính: 2–4 lần đánh giá mỗi quý, mỗi lần 8–16 giờ (khoảng 1–2 ngày công). |
| 7 | Pain từ người khác | Khi bàn giao tính năng mới cho Backend Engineer hoặc Frontend Engineer, họ muốn có API contract, schema và tài liệu tích hợp rõ ràng, để kết nối hệ thống mà không phải hỏi lại nhiều lần. | AI Engineer, Backend Engineer, Frontend Engineer | Phát sinh 2–3 vòng trao đổi để làm rõ request, response, streaming và error handling. |
| 8 | Tốn thời gian | Khi triển khai một hệ thống lên môi trường production, tôi muốn có quy trình đóng gói, cấu hình và triển khai thống nhất, để giảm thời gian thiết lập và tránh lỗi khác biệt giữa local, staging và production. | AI Engineer, DevOps, khách hàng | Mỗi môi trường cần cấu hình thủ công; thường mất 1–3 giờ để xử lý lỗi phụ thuộc và cấu hình. |
| 9 | Pain từ người khác | Khi khách hàng nhận được câu trả lời sai từ hệ thống, họ muốn phản ánh được lỗi và có người xem xét, để vấn đề được phát hiện và cải thiện thay vì chỉ trao đổi thủ công. | Khách hàng, AI Engineer, Product Owner | Feedback đang phân tán qua Slack, email hoặc ticket; khó thống kê tỷ lệ câu trả lời sai và nguyên nhân. Ước tính: 5–15 phản hồi mỗi tuần, qua 3 kênh (Slack, email, ticket). |
| 10 | Lặp lại | Khi cần bảo trì nhiều hệ thống đã triển khai cho khách hàng, tôi muốn nắm được tình trạng từng hệ thống (API, mô hình, cơ sở dữ liệu vector, mức dùng token, độ trễ) ở một chỗ, để phát hiện sự cố trước khi ảnh hưởng hoạt động của doanh nghiệp. | AI Engineer, DevOps, khách hàng | Phải kiểm tra log và từng service riêng lẻ; chưa có dashboard tổng hợp tình trạng các hệ thống AI. Ước tính: 5–10 hệ thống cần bảo trì, mỗi hệ thống mất 15–30 phút mỗi lần kiểm tra. |

**Nếu có dùng AI để gợi ý thêm:** 10 problem do tôi tự viết từ công việc của mình; tôi không dùng AI để gợi ý thêm problem. AI chỉ được dùng để duyệt bảng theo tiêu chí CP1 (xem mục 5), nên không có ý nào từ AI để giữ hoặc bỏ.

---

## 3. Top 3 Problem Cards + quy trình nháp (CP2)

### Bảng chọn top 3

Thứ tự khớp với bảng pitch trong báo cáo nhóm (Công #1, #2, #3).

| Rank | Problem | Vì sao chọn | Điều còn chưa chắc |
|---:|---|---|---|
| 1 | Khảo sát cấu trúc dữ liệu Odoo đầu dự án (dòng 1) | Việc lặp lại ở mỗi dự án, baseline 2–4 giờ, đầu ra rõ (nguồn dữ liệu + phương án tích hợp) | Các dự án có giống nhau đủ để tái sử dụng không? Khảo sát tốn ở bước đọc hay bước hỏi BA/khách? |
| 2 | Chuẩn bị bộ tài liệu hỗn hợp (PDF, DOCX, Excel) cho hệ thống tìm kiếm theo nội dung (dòng 2) | Quy trình lặp lại ở mọi dự án, actor rõ, có baseline 3–5 giờ, các bước đọc/phân loại/làm sạch/chia nhỏ tách được | Bước nào thật sự tốn nhất? Mức "sạch" nào là đủ? |
| 3 | Truy vết nguyên nhân khi quy trình tự động chạy sai (dòng 3) | Có baseline 30–60 phút/lần, bước xử lý tách được, vừa sức một buổi lab | Tần suất lỗi là bao nhiêu lần mỗi tuần? Có đủ log để truy vết chưa? |

### Problem Card #1

| Trường | Nội dung |
|---|---|
| Job Story | Khi nhận yêu cầu xây dựng một hệ thống trả lời khách hàng dựa trên dữ liệu Odoo, tôi muốn nhanh chóng hiểu cấu trúc dữ liệu Odoo, để xác định nguồn dữ liệu và phương án tích hợp phù hợp mà không phải khảo sát thủ công quá nhiều. |
| Actor | AI Engineer (người làm chính), BA, khách hàng |
| Thời điểm / bối cảnh | Giai đoạn đầu mỗi dự án, ngay sau khi nhận yêu cầu |
| Quy trình hiện tại (3–7 bước) | 1. Đọc yêu cầu, xác định phạm vi nghiệp vụ · 2. Liệt kê các model liên quan trong Odoo · 3. Đọc field, kiểu dữ liệu và quan hệ giữa các model · 4. Đối chiếu với BA / khách hàng xem dữ liệu nào cần dùng · 5. Chốt nguồn dữ liệu và phương án tích hợp |
| Bottleneck (bước nào, mất bao nhiêu phút) | Giả thuyết (chưa đo): bước 3, đọc field và quan hệ, khoảng 40–90 phút/dự án; cần so với bước 4 (đối chiếu BA / khách hàng, 30–60') vì bước này phụ thuộc người khác chứ không phải kỹ thuật |
| Impact (nếu không giải thì sao) | Mất 2–4 giờ khảo sát ở mỗi dự án; khảo sát thiếu thì chọn sai nguồn dữ liệu hoặc phương án tích hợp, phải làm lại |
| Success metric (baseline → target) | Thời gian khảo sát: 2–4 giờ → (mục tiêu đề xuất, chưa chốt) dưới 1 giờ; đo bằng cách bấm giờ mỗi dự án |
| Phương án không dùng AI | Template khảo sát dùng lại + script xuất danh sách model/field + sơ đồ quan hệ dữ liệu dùng chung giữa các dự án |
| Giả thuyết về AI (nếu có) | Đọc cấu trúc dữ liệu và đề xuất nguồn dữ liệu liên quan; con người xác nhận với BA / khách hàng |
| Cảm nhận nhanh | Rule hoặc Workflow |

Quy trình nháp hiện tại 2–4 giờ = 120–240':

```text
HIỆN TẠI — khoảng 120–240 phút / dự án

[1 Đọc yêu cầu, xác định phạm vi: 10–20'] → [2 Liệt kê model liên quan: 20–40']
→ [3 Đọc field + quan hệ: 40–90'] ← BOTTLENECK (giả thuyết)
→ [4 Đối chiếu BA / khách hàng: 30–60'] → [5 Chốt nguồn dữ liệu + phương án: 20–30']
```

### Problem Card #2

| Trường | Nội dung |
|---|---|
| Job Story | Khi cần chuẩn bị một bộ tài liệu doanh nghiệp (PDF, DOCX, Excel) để hệ thống tìm kiếm theo nội dung, tôi muốn đọc, phân loại, làm sạch và chia nhỏ tài liệu nhanh hơn, để giảm thời gian chuẩn bị dữ liệu trước khi đưa vào hệ thống tìm kiếm. |
| Actor | AI Engineer (người làm chính), Data Engineer |
| Thời điểm / bối cảnh | Đầu mỗi dự án, ngay sau khi khách hàng gửi bộ tài liệu nội bộ |
| Quy trình hiện tại (3–7 bước) | 1. Rà soát tài liệu nhận được · 2. Phân loại theo định dạng / loại nội dung · 3. Trích xuất văn bản · 4. Làm sạch (header/footer, bảng, ký tự lỗi) · 5. Chia nhỏ tài liệu · 6. Kiểm tra mẫu và chốt bộ dữ liệu |
| Bottleneck (bước nào, mất bao nhiêu phút) | Giả thuyết (chưa đo): bước 4, làm sạch, khoảng 50–90 phút/bộ tài liệu |
| Impact (nếu không giải thì sao) | Mất 3–5 giờ cho mỗi bộ tài liệu ở mỗi dự án; dự án nhận nhiều bộ tài liệu thì thời gian chuẩn bị chiếm phần lớn trước khi kiểm thử được hệ thống |
| Success metric (baseline → target) | Thời gian chuẩn bị một bộ tài liệu: 3–5 giờ → (mục tiêu đề xuất, chưa chốt) dưới 1,5 giờ; đo bằng cách bấm giờ ít nhất 3 bộ tài liệu và ghi kèm loại tài liệu (số trang, PDF scan hay PDF văn bản, Excel nhiều sheet); (cần định nghĩa tiêu chí "đủ sạch" trước khi đo) |
| Phương án không dùng AI | Script cố định cho từng định dạng + checklist quy tắc làm sạch + quy ước chia nhỏ dùng chung |
| Giả thuyết về AI (nếu có) | Hỗ trợ phân loại tài liệu và đề xuất cách chia nhỏ; con người duyệt mẫu trước khi chốt |
| Cảm nhận nhanh | Workflow |

Quy trình nháp hiện tại  3–5 giờ = 180–300'
```text
HIỆN TẠI — khoảng 180–300 phút / bộ tài liệu

[1 Rà soát tài liệu: 15–25'] → [2 Phân loại: 20–40'] → [3 Trích xuất văn bản: 40–80']
→ [4 Làm sạch: 50–90'] ← BOTTLENECK (giả thuyết)
→ [5 Chia nhỏ: 35–45'] → [6 Kiểm tra mẫu + chốt: 20']
```

### Problem Card #3

| Trường | Nội dung |
|---|---|
| Job Story | Khi một quy trình tự động chạy sai hoặc không hoàn thành, tôi muốn truy vết được từng bước xử lý, lời gọi công cụ và kết quả API, để xác định chính xác nguyên nhân thay vì debug toàn bộ hệ thống. |
| Actor | AI Engineer (người làm chính), Backend Engineer, QA |
| Thời điểm / bối cảnh | Khi có báo lỗi từ khách hàng hoặc QA sau khi hệ thống đã chạy |
| Quy trình hiện tại (3–7 bước) | 1. Nhận báo lỗi, lấy input gốc · 2. Tái hiện lỗi · 3. Đọc log theo từng bước · 4. Khoanh vùng nguyên nhân |
| Bottleneck (bước nào, mất bao nhiêu phút) | Giả thuyết (chưa đo): bước 2, tái hiện lỗi, khoảng 10–25 phút/lần (lỗi khó tái hiện) |
| Impact (nếu không giải thì sao) | Mất 30–60 phút cho mỗi lỗi khó tái hiện; (cần đếm tần suất: số lỗi mỗi tuần và hệ thống hiện có lưu log từng bước chưa); lỗi kéo dài thì khách hàng chờ lâu và dễ debug sai chỗ |
| Success metric (baseline → target) | Thời gian tìm nguyên nhân: 30–60 phút → (mục tiêu đề xuất, chưa chốt) dưới 15 phút; đo bằng cách bấm giờ mỗi lỗi |
| Phương án không dùng AI | Logging chuẩn có mã truy vết (trace ID), lưu input/output của từng bước, trang xem log theo phiên |
| Giả thuyết về AI (nếu có) | Tóm tắt chuỗi bước từ log và gợi ý bước nghi ngờ; con người xác nhận nguyên nhân |
| Cảm nhận nhanh | Rule hoặc Workflow |

Quy trình nháp hiện tại 30–60':

```text
HIỆN TẠI — khoảng 30–60 phút / lỗi

[1 Nhận báo lỗi + lấy input gốc: 3–5'] → [2 Tái hiện lỗi: 10–25'] ← BOTTLENECK (giả thuyết)
→ [3 Đọc log từng bước: 10–20'] → [4 Khoanh vùng nguyên nhân: 7–10']
```

### Card muốn pitch nhất

- Card số: #1 (Khảo sát cấu trúc dữ liệu Odoo đầu dự án)
- Vì sao: Việc này lặp lại ở mỗi dự án và mất 2–4 giờ ngay từ đầu; đầu ra rõ (nguồn dữ liệu và phương án tích hợp); có thể thử bằng template và script trước, không cần xây gì lớn; câu hỏi còn mở (các dự án có giống nhau không) là thứ nhóm có thể góp ý ngay bằng kinh nghiệm của họ.
- Câu hỏi muốn nhóm phản biện: Nếu các dự án Odoo đều dùng chung một nhóm model, thì bộ template khảo sát dùng lại có giải quyết hết vấn đề này không, hay vẫn còn phần cần giải pháp khác?

### AI đã phản biện card thế nào

| Card | Điểm yếu AI chỉ ra | Đồng ý? | Đã sửa gì |
|---|---|---|---|
| #1 | Khảo sát có thể tốn ở bước hỏi BA/khách hơn bước đọc dữ liệu | Đồng ý | Bổ sung vào bottleneck: so sánh bước 3 với bước 4 (30–60') |
| #1 | Các dự án có thể dùng chung một nhóm model nên template là đủ | Đồng ý một phần | Giữ template + script trong phương án không dùng AI; sẽ kiểm tra mức trùng giữa các dự án |
| #2 | Baseline 3–5 giờ dao động quá rộng, không biết do loại tài liệu nào | Đồng ý | Sửa success metric: đo ít nhất 3 bộ tài liệu và ghi kèm loại tài liệu |
| #2 | Chưa có tiêu chí "xong" cho bộ dữ liệu "đủ sạch" | Đồng ý | Thêm ghi chú cần định nghĩa tiêu chí trước khi đo |
| #3 | Chưa biết tần suất lỗi và hệ thống có đủ log hay chưa | Đồng ý | Thêm vào impact: cần đếm số lỗi mỗi tuần và kiểm tra log hiện có |
| Cả 3 | Số phút từng bước chỉ là ước lượng, chưa có phép đo thật | Đồng ý | Đổi mọi quy trình nháp sang khoảng phút khớp baseline, đánh dấu "chưa phải số đo thật" và ghi cần bấm giờ |

---

## 4. Tôi đã tham gia phần nào (CP3 → CP7)

| Hoạt động | Tôi đã làm gì? | Kết quả / ảnh hưởng tới bài nhóm |
|---|---|---|
| Pitch Problem Card | Pitch 3 card: khảo sát cấu trúc dữ liệu Odoo (#1), chuẩn bị tài liệu cho RAG (#2), truy vết lỗi khi quy trình tự động chạy sai (#3). Card tôi muốn pitch nhất là #1 (Odoo). | Cả 3 card vào bảng pitch của nhóm. Nhóm chọn candidate của Đạt (Đạt #2, 35 điểm); card RAG của tôi được 31 điểm và bị loại vì bottleneck "làm sạch" còn là giả thuyết. |
| Phản biện bài của bạn khác | Câu hỏi tôi đã đặt cho nhóm làm agent trích xuất keyword từ bài báo khoa học: (1) "Làm sao đảm bảo các key trích xuất từ bài báo là đúng?"; (2) "Làm sao khi chạy cùng một bài báo hai lần mà không ra cùng các key?"; (3) "Validation thế nào?" | Nhóm đó trả lời: ban đầu giao hết cho LLM; sau câu hỏi, họ thêm một bước lấy feedback từ người dùng để model tự cải thiện thêm. Nhóm mình chưa thay đổi gì trong bài sau câu hỏi này; điểm đáng ghi nhận là bài Rule của nhóm mình cho kết quả lặp lại được khi chạy lại trên cùng dữ liệu, và được kiểm bằng 3 lỗi thật (id 48, 87, 97). |
| Nhận phản biện | Câu hỏi tôi nhận được (Đạt hỏi, ghi trong bảng pitch): "2–4 giờ hiểu cấu trúc Odoo là cho dự án đầu tiên hay dự án nào cũng vậy?"; "Hiểu cấu trúc Odoo có phải việc AI làm được không, hay chỉ cần tài liệu Odoo đầy đủ?"; "3–5 giờ xử lý tài liệu RAG: bao nhiêu phần lặp lại y hệt, bao nhiêu phần cần hiểu nội dung?"; "Truy vết agent 30–60 phút/lỗi: lỗi của agent hay log chưa đủ tốt?" | Tôi đã sửa gì: chưa sửa card theo các câu hỏi của Đạt. Các chỉnh sửa hiện có trong card đến từ phản biện của AI (xem mục 3). |
| Gom cluster / cây OST | Hỗ trợ ở CP3 theo phân công trong `TEAM.md` (người chính: Quân); tôi chưa ghi lại đóng góp cụ thể. | Cluster A và B của báo cáo nhóm gồm các card của tôi (Công #1, #2, #3). |
| Chọn candidate problem | Hỗ trợ ở CP3 theo `TEAM.md`; báo cáo nhóm không ghi nhận bất đồng với lựa chọn Đạt #2. | Candidate được chọn: Đạt #2 (thiếu file trong catalog), vì có bằng chứng cụ thể nhất (id 48, 87, 97). |
| Kiểm chứng / research | Nhờ AI soạn bản research ban đầu (lychee, linkinator, Ajv). Khi gộp bài, tôi chọn giữ bản của Đạt (Android Lint, Ajv, Crashlytics). Riêng tôi chưa trực tiếp phỏng vấn ai; 3 snapshot phỏng vấn ở mục 3.2 báo cáo nhóm do nhóm ghi. | Mục 3.3 của báo cáo nhóm dùng bản research của Đạt. |
| Quy trình nhóm | Hỗ trợ ở CP5 theo `TEAM.md` (người chính: Đạt); quy trình nháp từ Problem Card #2 của Đạt. | Mục 4 báo cáo nhóm (quy trình hiện tại, tương lai, before/after) do Đạt vẽ. |
| Problem Statement | Nhờ AI soạn bản nháp Problem Statement v0 và v1, rồi đối chiếu với các mục khác của báo cáo nhóm. | Bản nháp đã vào báo cáo nhóm, đang ghi là đề xuất, chưa được cả nhóm xác nhận. |
| Mức can thiệp AI | Nhờ AI soạn mục 6 (ma trận, so sánh 4 mức, AI Canvas, hai câu hỏi PAIR); kết quả chọn mức Rule, không dùng AI. | Mục 6 trong báo cáo nhóm; cần nhóm xác nhận. |
| Quyết định | Nhờ AI soạn mục 8 (bốn rủi ro, ngưỡng dừng). Đề xuất "Go, phạm vi nhỏ". Giải quyết conflict trong báo cáo nhóm (giữ bản của Đạt) và push lên repo. | Quyết định vẫn ghi "đề xuất, cần nhóm xác nhận". |

---

## 5. Dùng AI

| Checkpoint | Tôi dùng AI để làm gì? | AI hữu ích ở đâu? | AI sai hoặc hời hợt ở đâu? | Tôi sửa gì bằng nhận định của mình? |
|---|---|---|---|---|
| CP1 Scan | Tự viết 10 problem trước, sau đó nhờ AI duyệt theo tiêu chí CP1 và điền vào bảng. AI không gợi ý thêm problem mới. | Chỉ ra Job Story có chữ "AI", "chatbot", "agent" (vi phạm tiêu chí CP1) và các dòng 3, 4, 6, 9, 10 chưa có số đo. | AI chép nguyên văn câu chữ cho khớp bảng pitch nhóm nên giữ cả lỗi trên. | Sau đó nhờ AI viết lại Job Story của cả 10 dòng để bỏ chữ AI/chatbot/agent và các giải pháp nằm sẵn trong câu; các con số đo vẫn do tôi tự cung cấp và còn phải đo thêm ở một số dòng. |
| CP2 Problem Card | Nhờ AI chọn top 3 từ 10 problem, soạn 3 card kèm quy trình nháp, và đóng vai "PM hoài nghi" phản biện. | Phản biện chỉ ra baseline dao động rộng, chưa có tiêu chí "đủ sạch", chưa biết tần suất lỗi; gợi ý câu hỏi cho card muốn pitch. | Số phút từng bước, bottleneck và target do AI suy ra từ baseline (chia khoảng), không phải số đo thật. AI từng đặt thứ tự card lệch với bảng pitch nhóm. | Ghi rõ bottleneck là giả thuyết (chưa đo) và target là mục tiêu đề xuất, chưa chốt; đổi mọi quy trình sang khoảng phút; sắp lại thứ tự card cho khớp báo cáo nhóm. Chưa bấm giờ thật. |
| CP4 Research | Nhờ AI tìm công cụ tương tự (lychee, linkinator, Ajv) và mở README để kiểm nội dung. | Có hướng để so sánh và nhận ra không công cụ nào kiểm được đường dẫn trong catalog JSON. | Các công cụ là link checker cho tài liệu, không đúng bài toán; AI ghi "chưa rõ có đọc được catalog không (cần thử)". Sau khi gộp bản của Đạt, các số thứ tự giả định trong báo cáo bị lệch. | Giữ bản research của Đạt (Android Lint, Ajv, Crashlytics); chỉnh lại các chỗ tham chiếu giả định cho khớp bảng của Đạt. Chưa tự mở lại từng link. |
| CP5 Quy trình | Không dùng AI để vẽ quy trình (mục 4 báo cáo nhóm, nháp từ Problem Card #2 của Đạt). Chỉ nhờ AI đọc lại để đối chiếu với các mục khác của báo cáo nhóm. | Chỉ ra mục 4.1 vẫn ghi "cập nhật số phút sau kiểm chứng CP4" trong khi chưa có số đo thời gian thật. | Không có (AI không soạn mục này). | Chưa sửa dòng trên; cần nhóm bỏ cụm đó hoặc đo thật rồi cập nhật. |
| CP5–6 Problem Statement | Nhờ AI soạn Problem Statement v0, v1 và 5 tiêu chí đánh giá. | Có khung 6 trường nhất quán và bảng thay đổi giữa v0 và v1. | Success Metric dựa trên baseline ước tính; AI để trống phần "phản biện nhận được" thay vì bịa; tiêu chí cho công cụ Rule chứ không phải đầu ra của mô hình AI. | Giữ nhãn "đề xuất, cần nhóm xác nhận"; chờ nhóm bổ sung phản biện thật. |
| CP6 Mức can thiệp / quyết định | Nhờ AI soạn so sánh 4 mức, AI Canvas, hai câu hỏi PAIR, bốn rủi ro và quyết định. | Có lập luận "vì sao không chọn mức đơn giản hơn" và ngưỡng dừng đo được. | Đánh giá "độ phức tạp thấp" và rủi ro Value "Trung bình" là phán đoán của AI, chưa được kiểm chứng bằng phỏng vấn. | Giữ "Go, phạm vi nhỏ" ở mức đề xuất; ghi rõ cần phỏng vấn và bấm giờ thật trước khi chốt. |

---

## 6. Reflection (CP7)

Trả lời bằng trải nghiệm thật của bạn, tối thiểu 200 từ cho các câu 6.1–6.6 (không tính 6.7, câu này được chấm riêng ở tiêu chí C5). **Không dùng AI để viết thay.**

**6.1. Tôi học được gì khi nghe top 3 problems của các bạn khác?**
Tôi học được mỗi người đều có những khó khăn riêng và cách giải quyết của mỗi người cũng khác nhau. Nhưng nhìn chung mọi người đều ứng dụng công nghệ để giải quyết các khó khăn của riêng họ. Dù cách dùng khác nhau, suy nghĩ khác nhau nhưng đều được công nghệ hỗ trợ.

**6.2. Nhóm có lúc nào bị "solution-first" (nghĩ giải pháp trước khi hiểu vấn đề) không? Lúc đó nhóm nhận ra và xử lý thế nào?**
Nhóm đã có những lúc như vậy. Nhưng sau khi mải mê đi tìm lời giải rồi dừng lại hỏi xem mình đang đi giải bài toán gì? Bài toán ban đầu của mình là gì? Mình có thể nhìn nhận vấn đề theo các ít công nghệ hơn không? Sau khi đã trả lời được các câu hỏi đó, nhóm bắt đầu lại với bài toán ban đầu, tìm những nỗi đau thật sự trong bài toán và đi tìm cách giải quyết.

**6.3. Tôi có đổi ý sau khi bị phản biện không? Kể một lần cụ thể.**
Tôi không đổi ý sau khi bị phản biện. Một nhóm khác hỏi vì sao nhóm tôi dùng rule thay vì AI, và nếu loại dữ liệu thay đổi hoặc có thêm dữ liệu mới thì sao. Tôi trả lời rằng công việc hiện tại chỉ là kiểm tra số file và theme, có thể đếm bằng code với chi phí rẻ hơn và độ chính xác cao hơn AI, nên rule là đủ. Khi việc kiểm tra phức tạp hơn, như nhiều loại dữ liệu hoặc kiểm tra nội dung từng file, nhóm sẽ cân nhắc áp dụng AI. Họ chỉ gật đầu và không phản biện thêm. Tôi giữ nguyên quyết định dùng rule cho phạm vi hiện tại.


**6.4. Kết quả kiểm chứng (phỏng vấn/survey/research) có làm tôi bất ngờ không? Điều gì?**
Những câu hỏi của nhóm khác không làm tôi bất ngờ vì nhóm tôi đã dự đoán được các câu hỏi mà các nhóm có thể hỏi.

**6.5. Điều khó nhất khi viết Problem Statement là gì?**
Khó khăn trong việc tìm ra nguyên nhân gốc rễ, đồng thời phân biệt dữ kiện thực tế với giả định cá nhân để tránh xây dựng Problem Statement dựa trên những nhận định chưa được kiểm chứng.
**6.6. Nếu làm lại, tôi sẽ đổi gì? Tôi sẽ phản biện nhóm mạnh hơn ở điểm nào?**
Nếu lại, tôi sẽ đổi cách tiếp cận đến bài toán, thay vì mải đi tìm công nghệ trước thì tôi sẽ viết problem statement rõ ràng, kĩ càng để có thể nhìn nhận vấn đề sâu sắc hơn, hiểu rõ nỗi đau của những người cần nó hơn. Tôi sẽ dựa vào đó để phản biện mạnh hơn về giải pháp mà tôi giải quyết được gốc rễ vấn đề như vậy, đánh đúng vào nhu cầu của thị trường
**6.7. Hiểu bài:** giải thích bằng 5–8 câu, không nhìn tài liệu, chuỗi *problem → quy trình → metric → boundary → mức can thiệp AI → quyết định* của bài nhóm mình.
Đạt gặp khó khăn trong việc kiểm tra tính đầy đủ của các file giao diện theo catalog, đặc biệt ở bước đối chiếu đường dẫn và rà soát file trên đĩa, mất khoảng 45–90 phút trong tổng quy trình 1–2 tiếng. Nhóm đề xuất xây dựng công cụ Rule-based để phát hiện file thiếu, với mục tiêu giảm thời gian tìm lỗi xuống dưới 1 phút và giảm số theme lỗi bị bỏ sót từ 1–2 lỗi mỗi đợt build xuống 0. Nhóm chọn Rule-based thay vì No AI vì checklist và rà soát thủ công vẫn để lọt các lỗi thực tế (ID 48, 87, 97), nhưng chưa cần Workflow hay Agent vì các điều kiện kiểm tra có thể biểu diễn bằng quy tắc rõ ràng. Công cụ chỉ cảnh báo, không tự ý sửa, xóa hoặc tạo file; mọi thay đổi đều do developer phê duyệt. Nhóm sẽ pilot trên toàn bộ catalog 160 theme, sử dụng 3 lỗi đã biết để kiểm chứng và bấm giờ 2–3 lần rà soát thủ công để so sánh. Nếu bỏ sót ít nhất 1 trong 3 lỗi, nhóm sẽ sửa rule; nếu vẫn bỏ sót sau lần sửa thứ hai, sẽ quay lại checklist và rà tay. Quyết định hiện tại là **Go với phạm vi pilot nhỏ**, trước khi xem xét mở rộng. Lưu ý, thời gian 45–90 phút hiện là ước tính, nhóm chưa bấm giờ thực tế và chưa phỏng vấn người dùng.

---

## 7. Tài liệu tham khảo

- Tài liệu khóa học: [docs/01-worksheet.md](../../docs/01-worksheet.md), [docs/03-international-frameworks.md](../../docs/03-international-frameworks.md).
- Danh sách tài liệu tham khảo chung của nhóm: [group_report.md](../team/group_report.md), mục 10.
