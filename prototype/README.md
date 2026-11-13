# Prototype — T3 · Trợ lý đổi chuyến (S4 + S8)

Câu AI nói theo nguyên văn `spec.md` §3.1, §3.2. Mức tự chủ theo §4.

## Mở thế nào

- File: `prototype/index.html`. Mở thẳng bằng trình duyệt, không cần cài gì.
- Công cụ: HTML + CSS + JS thuần, một file.
- Phần mock: toàn bộ. Dữ liệu lấy từ đặt chỗ dựng TRV-7Q2K của track T3. Câu trả lời của AI viết sẵn theo kịch bản.
- Lời gọi AI thật: **không có**.
- Link trực tiếp tới từng kịch bản: `index.html?s=S4`, `index.html?s=S8`.

Thanh trên cùng có nút chọn S4 / S8, nút **Làm lại** và ô **Hiện số HAX** để bật/tắt số chú thích.

## Bấm qua ca khó

**S4: "Thôi huỷ hết đi, hoàn tiền cho mình."**
1. Bấm tin gợi ý ở cuối khung chat để gửi.
2. AI trả lời (§3.1): **chưa gửi** gì, kèm ô căn cứ (②). **Hộp hoàn vé (④) hiện ngay**, là bản nháp cho cả 2 người. Nút **Gửi yêu cầu hoàn** khoá tới khi khách tick *"Tôi hiểu yêu cầu hoàn gửi rồi không rút lại được, và tôi sẽ mất cả 2 chỗ"*.
3. Bên dưới là thẻ giữ chỗ BM 201, nhỏ hơn, đếm ngược 20 phút (③).
4. Có các đường đi tiếp:

| Khách làm | Prototype làm |
|---|---|
| Gửi tin gợi ý **"gửi đi"** | Không gửi. AI nhắc: tick rồi bấm nút, chữ trong chat không tính |
| Tick rồi bấm **Gửi yêu cầu hoàn** | Gửi cho 2 người, nhả chỗ BM 201, báo "Đã gửi yêu cầu hoàn lúc …". Không có câu "nếu đổi ý" |
| Bấm **Không, quay lại** | Bỏ tick, bản nháp vẫn để đó, chưa gửi gì |
| Bấm **Đổi sang BM 201 (2 người)** | Đóng hộp hoàn vé (chưa gửi gì), hiện thẻ xác nhận đổi chuyến: phí 0 đ, "lần đổi miễn phí duy nhất", đếm ngược giữ chỗ |
| Bấm **Nhả chỗ** | Nhả chỗ BM 201, thẻ đổi chuyến (nếu đang mở) bị khoá |
| Gửi tin gợi ý **"Chỉ hoàn vé của mình thôi"** | AI không soạn hoàn cho một người (bé 5 tuổi), tự chuyển nhân viên kèm tóm tắt |
| Không làm gì 20 phút | Chỗ tự nhả, thẻ đổi chuyến bị khoá, bản nháp hoàn vé vẫn còn |

**S8: "Chuyến 7h mai cho bé Bình bay trước, mình đi chuyến sau nha"**
1. Bấm tin gợi ý để gửi.
2. AI trả lời (§3.2) và **tự chuyển nhân viên**: hiện dải (⑦) *"Đang chuyển nhân viên · chờ khoảng 5 phút"* cùng nút **Huỷ, quay lại chat**.
3. Ô căn cứ (②) ghi bé Gia Bình 5 tuổi. Ô "Trợ lý không làm" (⑥) có tóm tắt đã gửi nhân viên. Trên màn hình **không có nút** giữ chỗ hay đổi vé riêng cho bé.
4. Bấm **Giữ BM 201 cho 2 người** hoặc **Giữ BM 205 cho 2 người**: hiện thẻ giữ chỗ (③). Bấm **Đổi sang …** mở thẻ xác nhận, giống S4.

## Ảnh có đánh số

| Ảnh | Nội dung |
|---|---|
| `anh-1-S4.png` | S4, ngay sau câu trả lời của AI: hộp hoàn vé hiện sẵn, nút gửi còn khoá. Có số ①–⑤ |
| `anh-2-S8.png` | S8, AI đã chuyển nhân viên, khách đã giữ BM 201 cho 2 người rồi bấm "Đổi sang BM 201": thẻ xác nhận đổi chuyến đang mở. Có đủ ba mức tự chủ và số ①②③⑤⑥⑦ |

## Chú thích các số

| # | Thể hiện gì | Nguyên tắc HAX/PAIR | Mức tự chủ |
|---|---|---|---|
| ① | Thanh báo khách đang nhắn với trợ lý AI; việc không đảo lại được luôn chờ khách xác nhận | G1 · Luật AI 134/2025 Điều 11 | Lời hứa chung (§4.5) |
| ② | Ô "Căn cứ mình dùng": các dòng AI đã đọc từ `tra_cuu_dat_cho` | G11 · PAIR Explainability + Trust | `tra_cuu_dat_cho`: tự làm (chỉ đọc) |
| ③ | Thẻ giữ chỗ: "Chưa đổi vé", đếm ngược 20 phút, nút **Nhả chỗ** và **Đổi sang …** | G9 sửa dễ | `giu_cho_chuyen_moi`: tự làm, hoàn tác được. Nút đổi mở thẻ xác nhận của `doi_chuyen_bay` (khách duyệt) |
| ④ | Hộp hoàn vé: bản nháp AI soạn, dòng đỏ "Gửi rồi không rút lại được", tiền về đâu, bao lâu, không bồi thường, nút gửi khoá tới khi tick | G10 · PAIR Errors + Graceful Failure | `gui_yeu_cau_hoan_ve`: AI soạn, khách duyệt |
| ⑤ | Nút **Gặp nhân viên** luôn hiện | G8 gạt bỏ dễ | `chuyen_nhan_vien`: đường lui khách tự gọi |
| ⑥ | Ô "Trợ lý không làm · đã chuyển nhân viên", kèm tóm tắt đã gửi | G1 · G10 | Luật trẻ em (§4.4): việc bị chặn, `chuyen_nhan_vien` bắt buộc |
| ⑦ | Dải "Đang chuyển nhân viên · chờ khoảng 5 phút", nút **Huỷ, quay lại chat** | PAIR Errors + Graceful Failure | `chuyen_nhan_vien`: tự làm, khách huỷ được |

Phần dưới rail chú thích có bảng ba kiểu nhãn: *AI tự làm · hoàn tác được* / *Cần bạn xác nhận* / *Trợ lý không làm*.

## Giới hạn của bản mock

- Đếm ngược chạy thật 20 phút. Muốn demo cảnh hết giờ thì mở console, gõ `expireHold()`.
- Không giả lập cảnh 10 phút chưa ai nhận ca rồi đẩy lên trưởng ca, chỉ ghi trong dải chuyển nhân viên.
- Mã yêu cầu hoàn và mã vé mới không có trong dữ liệu track, nên prototype ghi "gửi qua SMS/email" thay vì in mã giả.
