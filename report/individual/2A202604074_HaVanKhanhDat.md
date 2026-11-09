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

-

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

**6.2. Nhóm có lúc nào bị "solution-first" (nghĩ giải pháp trước khi hiểu vấn đề) không? Lúc đó nhóm nhận ra và xử lý thế nào?**

**6.3. Tôi có đổi ý sau khi bị phản biện không? Kể một lần cụ thể.**

**6.4. Kết quả kiểm chứng (phỏng vấn/survey/research) có làm tôi bất ngờ không? Điều gì?**

**6.5. Điều khó nhất khi viết Problem Statement là gì?**

**6.6. Nếu làm lại, tôi sẽ đổi gì? Tôi sẽ phản biện nhóm mạnh hơn ở điểm nào?**

**6.7. Hiểu bài:** giải thích bằng 5–8 câu, không nhìn tài liệu, chuỗi *problem → quy trình → metric → boundary → mức can thiệp AI → quyết định* của bài nhóm mình.

---

## 7. Tài liệu tham khảo

-
