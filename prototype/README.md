# Prototype — T3 · Trợ lý đổi chuyến (S4 + S8)

> **Bản khung.** Luồng bấm và vị trí các số chú thích đã có. Câu chữ của AI, mức tự chủ từng tool và nguyên tắc HAX/PAIR **còn tạm**, sẽ chốt sau khi viết xong §3 và §4 trong `spec.md`. Chỗ nào ghi `[chờ bổ sung]` là còn thiếu dữ liệu.

## Mở thế nào

- File: `prototype/index.html`. Mở thẳng bằng trình duyệt, không cần cài gì.
- Công cụ: HTML + CSS + JS thuần, một file.
- Phần mock: toàn bộ. Dữ liệu lấy từ đặt chỗ dựng TRV-7Q2K của track T3. Câu trả lời của AI viết sẵn theo kịch bản.
- Lời gọi AI thật: **không có**.
- Link trực tiếp tới từng kịch bản: `index.html?s=S4`, `index.html?s=S8`.

## Bấm qua ca khó

Thanh trên cùng có hai nút chọn kịch bản S4 / S8, nút **Làm lại** và ô **Hiện số HAX** để bật/tắt số chú thích.

**S4: "Thôi huỷ hết đi, hoàn tiền cho mình."**
1. Bấm tin gợi ý ở cuối khung chat để gửi.
2. AI trả lời "chưa gửi", kèm ô căn cứ (②) và tự giữ 2 chỗ BM 201 07:00, đếm ngược 20 phút (③).
3. Có ba đường đi tiếp:
   - **Đổi sang BM 201**: hiện hộp xác nhận đổi chuyến (cần khách duyệt).
   - **Nhả chỗ**: hoàn tác việc giữ chỗ.
   - **Vẫn muốn hoàn vé…**: hiện hộp xác nhận hoàn vé (④). Nút gửi bị khoá tới khi khách tick "không rút lại được".
4. Nút **Gặp nhân viên** (⑤) luôn bấm được.

**S8: "Chuyến 7h mai cho bé Bình bay trước, mình đi chuyến sau nha"**
1. Bấm tin gợi ý để gửi.
2. AI từ chối tách vé cho bé, dẫn căn cứ "bé Gia Bình 5 tuổi" (②) và hiện ô "trợ lý không làm" (⑥). Trên màn hình **không có nút** đổi vé riêng cho bé.
3. Bấm **Chuyển nhân viên kèm tóm tắt**: chat chuyển cho nhân viên, kèm tóm tắt ngữ cảnh.
4. Trong lúc chờ, khách có thể giữ 2 chỗ cho hai mẹ con bay cùng chuyến BM 201 hoặc BM 205 (③), rồi đổi chuyến nếu muốn (cần xác nhận).

## Ảnh có đánh số

| Ảnh | Nội dung |
|---|---|
| `anh-1-S4.png` | S4, sau khi bấm "Vẫn muốn hoàn vé…": có số ①–⑤ |
| `anh-2-S8.png` | S8, sau khi đã chuyển nhân viên và giữ chỗ BM 201: có số ①②③⑤⑥ |

## Chú thích các số *(tạm, chốt theo §3/§4)*

| # | Thể hiện gì | Nguyên tắc HAX/PAIR | Mức tự chủ |
|---|---|---|---|
| ① | Thanh báo khách đang nhắn với trợ lý AI, và việc không đảo lại được luôn chờ khách xác nhận | G1 · Luật AI 134/2025 Điều 11 | (lời hứa chung) |
| ② | Ô "Căn cứ mình dùng": các dòng AI đã đọc từ `tra_cuu_dat_cho` | G11 · PAIR Explainability + Trust | `tra_cuu_dat_cho`: tự làm (chỉ đọc) |
| ③ | Thẻ giữ chỗ: đếm ngược 20 phút, nút "Nhả chỗ" | G9 sửa dễ | `giu_cho_chuyen_moi`: tự làm, hoàn tác được |
| ④ | Hộp xác nhận hoàn vé: hậu quả, tiền về đâu, bao lâu, tick "không rút lại được" | G10 · PAIR Errors + Graceful Failure | `gui_yeu_cau_hoan_ve`: cần khách xác nhận |
| ⑤ | Nút "Gặp nhân viên" luôn hiện | G8 gạt bỏ dễ | `chuyen_nhan_vien`: đường lui |
| ⑥ | Ô "Trợ lý không làm": tách vé cho trẻ bay một mình, kèm tóm tắt gửi nhân viên | G1 · G10 | Việc cấm: không có nút làm |

Ngoài ra, hộp xác nhận **đổi chuyến** (bấm "Đổi sang BM 201") minh hoạ mức *cần duyệt* cho `doi_chuyen_bay`.

## Còn thiếu / sẽ bổ sung

- [ ] Câu AI nói nguyên văn ở S4 và S8, theo §3.
- [ ] Mức tự chủ đã chốt cho từng tool, theo §4. Bản này đang giả định: giữ chỗ = tự làm, đổi chuyến và hoàn vé = cần khách xác nhận, tách vé cho trẻ = cấm.
- [ ] Thời gian chờ nhân viên, mã yêu cầu hoàn, mã vé mới (đang ghi `[chờ bổ sung]`).
- [ ] Lập luận cho §5: các cách hiện khác đã cân nhắc và vì sao loại.
- [ ] Chụp lại ảnh sau khi chốt nội dung.
