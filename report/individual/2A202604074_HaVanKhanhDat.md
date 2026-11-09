# Báo cáo cá nhân — MSSV_HoTen

> Đổi tên file theo quy tắc `MSSV_HoTen.md`, ví dụ `20241234_NguyenVanAn.md` (MSSV trước, dấu `_`, họ tên viết liền không dấu). Sửa cả dòng tiêu đề phía trên cho khớp.
> Template chi tiết và prompt mẫu cho từng mục: [docs/01-worksheet.md](../../docs/01-worksheet.md).
> Mỗi thành viên một file trong `report/individual/` trên repo nhóm: copy template này thành file mới, điền, rồi commit bằng tài khoản GitHub của bạn. Không viết hộ người khác.

## 1. Thông tin học viên

- Họ tên: Hà Văn Khánh Đạt
- MSSV: 2A202604074
- Email trường (không bắt buộc, repo có thể để public):
- Tên nhóm: T075
- Link repo nhóm: https://github.com/Shirou191/K5-L3B-Day02-T075-DiscoveryProblemFraming

---

## 2. Scan problem (CP1)

Lăng kính: **Lặp lại** · **Tốn thời gian** · **Cần đọc, tổng hợp nhiều thông tin** · **Pain từ người khác**.

| # | Lăng kính | Job Story: Khi… tôi muốn… để… | Ai chịu ảnh hưởng? | Dấu hiệu thật (thời gian, tần suất, số người, bằng chứng) |
|---:|---|---|---|---|
| 1 | Lặp lại | Khi thêm một theme bàn phím mới, tôi muốn biết đủ các file ảnh, âm thanh, font cần chuẩn bị, để không bị thiếu asset khi build | Dev, designer | ~3 theme/tuần, mỗi lần mất ~30' để kiểm tra lại |
| 2 | Lặp lại | Khi làm xong một theme mới, tôi muốn có sẵn catalog entry đúng schema (id, order, font, màu toolbar…), để không phải gõ tay từng trường rồi sai format | Dev | ~3 theme/tuần, mỗi entry ~15' gõ tay; từng sai màu toolbar 10 ký tự hex ở id 91/92/94/95 |
| 3 | Tốn thời gian | Khi cần làm GIF cho keycap, tôi muốn render 6-frame pulse từ keycap tĩnh tự động, để không phải xuất từng frame tay | Dev, designer | Mỗi theme 5 biến thể GIF, ~20'/theme làm tay |
| 4 | Cần đọc, tổng hợp nhiều thông tin | Khi một theme bị báo lỗi thiếu file, tôi muốn biết ngay file nào, theme nào, để không phải rà cả catalog 160 theme | Dev | Từng rà tay cả catalog vì id 48 trỏ tới file không tồn tại; id 87 thiếu popup, id 97 var4 404 |
| 5 | Pain từ người khác | Khi designer giao asset mới, tôi muốn tên file đúng chuẩn ngay từ đầu, để không phải đổi tên hàng loạt | Designer, dev | Id 123 typo `nomal`, id 134 tên file chứa `{cate}` — đều phải sửa tay sau |
| 6 | Lặp lại | Khi đóng gói ZIP giao, tôi muốn mỗi theme tự chứa đủ folder (Background/Keycap/Popup/Sound/Effect…), để không phải đi gom file rời | Dev | Combo V3: 160 theme, 2.192 file; gom tay từng để sót ref |
| 7 | Tốn thời gian | Khi cần làm video preview MP4 cho theme, tôi muốn render tự động từ ảnh ngày/đêm, để không phải dựng tay từng video | Dev | 160 theme, mỗi video 3s zoompan, làm tay ~10'/video |
| 8 | Cần đọc, tổng hợp nhiều thông tin | Khi có 2 theme gần giống nhau, tôi muốn biết chúng trùng ở asset nào, để quyết định làm lại hay giữ | Dev | Cặp Mint Heart Boy (357) vs Lilac Heart Girl (358) từng phải soi tay từng file |

**Nếu có dùng AI để gợi ý thêm:** ý nào AI gợi ý mà bạn giữ lại, ý nào bỏ và vì sao.

- Dòng 1 dựa trên ví dụ minh họa AI (Claude) đưa ra khi giải thích cách làm CP1; giữ lại vì đúng việc mình làm hằng tuần, số liệu là của mình. Các dòng 2–8 tự viết từ việc làm app bàn phím. Không dùng AI để gợi ý thêm problem.

---

## 3. Top 3 Problem Cards + quy trình nháp (CP2)

### Bảng chọn top 3

| Rank | Problem | Vì sao chọn | Điều còn chưa chắc |
|---:|---|---|---|
| 1 | Thêm theme mới hay thiếu asset khi build | Lặp lại nhiều nhất: ~3 theme/tuần, mỗi lần mất ~30' kiểm tra lại; thiếu file cũng là lỗi hay gặp nhất trong catalog | Chưa chắc mọi loại theme (animated, day-night) có cùng checklist asset không, hay mỗi loại cần thêm file riêng |
| 2 | Theme bị báo lỗi thiếu file nhưng không biết file nào, phải rà cả catalog 160 theme | Lỗi đã lọt vào dữ liệu thật nhiều lần; rà tay cả catalog vừa lâu vừa dễ sót, mà lỗi này ra tới tay user là theme hỏng luôn | Chưa chắc lỗi thiếu file là do đặt tên sai, file chưa từng được tạo, hay do catalog ghi sai đường dẫn |
| 3 | Đóng gói ZIP phải gom file rời từng theme | Quy mô lớn nhất: 160 theme, 2.192 file; gom tay từng để sót ref, và mỗi lần sửa lại phải đóng gói lại từ đầu | Chưa chắc cấu trúc folder chuẩn (Background/Keycap/Popup/Sound/Effect…) đã cố định chưa, hay sau này còn đổi |

### Problem Card #1

| Trường | Nội dung |
|---|---|
| Job Story | Khi thêm một theme bàn phím mới, tôi muốn biết đủ các file ảnh, âm thanh, font cần chuẩn bị, để không bị thiếu asset khi build |
| Actor | Dev (người làm data theme) |
| Thời điểm / bối cảnh | Mỗi khi thêm theme mới, ~3 theme/tuần, lúc chuẩn bị build và đóng gói ZIP |
| Quy trình hiện tại (3–7 bước) | 1. Chốt mẫu theme và phong cách (kawaii/neon/zodiac…) — 2. Gen ảnh các asset: background, keycap, popup, effect, preview — 3. Làm GIF keycap + MP4 preview — 4. Chuẩn bị sound + font — 5. Ghi catalog entry tay (id, order, font, màu toolbar…) — 6. Rà tay từng file xem đủ chưa — 7. Đóng gói ZIP theo từng category |
| Bottleneck (bước nào, mất bao nhiêu phút) | Bước 6 — rà tay từng file: ~30'/theme, ~90'/tuần; mà vẫn sót (id 48 trỏ file không tồn tại, id 87 thiếu popup, id 97 var4 404) |
| Impact (nếu không giải thì sao) | Theme thiếu file lọt ra ngoài → theme hỏng trên tay user, phải sửa + đóng gói lại; catalog sai có thể làm app thiếu asset |
| Success metric (baseline → target) | Thời gian kiểm tra asset: 30'/theme → <2'/theme; số theme thiếu file khi build: 1–2 lỗi/đợt → 0 |
| Phương án không dùng AI | Checklist cố định theo loại theme + script đọc catalog JSON rồi đối chiếu file trên đĩa, báo ngay file nào thiếu trước khi build |
| Giả thuyết về AI (nếu có) | Không cần AI cho bước kiểm tra — kiểm tra file tồn tại là bài toán xác định, rule là đủ; AI chỉ có ích ở bước gen ảnh asset, không phải ở đây |
| Cảm nhận nhanh | Rule |

Quy trình nháp hiện tại:

```text
Quy trình nháp hiện tại: thêm theme bàn phím mới

1. Chốt mẫu theme: chọn phong cách (kawaii/neon/zodiac…), lấy id mới từ registry (~5')
2. Gen ảnh asset: background ngày/đêm, 5 keycap frame, popup, effect, preview (~60–90')
3. Làm GIF keycap (6-frame pulse) + MP4 preview zoompan (~20–30')
4. Chuẩn bị sound + font thật, ghi catalog entry tay (id, order, font, màu toolbar…) (~15')
5. Rà tay từng file xem đủ chưa, đối chiếu với catalog (~30') ← bottleneck
6. Đóng gói ZIP theo từng category, kiểm tra lại ref (~15')
7. Build thử / giao

Tổng: ~2–3 tiếng/theme. Bottleneck là bước 5: vừa lâu (~30') vừa vẫn sót lỗi.
```

### Problem Card #2

| Trường | Nội dung |
|---|---|
| Job Story | Khi một theme bị báo lỗi thiếu file, tôi muốn biết ngay file nào, theme nào, để không phải rà cả catalog 160 theme |
| Actor | Dev (người làm data theme) |
| Thời điểm / bối cảnh | Khi build báo lỗi, hoặc khi kiểm tra catalog sau một đợt làm nhiều theme; catalog hiện có 160 theme, 2.192 file |
| Quy trình hiện tại (3–7 bước) | 1. Nhận báo lỗi (build fail hoặc theme hỏng) — 2. Mở catalog JSON, tìm entry của theme đó — 3. Đối chiếu từng đường dẫn trong entry với file trên đĩa — 4. Nếu không thấy, rà tiếp các theme cùng đợt làm — 5. Sửa lại đường dẫn hoặc bổ sung file thiếu — 6. Build lại / đóng gói lại để kiểm chứng |
| Bottleneck (bước nào, mất bao nhiêu phút) | Bước 4–5 (theo quy trình nháp bên dưới) — rà tay từng đường dẫn: ~30–60'/lần, tùy mức độ; từng phải rà cả catalog vì id 48 trỏ file không tồn tại |
| Impact (nếu không giải thì sao) | Theme lỗi lọt ra ngoài; sửa chậm vì không biết lỗi ở đâu; mỗi lần sửa lại phải build lại từ đầu |
| Success metric (baseline → target) | Thời gian xác định file lỗi: 30–60' → <1'; số theme lỗi lọt qua kiểm tra: 1–2/đợt → 0 |
| Phương án không dùng AI | Script quét toàn bộ catalog, kiểm tra từng ref có file thật không, in báo cáo theme nào thiếu file nào |
| Giả thuyết về AI (nếu có) | Không cần AI — kiểm tra ref là bài toán xác định, AI không giúp gì thêm ở đây |
| Cảm nhận nhanh | Rule |

Quy trình nháp hiện tại:

```text
Quy trình nháp hiện tại: xác định file thiếu khi theme báo lỗi (Card #2)

1. Nhận báo lỗi: build fail, theme hỏng trên máy, hoặc user báo (~5')
2. Xác định theme nào lỗi từ thông báo — đôi khi báo chung chung, phải đoán (~5–10')
3. Mở catalog JSON, tìm entry của theme đó (~5')
4. Đối chiếu từng đường dẫn trong entry với file trên đĩa (~15–30')
5. Nếu không thấy: rà tiếp các theme cùng đợt làm, hoặc rà cả catalog (~30–60') ← bottleneck
6. Sửa đường dẫn sai / bổ sung file thiếu (~10')
7. Build lại / đóng gói lại để kiểm chứng (~10–15')

Tổng: ~1–2 tiếng/lần. Bottleneck là bước 4–5: rà tay từng đường dẫn, càng nhiều theme càng lâu.
```

### Problem Card #3

| Trường | Nội dung |
|---|---|
| Job Story | Khi đóng gói ZIP giao, tôi muốn mỗi theme tự chứa đủ folder (Background/Keycap/Popup/Sound/Effect…), để không phải đi gom file rời |
| Actor | Dev (người làm data theme) |
| Thời điểm / bối cảnh | Cuối mỗi đợt làm theme, khi giao Combo (160 theme, 2.192 file); mỗi lần sửa theme lại phải đóng gói lại |
| Quy trình hiện tại (3–7 bước) | 1. Gom file của từng theme từ nhiều folder nguồn (Keycap, Background, Popup…) — 2. Tạo cấu trúc folder chuẩn cho mỗi theme (ThemePreview/PreviewFullKeyboard/Background/Keycap/Popup/Sound/Effect) — 3. Copy file vào đúng folder, đổi tên nếu cần — 4. Kiểm tra lại ref trong catalog khớp với file trong ZIP — 5. Nén ZIP theo từng category — 6. Giao / upload |
| Bottleneck (bước nào, mất bao nhiêu phút) | Bước 1–3 — gom + copy tay: ~1–2 tiếng/đợt cho 160 theme; gom tay từng để sót ref |
| Impact (nếu không giải thì sao) | ZIP thiếu file → người nhận build lỗi; sửa lại phải đóng gói lại toàn bộ; tốn thời gian mỗi đợt giao |
| Success metric (baseline → target) | Thời gian đóng gói 1 đợt: 1–2 tiếng → <10'; số ref sót trong ZIP: từng có → 0 |
| Phương án không dùng AI | Script build đọc catalog JSON, tự tạo folder chuẩn + copy file + nén ZIP, báo lỗi ngay nếu thiếu file |
| Giả thuyết về AI (nếu có) | Không cần AI — đóng gói là workflow xác định, script là đủ |
| Cảm nhận nhanh | Workflow |

Quy trình nháp hiện tại:

```text
Quy trình nháp hiện tại: đóng gói ZIP giao (Card #3)

1. Liệt kê các theme trong đợt giao + category của chúng (~5')
2. Gom file của từng theme từ nhiều folder nguồn (Keycap, Background, Popup, Sound, Effect, Font…) (~30–60')
3. Tạo cấu trúc folder chuẩn cho mỗi theme (ThemePreview/PreviewFullKeyboard/Background/Keycap/Popup/Sound/Effect) (~15')
4. Copy file vào đúng folder, đổi tên nếu cần (~30') ← bottleneck
5. Kiểm tra lại ref trong catalog khớp với file trong ZIP (~20–30')
6. Nén ZIP theo từng category (~10')
7. Mở lại ZIP kiểm tra đủ file không, rồi giao/upload (~10')

Tổng: ~2–3 tiếng/đợt (160 theme). Bottleneck là bước 2–4: gom + copy tay, vừa lâu vừa dễ sót ref.

```

### Card muốn pitch nhất

- Card số: 2
- Vì sao: Có bằng chứng là lỗi đã thật sự xảy ra (id 48 trỏ tới file không tồn tại, id 87 thiếu popup, id 97 var4 404), không phải phỏng đoán. Bottleneck rõ và đo được: bước 4–5 rà tay từng đường dẫn mất 30–60'/lần. Card #1 cũng nghẽn ở bước rà file, nên giải được Card #2 thì giải luôn phần lớn Card #1.
- Câu hỏi muốn nhóm phản biện: Vấn đề này hiện chỉ mình (dev) gặp, có đủ người chịu ảnh hưởng để cả nhóm chọn không? Và nếu một script kiểm tra là đủ thì nhóm có chấp nhận kết luận No AI / Rule không?

### AI đã phản biện card thế nào

| Điểm yếu AI chỉ ra | Đồng ý? | Đã sửa gì |
|---|---|---|
| Card #2: bảng ghi bottleneck là "Bước 3–4", nhưng quy trình nháp bên dưới lại đánh dấu bước 4–5; hai quy trình không khớp nhau | Đồng ý | Sửa bottleneck trong bảng thành bước 4–5, lấy quy trình nháp làm chuẩn |
| Card #2: success metric có chèn giải pháp ("máy báo chính xác file nào…"), metric phải đo kết quả chứ không mô tả cách làm | Đồng ý | Bỏ phần mô tả giải pháp, chỉ giữ 30–60' → <1' và 1–2 lỗi/đợt → 0 |
| Card #2: chỉ có thời gian mỗi lần (30–60'), chưa có tần suất (mấy lần/tháng), nên chưa biết tổng thời gian mất thật sự | Đồng ý | Chưa sửa, cần đếm lại số lần gặp lỗi thiếu file trong tháng qua rồi bổ sung |
| Card #2: actor chỉ có mình (dev), chưa có người khác gặp vấn đề nên khó kiểm chứng với người thật ở CP4 | Đồng ý một phần | Giữ nguyên; user cuối chịu ảnh hưởng gián tiếp khi nhận theme hỏng. Đưa thành câu hỏi phản biện cho nhóm ở mục pitch |
| Cả 3 card đều có phương án không dùng AI (checklist/script) giải gần hết vấn đề, nên có thể không cần AI | Đồng ý | Không sửa; ghi rõ cảm nhận nhanh là Rule/Workflow, vì lab chấp nhận kết luận không cần AI nếu lập luận chặt |

---

## 4. Tôi đã tham gia phần nào (CP3 → CP7)

| Hoạt động | Tôi đã làm gì? | Kết quả / ảnh hưởng tới bài nhóm |
|---|---|---|
| Pitch Problem Card | Pitch Card #2: theme báo lỗi thiếu file, không biết file nào, phải rà cả catalog 160 theme | Card #2 được nhóm chọn làm candidate (35/35 điểm ở bảng 2.4) |
| Phản biện bài của bạn khác | Câu hỏi tôi đã đặt: <br>**Hỏi Công:** (1) "2–4 giờ hiểu cấu trúc Odoo là cho dự án đầu tiên hay dự án nào cũng vậy? Nếu chỉ lần đầu thì sau vài dự án có còn đau không?" (2) "Hiểu cấu trúc dữ liệu Odoo có phải là việc AI làm được không, hay thực ra chỉ cần tài liệu Odoo đầy đủ là xong?" (3) "3–5 giờ xử lý tài liệu RAG: bao nhiêu phần là việc lặp lại y hệt mỗi lần, bao nhiêu phần là việc cần hiểu nội dung?" (4) "Truy vết agent chạy sai 30–60 phút/lỗi — đó là lỗi của agent, hay là log của mình chưa đủ tốt?" <br>**Hỏi Quân:** (1) "15–30 phút hỏi lại phần thiếu mỗi lần — có phải vì nhóm không cập nhật tiến độ thường xuyên, chứ không phải thiếu công cụ?" (2) "20–30 phút đối chiếu rubric — có phải vì báo cáo viết lộn xộn nên tìm không ra, chứ không phải vì rubric khó?" (3) "Tìm quyết định cũ mất 10–20 phút/lần — vấn đề là tìm không ra, hay là nhóm không ghi quyết định lại một chỗ ngay từ đầu?" | Các câu hỏi chỉ ra card của Công có thể chỉ đau ở lần đầu hoặc do log chưa tốt, còn card của Quân có thể giải bằng sửa quy trình nhóm (No AI); góp phần để nhóm chọn Đạt #2, card có bằng chứng lỗi thật |
| Nhận phản biện | Câu hỏi tôi nhận được: (1) Sao không dùng test Lint có sẵn? (2) Mỗi data/theme phải viết một script à? | Tôi đã sửa gì: (1) Ghi rõ trong research 3.3 rằng Lint chỉ kiểm resource trong `res/`, không đọc catalog JSON nên không thay được bước đối chiếu. (2) Làm rõ giải pháp là một script dùng chung cho cả catalog, đọc catalog JSON và quét toàn bộ 160 theme; thêm theme mới không cần viết thêm script. Ghi hai câu này vào cột phản biện của bảng pitch 2.1 |
| Gom cluster / cây OST | Card #2, #3 của tôi được xếp vào cluster B (kiểm tra và vận hành asset/workflow kỹ thuật) | |
| Chọn candidate problem | Cung cấp bằng chứng thật cho Card #2: lỗi id 48, 87, 97 | Là lý do chính nhóm chấm "Pain có bằng chứng" 5/5 |
| Kiểm chứng / research | Cung cấp quy trình và số phút thật của việc rà lỗi; research Android Lint, JSON Schema, Crashlytics (có AI hỗ trợ) | Mục 3.3 báo cáo nhóm |
| Quy trình nhóm | Cung cấp 7 bước quy trình hiện tại và thời gian từng bước từ Card #2 | Mục 4.1, 4.2, 4.3 báo cáo nhóm |
| Problem Statement | Cung cấp actor, bottleneck, impact, metric từ trải nghiệm làm catalog | Mục 5, 7 báo cáo nhóm |
| Mức can thiệp AI | Đồng ý chọn Rule: kiểm tra file tồn tại là bài toán đúng/sai rõ ràng | Mục 6 báo cáo nhóm |
| Quyết định | Not Yet: cần phỏng vấn người khác trước vì bằng chứng mới từ một mình tôi | Mục 8 báo cáo nhóm |

---

## 5. Dùng AI

| Checkpoint | Tôi dùng AI để làm gì? | AI hữu ích ở đâu? | AI sai hoặc hời hợt ở đâu? | Tôi sửa gì bằng nhận định của mình? |
|---|---|---|---|---|
| CP1 Scan | Hỏi cách làm CP1; AI đưa ví dụ Job Story từ việc làm app bàn phím, sau đó định dạng bảng từ ý của tôi | Viết lại đúng mẫu "Khi… tôi muốn… để…" | Ví dụ dòng 1 dùng số "~3 theme/tuần, ~30'" do AI đưa ra; dòng 3 và 7 vẫn còn giải pháp trong Job Story ("render tự động") | Kiểm lại số dòng 1 theo thực tế; ghi rõ dòng 1 từ ví dụ của AI |
| CP2 Problem Card | Nhờ AI phản biện các card, gợi ý card nên pitch | Chỉ ra bottleneck Card #2 ghi lệch bước (3–4 so với 4–5), metric chèn giải pháp, thiếu tần suất | AI không biết tần suất thật nên không điền được số lần/tháng | Sửa bottleneck và metric; tần suất để bổ sung bằng số thật |
| CP4 Research | Tìm công cụ đã có cho bài toán kiểm tra asset thiếu | Tìm được Android Lint, JSON Schema/Ajv, Crashlytics kèm link chính thức | Lint chỉ kiểm resource trong `res/`, không kiểm catalog JSON — phải đọc kỹ mới thấy | Ghi rõ khoảng trống của từng công cụ; tự mở kiểm link |
| CP5 Quy trình | Chuyển quy trình 7 bước của Card #2 thành sơ đồ Mermaid, vẽ quy trình tương lai | Vẽ nhanh, tô rõ bottleneck, thêm phương án quay về | Số "Sau" ở before/after là kỳ vọng, chưa đo | Ghi chú rõ số liệu "Sau" chưa đo |
| CP5–6 Problem Statement | AI soạn nháp PS v0, v1 và tiêu chí đánh giá từ dữ liệu Card #2 | Đủ trường, metric có baseline → target và cách đo | Bản nháp do AI viết, nhóm phải tự đọc lại và sửa theo ý mình | (Nhóm tự sửa sau khi thảo luận) |
| CP6 Mức can thiệp / quyết định | AI soạn nháp bảng 4 mức, 4 rủi ro, quyết định | Lập luận vì sao Rule đủ, vì sao không cần Workflow/Agent | Value chỉ dựa trên trải nghiệm của tôi, chưa có phỏng vấn | Chọn Not Yet thay vì Go cho tới khi phỏng vấn xong |

---

## 6. Reflection (CP7)

Trả lời bằng trải nghiệm thật của bạn, tối thiểu 200 từ cho các câu 6.1–6.6 (không tính 6.7, câu này được chấm riêng ở tiêu chí C5). **Không dùng AI để viết thay.**

**6.1. Tôi học được gì khi nghe top 3 problems của các bạn khác?**

Bảng pitch có 9 ứng viên từ 3 người, mỗi người một kiểu vấn đề khác nhau.

Công (AI Engineer): Odoo chatbot 2–4 giờ/dự án, RAG xử lý tài liệu 3–5 giờ/bộ, debug agent 30–60 phút/lỗi — vấn đề sâu, tốn nhiều giờ mỗi lần, nhưng không xảy ra hàng ngày.

Quân (điều phối nhóm): deadline 15–30 phút/lần, đối chiếu rubric 20–30 phút, tìm quyết định cũ 10–20 phút/lần — vấn đề nhỏ, nhưng lặp lại nhiều lần, ảnh hưởng cả nhóm.

Tôi: theme thiếu asset 30'/theme, rà catalog 160 theme, đóng gói ZIP 1–2 giờ/đợt — nằm giữa hai kiểu trên: vừa lặp lại, vừa tốn giờ.

Bài học rút ra: bottleneck to chưa chắc đã đáng giải nhất, tần suất lặp lại cũng quan trọng không kém; vấn đề mạnh lên rất nhiều khi có bằng chứng ghi nhận thật (log lỗi id 48/87/97 của tôi) thay vì chỉ ước lượng; và vấn đề của một người khác vấn đề của cả team — Quân đau ở chỗ cả nhóm cùng chịu, còn card của tôi ban đầu chỉ có một actor là chính tôi.

**6.2. Nhóm có lúc nào bị "solution-first" (nghĩ giải pháp trước khi hiểu vấn đề) không? Lúc đó nhóm nhận ra và xử lý thế nào?**

Có, thấy rõ trong buổi làm việc hôm nay: giải pháp "viết script kiểm tra" xuất hiện gần như ngay sau khi viết xong problem, trước cả khi đo thời gian thật hay định nghĩa metric. Cả nhãn "Rule" cũng được chốt rất nhanh, khi chưa ai hỏi "liệu có cần AI ở đây không".

Nhóm nhận ra lúc nào: khi bị hỏi ngược lại — số 30' đo từ đâu, và giải pháp không dùng AI thì có đủ AI thực chiến không.

Xử lý thế nào: quay lại viết metric (thời gian tìm ra file lỗi 45–90' → dưới 1') và boundary (chỉ báo lỗi, không tự sửa catalog) trước, ghi rõ các số phút hiện mới là ước lượng cần đo lại, rồi mới chốt giải pháp là Rule.

**6.3. Tôi có đổi ý sau khi bị phản biện không? Kể một lần cụ thể.**

Có. Trước: tôi viết Card #2 với bottleneck "Bước 3–4" và success metric có kèm luôn cách làm ("máy báo chính xác file nào + dòng catalog nào").

Phản biện: khi nhờ AI phản biện card, nó chỉ ra bottleneck trong bảng lệch với quy trình nháp (bước 4–5), metric đang chèn giải pháp chứ không đo kết quả, và card chưa có tần suất lỗi mỗi tháng.

Sau: tôi sửa bottleneck thành bước 4–5, bỏ phần giải pháp khỏi metric, còn tần suất thì để bổ sung bằng số thật chứ không ước đại. Lúc đầu tôi nghĩ card đã đủ chặt vì có id lỗi cụ thể, sau phản biện mới thấy viết lẫn giải pháp vào metric là lỗi rất dễ mắc.

**6.4. Kết quả kiểm chứng (phỏng vấn/survey/research) có làm tôi bất ngờ không? Điều gì?**

Phỏng vấn/survey chính thức thì chưa làm — phần bấm giờ 1 tuần và hỏi designer/dev vẫn đang chờ. Nhưng có một kiểm chứng từ hồ sơ thật: rà lại log lỗi catalog thì thấy vấn đề không phải chuyện lẻ tẻ.

Điều bất ngờ: lỗi thiếu file không chỉ có một dạng. Ngoài file không tồn tại (id 48) còn có thiếu popup (id 87), file 404 (id 97 var4), sai tên file (id 123 typo nomal), tên file chứa {cate} chưa điền (id 134), cả sai màu toolbar 10 ký tự hex (id 91/92/94/95). Tức là lỗi rải khắp catalog, không phải một theme xui xẻo.

Điều đó làm problem mạnh lên: vì lỗi đã ghi nhận thật trong hồ sơ, không còn là cảm giác "hình như hay thiếu file" nữa.

**6.5. Điều khó nhất khi viết Problem Statement là gì?**

Viết đúng 1 vấn đề, không để lọt giải pháp vào trong câu problem: viết "cần script kiểm tra" đã là giải pháp, không phải vấn đề.

Định lượng bottleneck một cách trung thực khi chưa có số đo thật: ghi 30' mà chưa bấm giờ lần nào, không biết mình đang nói quá hay nói thiếu.

Vẽ boundary: nói rõ cái gì mình sẽ KHÔNG làm (không gen asset, không chấm chất lượng) khó hơn nói sẽ làm gì, vì cứ muốn ôm thêm.

Viết ngắn mà vẫn đủ cụ thể: phải có đủ actor, thời điểm, bottleneck và bằng chứng trong vài dòng, thiếu một thứ là câu problem mờ đi ngay.

**6.6. Nếu làm lại, tôi sẽ đổi gì? Tôi sẽ phản biện nhóm mạnh hơn ở điểm nào?**

Đo thời gian trước khi pitch: số 30' hôm nay chỉ là ước lượng, chưa bấm giờ thật lần nào, mà cả card đứng trên con số đó.

Hỏi sớm câu "có thật sự cần AI ở đây không", thay vì chốt Rule rồi mới bị hỏi lại lý do.

Ép nhóm thừa nhận 3 card của mình thực ra là 1 vấn đề ngay từ lúc xếp hạng, thay vì để 3 card riêng rồi mới gộp sau.

Đòi bằng chứng ghi nhận trước khi xếp hạng: log lỗi thật (id 48, 87, 97) thay vì cảm giác "hay gặp".

Phản biện mạnh hơn ở điểm "ai khác cũng đau": actor của card #2 chỉ có một mình tôi, nếu không chứng minh được người khác cũng gặp thì problem yếu đi một nửa.

**6.7. Hiểu bài:** giải thích bằng 5–8 câu, không nhìn tài liệu, chuỗi *problem → quy trình → metric → boundary → mức can thiệp AI → quyết định* của bài nhóm mình.

Problem (Card #2): khi một theme bị báo lỗi thiếu file, dev không biết ngay file nào, theme nào, phải rà tay cả catalog 160 theme.

Quy trình hiện tại có 7 bước; bottleneck là bước 4–5, đối chiếu tay từng đường dẫn trong catalog với file trên đĩa, mất khoảng 45–90' mỗi lần.

Metric: thời gian tìm ra file lỗi từ 45–90' xuống dưới 1'; số theme thiếu file lọt qua khi giao từ 1–2/đợt xuống 0.

Boundary: giải pháp chỉ báo lỗi, không tự sửa đường dẫn, không xóa entry, không tạo hay đổi tên file; dev quyết định mọi thay đổi.

Mức can thiệp: Rule — một script đối chiếu catalog với file trên đĩa, vì đường dẫn chỉ có hai khả năng là có file hoặc không, không cần AI dự đoán hay tạo nội dung.

Quyết định: Go, phạm vi nhỏ — giải pháp rẻ và làm được nên pilot script trên catalog hiện tại, nhưng bằng chứng mới từ một mình tôi nên vẫn cần phỏng vấn thêm dev khác về tần suất lỗi.

---

## 7. Tài liệu tham khảo

-
