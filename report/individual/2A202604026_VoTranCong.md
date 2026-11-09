# Báo cáo cá nhân — MSSV_HoTen

> Đổi tên file theo quy tắc `MSSV_HoTen.md`, ví dụ `20241234_NguyenVanAn.md` (MSSV trước, dấu `_`, họ tên viết liền không dấu). Sửa cả dòng tiêu đề phía trên cho khớp.
> Template chi tiết và prompt mẫu cho từng mục: [docs/01-worksheet.md](../../docs/01-worksheet.md).
> Mỗi thành viên một file trong `report/individual/` trên repo nhóm: copy template này thành file mới, điền, rồi commit bằng tài khoản GitHub của bạn. Không viết hộ người khác.

## 1. Thông tin học viên

- Họ tên: Võ Trần Công
- MSSV: 2A202604026
- Email trường (không bắt buộc, repo có thể để public):
- Tên nhóm: T075
- Link repo nhóm: https://github.com/Shirou191/K5-L3B-Day02-T075-DiscoveryProblemFraming.git

---

## 2. Scan problem (CP1)

Lăng kính: **Lặp lại** · **Tốn thời gian** · **Cần đọc, tổng hợp nhiều thông tin** · **Pain từ người khác**.

| # | Lăng kính | Job Story | Ai chịu ảnh hưởng? | Dấu hiệu thật (thời gian, tần suất, số người, bằng chứng) |
|---:|---|---|---|---|
| 1 | Lặp lại | Khi nhận yêu cầu xây dựng chatbot AI, tôi muốn hiểu cấu trúc dữ liệu Odoo nhanh hơn để xác định nguồn dữ liệu và phương án tích hợp | AI Engineer, BA, khách hàng | Mỗi dự án mất 2–4 giờ khảo sát model, field và quan hệ dữ liệu Odoo. |
| 2 | Tốn thời gian | Khi xây dựng pipeline RAG, tôi muốn xử lý bộ tài liệu PDF, DOCX, Excel nhanh hơn để giảm thời gian chuẩn bị dữ liệu | AI Engineer, Data Engineer | Mất 3–5 giờ xử lý một bộ tài liệu hỗn hợp PDF, DOCX, Excel. |
| 3 | Tốn thời gian | Khi AI Agent chạy sai, tôi muốn truy vết từng bước reasoning, tool call và API để tìm đúng nguyên nhân | AI Engineer, Backend Engineer, QA | Mất 30–60 phút để tái hiện và tìm nguyên nhân một lỗi Agent khó tái hiện. |
| 4 | Cần đọc, tổng hợp nhiều thông tin | Khi khách hàng yêu cầu chatbot trả lời dựa trên dữ liệu nội bộ, tôi muốn xác định chính xác quyền truy cập của từng người dùng và phòng ban, để chatbot không trả về thông tin ngoài phạm vi được phép. | AI Engineer, khách hàng, IT Admin | Phải xử lý nhiều trường hợp phân quyền theo user, department và role; một lỗi phân quyền có thể làm lộ dữ liệu nội bộ. |
| 5 | Lặp lại | Khi triển khai AI Agent kết nối với Odoo và các ứng dụng bên ngoài, tôi muốn có bộ công cụ chuẩn hóa cho API, authentication, retry và logging, để không phải viết lại logic tích hợp cho từng dự án. | AI Engineer, Backend Engineer, khách hàng | Nhiều dự án phải viết lại các đoạn code gọi API, xử lý token và retry. |
| 6 | Cần đọc, tổng hợp nhiều thông tin | Khi lựa chọn LLM, embedding model hoặc reranker cho dự án, tôi muốn có benchmark theo dữ liệu và phần cứng thực tế, để chọn được mô hình cân bằng giữa độ chính xác, latency và chi phí. | AI Engineer, Tech Lead, khách hàng | Mỗi lần đánh giá model phải chạy nhiều thử nghiệm thủ công; kết quả chưa được chuẩn hóa giữa các dự án. |
| 7 | Pain từ người khác | Khi bàn giao tính năng AI cho Backend Engineer hoặc Frontend Engineer, họ muốn có API contract, schema và tài liệu tích hợp rõ ràng, để kết nối hệ thống mà không phải hỏi lại nhiều lần. | AI Engineer, Backend Engineer, Frontend Engineer | Phát sinh 2–3 vòng trao đổi để làm rõ request, response, streaming và error handling. |
| 8 | Tốn thời gian | Khi triển khai mô hình AI lên môi trường production, tôi muốn có quy trình đóng gói, cấu hình và triển khai thống nhất bằng Docker, để giảm thời gian setup và tránh lỗi khác biệt giữa local, staging và production. | AI Engineer, DevOps, khách hàng | Mỗi môi trường cần cấu hình thủ công; thường mất 1–3 giờ để xử lý lỗi phụ thuộc và cấu hình. |
| 9 | Pain từ người khác | Khi khách hàng sử dụng chatbot hoặc AI Agent nhưng nhận được câu trả lời sai, họ muốn có cơ chế ghi nhận feedback và đánh giá chất lượng, để vấn đề được phát hiện và cải thiện thay vì chỉ phản ánh qua trao đổi thủ công. | Khách hàng, AI Engineer, Product Owner | Feedback đang phân tán qua Slack, email hoặc ticket; khó thống kê tỷ lệ câu trả lời sai và nguyên nhân. |
| 10 | Lặp lại | Khi cần bảo trì nhiều hệ thống AI đã triển khai cho khách hàng, tôi muốn theo dõi tập trung tình trạng API, model, vector database, token usage và latency, để phát hiện sự cố trước khi ảnh hưởng đến hoạt động doanh nghiệp. | AI Engineer, DevOps, khách hàng | Phải kiểm tra log và từng service riêng lẻ; chưa có dashboard tổng hợp tình trạng các hệ thống AI. |

**Nếu có dùng AI để gợi ý thêm:** ý nào AI gợi ý mà bạn giữ lại, ý nào bỏ và vì sao.

-

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
| Bottleneck (bước nào, mất bao nhiêu phút) | **[Cần xác nhận]** Giả thuyết: bước 3, đọc field và quan hệ, khoảng 40–90 phút/dự án; cần so với bước 4 (đối chiếu BA / khách hàng, 30–60') vì bước này phụ thuộc người khác chứ không phải kỹ thuật |
| Impact (nếu không giải thì sao) | Mất 2–4 giờ khảo sát ở mỗi dự án; khảo sát thiếu thì chọn sai nguồn dữ liệu hoặc phương án tích hợp, phải làm lại |
| Success metric (baseline → target) | Thời gian khảo sát: 2–4 giờ → **[đề xuất, bạn chốt]** dưới 1 giờ; đo bằng cách bấm giờ mỗi dự án |
| Phương án không dùng AI | Template khảo sát dùng lại + script xuất danh sách model/field + sơ đồ quan hệ dữ liệu dùng chung giữa các dự án |
| Giả thuyết về AI (nếu có) | Đọc cấu trúc dữ liệu và đề xuất nguồn dữ liệu liên quan; con người xác nhận với BA / khách hàng |
| Cảm nhận nhanh | Rule hoặc Workflow |

Quy trình nháp hiện tại (**đề xuất cập nhật số phút**: đổi từ một con số sang khoảng, tổng khớp baseline 2–4 giờ = 120–240'. Đây chưa phải số đo thật; thay bằng số bấm giờ khi có):

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
| Bottleneck (bước nào, mất bao nhiêu phút) | **[Cần xác nhận]** Giả thuyết: bước 4, làm sạch, khoảng 50–90 phút/bộ tài liệu |
| Impact (nếu không giải thì sao) | Mất 3–5 giờ cho mỗi bộ tài liệu ở mỗi dự án; dự án nhận nhiều bộ tài liệu thì thời gian chuẩn bị chiếm phần lớn trước khi kiểm thử được hệ thống |
| Success metric (baseline → target) | Thời gian chuẩn bị một bộ tài liệu: 3–5 giờ → **[đề xuất, bạn chốt]** dưới 1,5 giờ; đo bằng cách bấm giờ ít nhất 3 bộ tài liệu và ghi kèm loại tài liệu (số trang, PDF scan hay PDF văn bản, Excel nhiều sheet); **[cần định nghĩa tiêu chí "đủ sạch" trước khi đo]** |
| Phương án không dùng AI | Script cố định cho từng định dạng + checklist quy tắc làm sạch + quy ước chia nhỏ dùng chung |
| Giả thuyết về AI (nếu có) | Hỗ trợ phân loại tài liệu và đề xuất cách chia nhỏ; con người duyệt mẫu trước khi chốt |
| Cảm nhận nhanh | Workflow |

Quy trình nháp hiện tại (**đề xuất cập nhật số phút**: đổi sang khoảng, tổng khớp baseline 3–5 giờ = 180–300'. Chưa phải số đo thật; thay bằng số bấm giờ khi có):

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
| Bottleneck (bước nào, mất bao nhiêu phút) | **[Cần xác nhận]** Giả thuyết: bước 2, tái hiện lỗi, khoảng 10–25 phút/lần (lỗi khó tái hiện) |
| Impact (nếu không giải thì sao) | Mất 30–60 phút cho mỗi lỗi khó tái hiện; **[cần đếm tần suất: số lỗi mỗi tuần và hệ thống hiện có lưu log từng bước chưa]**; lỗi kéo dài thì khách hàng chờ lâu và dễ debug sai chỗ |
| Success metric (baseline → target) | Thời gian tìm nguyên nhân: 30–60 phút → **[đề xuất, bạn chốt]** dưới 15 phút; đo bằng cách bấm giờ mỗi lỗi |
| Phương án không dùng AI | Logging chuẩn có mã truy vết (trace ID), lưu input/output của từng bước, trang xem log theo phiên |
| Giả thuyết về AI (nếu có) | Tóm tắt chuỗi bước từ log và gợi ý bước nghi ngờ; con người xác nhận nguyên nhân |
| Cảm nhận nhanh | Rule hoặc Workflow |

Quy trình nháp hiện tại (**đề xuất cập nhật số phút**: đổi sang khoảng, tổng khớp baseline 30–60'. Chưa phải số đo thật; thay bằng số bấm giờ khi có):

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
| Pitch Problem Card | | |
| Phản biện bài của bạn khác | Câu hỏi tôi đã đặt: | |
| Nhận phản biện | Câu hỏi tôi nhận được: | Tôi đã sửa gì: |
| Gom cluster / cây OST | | |
| Chọn candidate problem | | |
| Kiểm chứng / research | | |
| Quy trình nhóm | | |
| Problem Statement | | |
| Mức can thiệp AI | | |
| Quyết định | | |

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
Tôi học được mỗi người đều có những khó khắn riêng, 

**6.2. Nhóm có lúc nào bị "solution-first" (nghĩ giải pháp trước khi hiểu vấn đề) không? Lúc đó nhóm nhận ra và xử lý thế nào?**

**6.3. Tôi có đổi ý sau khi bị phản biện không? Kể một lần cụ thể.**

**6.4. Kết quả kiểm chứng (phỏng vấn/survey/research) có làm tôi bất ngờ không? Điều gì?**

**6.5. Điều khó nhất khi viết Problem Statement là gì?**

**6.6. Nếu làm lại, tôi sẽ đổi gì? Tôi sẽ phản biện nhóm mạnh hơn ở điểm nào?**

**6.7. Hiểu bài:** giải thích bằng 5–8 câu, không nhìn tài liệu, chuỗi *problem → quy trình → metric → boundary → mức can thiệp AI → quyết định* của bài nhóm mình.

---

## 7. Tài liệu tham khảo

-
