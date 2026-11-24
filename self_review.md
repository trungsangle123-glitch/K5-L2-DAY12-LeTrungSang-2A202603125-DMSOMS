# Tự đánh giá — Lê Trung Sang · G10

## 1. Tự rà soát 4 cảnh

| Ảnh | Đối tượng | Loại lỗi | Ghi chú | Đã sửa? |
|---|---|---|---|---|
| S01_rgb | person / seatbelt | ok | Kiểm tra ghế theo vị trí trong xe | chưa cần |
| S01_ir | person / seatbelt | ok hoặc guess | Chỉ giữ unknown nếu không nhìn thấy rõ dây | đã/đang kiểm tra |
| D01 | face / eyes | lr_flip | Đổi trái/phải theo tài xế dù ảnh xoay | đã kiểm tra |
| D03 | hand | on_wheel | Tài xế tự lái nên tay rời vô lăng là bình thường | đã kiểm tra |

## 2. Lỗi mình lặp lại nhiều nhất hôm nay

Lỗi: Có thể nhầm trái/phải ghế hoặc trái/phải mắt theo vị trí trong ảnh thay vì theo người/xe.

Vì sao mình mắc: Dễ mặc định trái/phải dựa trực tiếp trên màn hình.

Lần sau tránh bằng cách: Lập tức chỉ ra ghế theo hướng người nhìn về phía trước, và mắt/tay theo hai bên cơ thể của người lái.
