# Bài nộp LAB5 — T3 · Nhóm DungPhucTrung
**Lớp:** L3B · **Bàn / zone:** ____ · **Track:** T3
| Họ và Tên | Mã Học Viên | Việc đã làm |
|---|---|---|
|Nguyễn Minh Phúc|2A202603894|Chưa làm gì cả|
|Phạm Quang Dũng|2A202603896|Chưa làm gì cả|
|Nguyễn Văn Anh Trung|2A202603903|Chưa làm gì cả|

## §1. Lát cắt & phạm vi
- Trong Đặt chỗ của tôi, khi hành khách vừa nhận tin chuyến bay bị huỷ và nhắn hỏi, AI đề xuất và giữ chỗ chuyến thay thế, hỏi lại cho rõ, đổi vé, hay chuyển nhân viên, để khách tới nơi kịp mà không mất vé hay tiền vì một thao tác không đảo lại được.
- Các việc tính năng KHÔNG làm
  - Việc 1: **Không đổi tên người bay**, vì việc này cần xác minh giấy tờ theo quy định của hãng. AI đổi sai thì khách bị từ chối lên máy bay, nên luôn chuyển nhân viên.

  - Việc 2: **Không hứa hay xử lý bồi thường tiền mặt**, vì chuyến BM 213 huỷ do thời tiết và chính sách hãng Bay Mẫu là không bồi thường. AI hứa sai thì khách mất lòng tin và nhân viên phải đi gỡ.

  - Việc 3: **Không nhận số thẻ hay OTP, không xử lý thanh toán**, vì lát cắt chỉ là đổi chuyến hoặc hoàn vé trên đặt chỗ đã có. Xin thông tin thanh toán trong chat là mở đường cho lừa đảo và lộ dữ liệu.


## §2. Kịch bản rủi ro  (chặng 2)
<!-- - ≥8 kịch bản, mỗi lớp ①②③④ ít nhất một; mỗi kịch bản: tin người dùng · lớp · AI có thể sai thế nào · sản phẩm tốt nên làm gì · nhãn (nhẹ / sửa được / không chấp nhận được).
- Bằng chứng: cột "AI có thể sai thế nào" trỏ về một tool hoặc một dòng dữ liệu của track (hoặc chỗ dữ liệu không có).
- Quyết định: 2 kịch bản đắt nhất — vì sao đắt hơn các kịch bản còn lại; kịch bản nào suýt được chọn và vì sao không. -->

| # | Tin người dùng nhắn | Lớp | AI có thể sai thế nào | Sản phẩm tốt nên làm gì | Nhãn | Thành viên làm |
|---|---|---|---|---|---|---|
| S1|”Đổi đi”|2|Trỏ ngay lập tức về `doi_chuyen_bay` mà không có thông tin về chuyến bay muốn đổi|Hỏi khách xem khách muốn đổi sang chuyến nào|Không chấp nhận được|Nguyễn Văn Anh Trung
| S2 | | | | | | |
| S3 | | | | | | |
| S4 | | | | | | |
| S5 | | | | | | |
| S6 | | | | | | |
| S7 | | | | | | |
| S8 | | | | | | |

### 2 kịch bản đắt nhất
- **Sx — [tên ngắn]:** vì sao đắt hơn các kịch bản còn lại.
- **Sy — [tên ngắn]:** vì sao đắt hơn các kịch bản còn lại.

### Kịch bản suýt được chọn
- **Sz — [tên ngắn]:** vì sao suýt chọn, vì sao cuối cùng không chọn.


## §3. Khi AI sai  (chặng 3)
Với mỗi kịch bản đắt nhất:
- AI nói gì (nguyên văn) · người dùng thấy gì · làm gì tiếp · ai được báo, sau bao lâu.
- Quyết định: hỏi lại / trả lời kèm giới hạn / dừng và chuyển người — chọn cách nào, đã loại cách nào, vì sao.
- Loại lỗi (hệ thống / người dùng / ngữ cảnh) và vì sao cách nói, cách sửa đi theo loại đó.
- 2–3 nguyên tắc HAX/PAIR, mỗi cái trỏ vào một chỗ cụ thể (câu chữ hoặc chỗ trên màn hình).
- Lỗi nào sửa câu chữ không cứu được (nếu có), và thiết kế cứu nó thế nào.

## §4. Mức tự chủ  (chặng 4)
Với mỗi tool:
- Mức của nhóm (tự làm / cần người duyệt / cấm). Nếu cần người duyệt: ai duyệt · người duyệt thấy gì · quá hạn thì sao.
- Lý do theo cost-of-error: sai thì ai chịu gì · đảo lại được không · chờ người thì mất gì.
- Phương án đã cân nhắc và vì sao loại.
Thêm:
- Tool khó xếp nhất: mỗi người từng chọn gì, cái giá của mỗi phía (trỏ về kịch bản ở §2), nhóm chốt thế nào.
- Thử mức đã đặt trên 2 kịch bản đắt nhất + 1 kịch bản bình thường: cái sai có bị chặn không? còn việc nào làm khi lẽ ra phải hỏi? người dùng bình thường có phải chờ vô ích không?
- Luật thêm hoặc tool tách bước (nếu có), và vì sao.
- Một mức tự chủ đã đổi lời hứa nào với người dùng.

## §5. Prototype  (chặng 5)
- Link hoặc file · công cụ · phần nào mock · có lời gọi AI thật không.
- 1–2 ảnh có đánh số; mỗi số: thể hiện gì · nguyên tắc HAX/PAIR nào · mức tự chủ nào.
- Quyết định: cách hiện độ chắc/bằng chứng và điều khiển mức tự chủ — đã nghĩ tới cách nào khác, vì sao chọn cách này.

## §6. Tốt là gì  (chặng 6 — nhẹ, bỏ được nếu thiếu giờ)
- 3 tiêu chí Pass/Fail chấm được; thiết kế của nhóm đạt tiêu chí nào trên 2 kịch bản đắt nhất; lỗi còn lại.

## §7. Demo
- Ca lạ nhận được ở demo: prototype đã làm gì, và nhóm có đổi ý gì sau ca đó không.
