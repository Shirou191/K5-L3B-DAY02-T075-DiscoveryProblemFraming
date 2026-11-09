# Team

> Điền file này trên repo chung do nhóm trưởng fork. Nhóm điền phần **Thông tin nhóm** và **Thành viên**. Mỗi người tự điền phần của mình trong **Cá nhân**. Không copy file này sang repo khác.

## Thông tin nhóm

- Tên nhóm: T075
- Candidate problem nhóm chọn (1 câu): Khi một theme bàn phím bị báo lỗi thiếu file, dev muốn biết ngay file nào, theme nào để không phải rà tay cả catalog 160 theme (Đạt #2).
- Quyết định cuối (Go / Not Yet / No-Go): Go, phạm vi nhỏ — giải pháp mức Rule (script kiểm tra), không dùng AI

## Thành viên

| STT | Họ và tên | MSSV | Vai trò trong nhóm | Tài khoản GitHub |
|---:|---|---|---|---|
| 1 | Phan Đào Minh Quân | 2A202603971 | Nhóm trưởng, điều phối thời gian, ghi chép CP3 | Shirou191 |
| 2 | Hà Văn Khánh Đạt | 2A202604074 | Chủ candidate được chọn (Đạt #2), phụ trách research, vẽ quy trình | hadatttt |
| 3 | Võ Trần Công | 2A202604026 | Viết Problem Statement, người phản biện chính, gộp báo cáo nhóm | congvt |

Không ghi email hay số điện thoại vào bảng này, vì repo có thể để public.

Gợi ý vai trò (một người có thể giữ nhiều vai): điều phối thời gian, ghi chép, người phản biện chính, phụ trách kiểm chứng (phỏng vấn/survey), phụ trách research, vẽ quy trình, viết Problem Statement.

## Phân công theo checkpoint

| Checkpoint | Người chính | Người hỗ trợ | Sản phẩm |
|---|---|---|---|
| CP3 — Hội tụ nhóm | Quân | Đạt, Công | Cluster, cây OST, bảng chấm điểm |
| CP4 — Kiểm chứng | Đạt | Công | Assumption map, bộ câu hỏi phỏng vấn, kế hoạch kiểm chứng |
| CP4 — Research | Đạt | Quân | Bảng research có link |
| CP5 — Quy trình trước/sau | Đạt | Công | Quy trình + bảng before/after |
| CP5 — Problem Statement v0 | Công | Đạt | Problem Statement v0 |
| CP6 — Mức can thiệp + Problem Statement v1 | Công | Đạt | Ma trận, AI Canvas, eval, Problem Statement v1 |
| CP6 — Quyết định | Công | Đạt, Quân | 4 rủi ro + Go/Not Yet/No-Go |

## Cá nhân

Mỗi thành viên thêm một mục theo mẫu dưới đây, tiêu đề là `HoVaTen-MSSV`.

### HaVanKhanhDat-2A202604074

**Phần việc phụ trách:**

- Đưa ra candidate được nhóm chọn (Đạt #2 — chẩn đoán file thiếu trong catalog theme) và cung cấp toàn bộ dữ liệu thật cho bài nhóm.
- CP4: Assumption Map, bộ câu hỏi phỏng vấn, research giải pháp đã có.
- CP5: quy trình hiện tại, quy trình tương lai, bảng before/after.

**Đóng góp cụ thể** (mình đã làm gì, ra sản phẩm gì):

- Cung cấp bằng chứng lỗi thật (id 48, 87, 97), quy trình 7 bước và số phút từng bước — là lý do candidate đạt 35/35 điểm ở bảng 2.4.
- Viết mục 3.1 Assumption Map, bộ câu hỏi phỏng vấn ở 3.2, bảng research 3.3 (Android Lint, JSON Schema/Ajv, Firebase Crashlytics, có link).
- Vẽ sơ đồ Mermaid quy trình hiện tại (4.1) và tương lai (4.2) có Rule, con người, boundary, phương án quay về; bảng before/after (4.3); mục 9, 10.
- Góp ý cho Problem Statement và quyết định: chọn Rule vì kiểm tra file tồn tại là bài toán đúng/sai rõ ràng.

**Bằng chứng** (phần nào trong `group_report.md`, file nào trong `report/assets/`, commit nào):

- `group_report.md` mục 1, 3.1, 3.2 (bộ câu hỏi), 3.3, 4.1, 4.2, 4.3, 9, 10 — commit `af003eb` ("dat push").
- Báo cáo cá nhân `report/individual/2A202604074_HaVanKhanhDat.md` — commit `c1cf0a6`; Problem Card #2 là nguồn của candidate nhóm.

**Điều mình học được từ phần nhóm:**

- Bằng chứng ghi nhận thật (log lỗi có id) làm vấn đề thuyết phục hơn nhiều so với ước lượng; nhưng vấn đề chỉ một người gặp thì vẫn yếu ở rủi ro Value.
- Chọn mức đơn giản nhất đủ dùng: bài này Rule là đủ, kết luận không cần AI vẫn là kết luận tốt nếu lập luận chặt.

### PhanDaoMinhQuan-2A202603971

**Phần việc phụ trách:**

- Nhóm trưởng, điều phối thời gian và ghi chép CP3.
- Chuẩn bị 3 Problem Card về tổng hợp tiến độ, kiểm tra báo cáo theo rubric và tìm lại quyết định cũ.
- Tham gia gom cluster, xây cây OST, chấm điểm candidate và đồng thuận chọn problem.

**Đóng góp cụ thể** (mình đã làm gì, ra sản phẩm gì):

- Viết 8 candidate problem theo 4 lăng kính ở CP1; chọn và phát triển 3 Problem Card ở CP2.
- Đóng góp 3 candidate vào phần pitch CP3 và cluster “Điều phối và truy hồi thông tin nhóm”.
- Đề xuất cách tách problem khỏi solution: mô tả pain, actor, bottleneck trước khi chọn No AI/Rule/Workflow/Agent.
- Tham gia chấm điểm shortlist và ghi nhận lý do candidate asset của Đạt được ưu tiên vì có bằng chứng cụ thể hơn.
- Rà soát boundary và mức can thiệp của nhóm; ủng hộ giải pháp Rule, không để công cụ tự sửa hoặc tự tạo file.

**Bằng chứng** (phần nào trong `group_report.md`, file nào trong `report/assets/`, commit nào):

- Báo cáo cá nhân `report/individual/2A202603971_PhanDaoMinhQuan.md`: CP1, CP2, CP3–CP7.
- `group_report.md` mục 2.1 Pitch, 2.2 Cluster, 2.3 Opportunity Solution Tree, 2.4 Chấm điểm shortlist.
- `group_report.md` mục 4–8: quy trình, Problem Statement, mức Rule và quyết định Go phạm vi nhỏ.
- Tài khoản GitHub thực hiện đóng góp: `Shirou191`.

**Điều mình học được từ phần nhóm:**

- Problem có scope nhỏ nhưng có actor, bottleneck và bằng chứng cụ thể đáng tin hơn một ý tưởng AI rộng nhưng chưa có baseline.
- Cần kiểm tra No AI và Rule trước khi chọn Workflow hoặc Agent; bài toán đối chiếu file có đúng/sai rõ nên Rule là mức phù hợp.
- Các số liệu ước tính phải được tách khỏi bằng chứng đã kiểm chứng và cần được bấm giờ hoặc ghi log trước khi chốt metric.
