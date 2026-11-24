# Danh sách lớp v0 — Lê Trung Sang · G10

## DMS

| # | Lớp / thuộc tính | Giá trị | Để làm gì (chức năng DMS) | Nhìn thấy được trên IR? |
|---|---|---|---|---|
| 1 | eye_state | open / closed / unknown | Phát hiện chớp mắt, buồn ngủ và mất tập trung | Có, trừ khi kính phản xạ hoặc che mắt |
| 2 | glasses | none / clear / sun / unknown | Hiệu chỉnh model và giảm nhầm mắt/bờ mắt trong các tình huống đeo kính | Có thể; kính râm trên NIR có thể trông trong suốt |
| 3 | gaze_zone | road / mirrors / cluster / center / lap / other | Đánh giá tài xế có nhìn đường hay phân tán tầm nhìn | Có, nếu hướng mắt và đầu nhìn rõ |
| 4 | face13 | 13 điểm khuôn mặt | Ước lượng pose đầu, yaw/pitch và phát hiện trạng thái khuôn mặt | Có với mặt đủ rõ và kích thước |
| 5 | hand | whose / side / on_wheel | Phát hiện tay rời vô lăng và hành vi sử dụng tay | Có, nhưng ảnh tối có thể không phân biệt rõ |
| 6 | phone | held / mounted / lap | Phát hiện tài xế sử dụng điện thoại để cảnh báo phân tán | Chỉ khi thấy hình dạng cạnh, góc hoặc màn hình |
| 7 | seatbelt | worn_correct / worn_incorrect / not_worn / unknown | Kiểm tra việc thắt dây và phát hiện việc thắt sai | Thường có thể, tùy độ tương phản và che khuất |

## OMS

| # | Lớp / thuộc tính | Giá trị | Để làm gì (chức năng OMS) | Nhìn thấy được trên IR? |
|---|---|---|---|---|
| 1 | person | rear_left / rear_middle / rear_right / unknown | Nhận biết người trên ghế sau để kiểm soát túi khí và cảnh báo có người | Có nếu hình dạng người đủ rõ |
| 2 | child_seat | occupied no / unknown, theo ghế | Nhận biết ghế trẻ em trống để hỗ trợ quy tắc túi khí và giám sát ghế | Có trong nhiều trường hợp; che khuất cần unknown |
| 3 | infant_seat | facing rear / front, theo ghế | Nhận biết nôi em bé và hướng đặt để xử lý nhắc nhở hoặc túi khí | Có nếu hình dạng ghế em bé rõ |
| 4 | object | bag / box / cup / other, theo ghế | Nhận biết đồ vật để cảnh báo quên đồ hoặc phân tách vật với người | Có, dựa trên hình dạng; IR không cho thông tin màu |
| 5 | seatbelt_state | worn_correct / worn_incorrect / not_worn / unknown | Kiểm tra an toàn của người trên ghế | Chỉ có thể nếu dây và tư thế được nhìn thấy |
| 6 | empty_seat | ghế trống, không gán box | Tránh cảnh báo người/vật ở ghế trống | Có khi vùng ghế không bị che hoặc thiếu tương phản |
| 7 | occupied_status | ghế có người/vật hay trống | Hỗ trợ occupancy monitoring và quản lý trạng thái ghế | Có khi mô hình phân tích được cả người và vật |

## 2 câu hỏi leo thang

1. Câu hỏi: Khi ghế trẻ em bị một vật che gần hết, guideline nên cho phép gán `child_seat` + `object` hay chỉ gán object rõ nhất?
   Khung ví dụ: G10 S03 hoặc S04.
   Bạn tạm gán thế nào và vì sao: Giữ box nhìn thấy và dùng `unknown` cho thuộc tính không xác định; không đoán phần bị che.

2. Câu hỏi: Nếu dây an toàn chỉ thấy ở một phần và không xác định được đúng/sai, có nên thêm giá trị trạng thái tách khỏi `unknown` không?
   Khung ví dụ: G10 S01_ir.
   Bạn tạm gán thế nào và vì sao: Chọn `unknown` theo Guideline, không suy dây an toàn từ ảnh RGB của cùng cảnh.
