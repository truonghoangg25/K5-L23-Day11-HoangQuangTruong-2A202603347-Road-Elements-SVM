# Bảng rà soát 6 ảnh — QC1 Road v1.0

| Ảnh | File nguồn | Cảnh báo lint | Kết quả đối chiếu |
|---|---|---|---|
| A01 | `A01_bc5fadac-fa6dd225.jpg` | 2 | Chưa xác minh |

- [QC1-02 nặng] A01 lane: chưa có R1 (bỏ qua nếu thật sự không thấy vạch)
- [QC1-05 chính] A01 lane: 4 polyline cùng position L1: vạch đứt có bị tách không?

| A05 | `A05_b2576c8c-2de20b8a.jpg` | 2 | Đã xem ảnh gốc; chờ coach duyệt ngoại lệ QC1-02 |

- [QC1-02 nặng] A05 lane: chưa có L1 (bỏ qua nếu thật sự không thấy vạch)
- [QC1-02 nặng] A05 lane: chưa có R1 (bỏ qua nếu thật sự không thấy vạch)

| A06 | `A06_b8c66e31-37045eec.jpg` | 9 | Chưa xác minh |

- [QC1-02 nặng] A06 lane: chưa có R1 (bỏ qua nếu thật sự không thấy vạch)
- [QC1-04 chính] A06 lane#10@(711,449): điểm đầu cao hơn điểm cuối: có vẽ từ xa về gần không?
- [QC1-04 chính] A06 lane#12@(180,410): điểm đầu cao hơn điểm cuối: có vẽ từ xa về gần không?
- [QC1-04 chính] A06 lane#13@(192,423): điểm đầu cao hơn điểm cuối: có vẽ từ xa về gần không?
- [QC1-04 chính] A06 lane#14@(691,462): điểm đầu cao hơn điểm cuối: có vẽ từ xa về gần không?
- [QC1-04 chính] A06 lane#15@(435,422): điểm đầu cao hơn điểm cuối: có vẽ từ xa về gần không?
- [QC1-04 chính] A06 lane#18@(0,422): điểm đầu cao hơn điểm cuối: có vẽ từ xa về gần không?
- [QC1-04 chính] A06 lane#19@(0,411): điểm đầu cao hơn điểm cuối: có vẽ từ xa về gần không?
- [QC1-05 chính] A06 lane: 9 polyline cùng position L1: vạch đứt có bị tách không?

| A08 | `A08_c0deebc1-16cfa791.jpg` | 7 | Chưa xác minh |

- [QC1-02 nặng] A08 lane: chưa có R1 (bỏ qua nếu thật sự không thấy vạch)
- [QC1-04 chính] A08 lane#7@(517,302): điểm đầu cao hơn điểm cuối: có vẽ từ xa về gần không?
- [QC1-04 chính] A08 lane#10@(0,360): điểm đầu cao hơn điểm cuối: có vẽ từ xa về gần không?
- [QC1-04 chính] A08 lane#11@(96,420): điểm đầu cao hơn điểm cuối: có vẽ từ xa về gần không?
- [QC1-04 chính] A08 lane#12@(80,497): điểm đầu cao hơn điểm cuối: có vẽ từ xa về gần không?
- [QC1-04 chính] A08 lane#13@(566,279): điểm đầu cao hơn điểm cuối: có vẽ từ xa về gần không?
- [QC1-05 chính] A08 lane: 10 polyline cùng position L1: vạch đứt có bị tách không?

| B03 | `B03_04267_RV.png` | 3 | Chưa xác minh |

- [QC1-11 chính] B03 road_curb#12@(740,289): chỉ 3 điểm: trên fisheye hãy đặt điểm theo cung
- [QC1-11 chính] B03 traffic_sign#8@(1130,357): gợi ý edge_zone = bật (tâm box ngoài 80 % bán kính; tự kiểm lại)
- [QC1-10 nhẹ] B03 traffic_sign#6@(794,268): box thấp hơn 8 px: không bắt buộc

| B11 | `B11_07282_RV.png` | 0 | Đã xem ảnh gốc; chờ coach xác nhận phạm vi |



## Thống kê XML của 6 ảnh

| Ảnh | Shapes | Image tags | Tổng phần tử XML |
|---|---:|---:|---:|
| A01 | 11 | 4 | 15 |
| A05 | 3 | 4 | 7 |
| A06 | 20 | 4 | 24 |
| A08 | 21 | 4 | 25 |
| B03 | 16 | 4 | 20 |
| B11 | 0 | 4 | 4 |
| **Tổng** | **71** | **24** | **95** |

Lưu ý: Đây là số lượng trích xuất từ XML, không phải số nhãn đã kiểm thủ công.

## Tình trạng đối chiếu ảnh và annotation overlay

- A05: XML có `drivable`, `road_curb`, `crosswalk`; không có `lane`. Đã xem ảnh gốc và không thấy vạch sơn L1/R1. Đề xuất ngoại lệ QC1-02, chờ coach xác nhận.
- B11: Manifest ghi `fisheye_rear`, nhóm `extra`. Đã xem ảnh gốc: thấy vạch ô đỗ và vùng gạch chéo, không thấy vạch phân làn L1/R1. XML không có shapes. Vẫn chờ coach xác nhận phạm vi gán nhãn cho ảnh nhóm `extra`.
- A01, A06, A08, B03: Các cảnh báo lint đã được liệt kê; chưa xác minh từng shape với ảnh và guideline. Không xem cảnh báo lint đơn lẻ là lỗi đã xác nhận.

Kết luận tạm thời: Chưa đủ căn cứ để chốt số lỗi QC1 hoặc tỷ lệ lỗi. Các trường hợp nêu trên cần được đối chiếu với ảnh, annotation và guideline.

## Đối chiếu với guideline Road v1.0

- A05: Đã xem ảnh gốc, không thấy vạch sơn L1/R1; cần coach xác nhận trước khi áp dụng ngoại lệ QC1-02.
- B11: Đã xem ảnh gốc, không thấy vạch phân làn L1/R1; vẫn cần coach xác nhận phạm vi gán nhãn của ảnh nhóm `extra`. Không kết luận hợp lệ chỉ từ số shapes bằng 0.
- A01/A06/A08/B03: Chưa chốt lỗi từ cảnh báo lint đơn lẻ; cần đối chiếu từng shape với quy tắc vị trí, hình học và thuộc tính trong guideline.

Ghi chú: Các nhận xét trong bảng là trạng thái rà soát, không phải kết luận QC cuối cùng. Chỉ ghi “đã xem ảnh/overlay” sau khi việc kiểm tra đó thực sự hoàn tất.

## Kết quả kiểm tra trực tiếp ảnh gốc bổ sung

- **A05_b2576c8c-2de20b8a.jpg:** Đã xem ảnh gốc. Không thấy vạch sơn phân làn L1/R1 trên mặt đường. Đề xuất ngoại lệ QC1-02 cho cả L1 và R1; vẫn cần coach xác nhận theo quy định checkpoint trước khi chốt ngoại lệ.
- **B11_07282_RV.png:** Đã xem ảnh fisheye rear. Có vạch phân ô đỗ xe màu trắng và vùng gạch chéo màu vàng quanh khu vực đỗ xe dành cho người khuyết tật; không thấy vạch phân làn L1/R1. Không tính vạch ô đỗ xe là lane theo QC1-03. Việc không có lane shape ở B11 không được xem là lỗi thiếu lane dựa trên ảnh này.
