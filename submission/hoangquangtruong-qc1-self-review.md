# Phiếu QC 1 — Road v1.0

Lô được kiểm (học viên): Hoàng Quang Trường
Người kiểm (học viên): Hoàng Quang Trường — tự kiểm bài cá nhân
Ngày: 2026-11-22
Phiên bản guideline: Road v1.0
File được kiểm (tên + `revision` trong manifest): hoangquangtruong-front.zip; hoangquangtruong-fisheye.zip (revision: 1)
Số ảnh đã đối chiếu trực tiếp: 2 (A05, B11); 4 ảnh còn lại chưa có kết luận đối chiếu trực quan được ghi nhận
Số nhãn đã đối chiếu trực tiếp trên 2 ảnh (shape + tag): 11 (A05: 3 shape + 4 tag; B11: 0 shape + 4 tag). Chưa đủ dữ liệu để phân bổ số mục kiểm theo từng mã QC.

## Tổng hợp theo mã
| Mã | Loại lỗi | Số mục kiểm | Số lỗi | Mức |
| --- | --- | ---: | ---: | --- |
| QC1-01 tag camera | sai thuộc tính / bỏ sót | chưa thống kê | chưa xác nhận | nặng |
| QC1-02 đủ L1, R1 | bỏ sót | chưa thống kê | chưa xác nhận | nặng |
| QC1-03 position | sai thuộc tính / thừa | chưa thống kê | chưa xác nhận | nặng |
| QC1-04 tâm vạch, chiều, điểm dừng | sai phạm vi / bỏ sót | chưa thống kê | chưa xác nhận | chính |
| QC1-05 vạch đứt, che | sai phạm vi / sai thuộc tính | chưa thống kê | chưa xác nhận | chính |
| QC1-06 style, color, kind | sai thuộc tính | chưa thống kê | chưa xác nhận | chính |
| QC1-07 vùng lái | sai phạm vi / bỏ sót / thừa | chưa thống kê | chưa xác nhận | chính |
| QC1-08 đèn, màu | bỏ sót / sai phạm vi / sai thuộc tính | chưa thống kê | chưa xác nhận | nặng / chính |
| QC1-09 facing, type, group, biển phụ | sai thuộc tính | chưa thống kê | chưa xác nhận | chính |
| QC1-10 hình in, đủ biển | bỏ sót / sai phạm vi | chưa thống kê | chưa xác nhận | chính |
| QC1-11 fisheye | sai phạm vi / sai thuộc tính | chưa thống kê | chưa xác nhận | chính |
| QC1-12 file | lỗi file | chưa thống kê | chưa xác nhận | nhẹ / nặng |

## Danh sách lỗi
Chưa có lỗi QC1 nào được xác nhận. Các cảnh báo lint vẫn là mục cần đối chiếu, không tự động tính là lỗi.

## Ca mơ hồ
| Ảnh | Câu hỏi cho lead | Lời đáp (nếu có) |
| --- | --- | --- |
| A05 | Có thể miễn QC1-02 nếu L1/R1 thực sự không nhìn thấy; xác nhận ảnh này không có vạch làn cần gán? | |
| B11 | Ảnh fisheye_rear, nhóm extra: có vạch lane dọc nào thuộc phạm vi cần gán không? Xác nhận bỏ vạch ô đỗ theo QC1-03 và chốt việc XML không có shape? | |

## Quyết định
Lỗi nặng: chưa xác nhận
Lỗi chính: chưa xác nhận / chưa xác định nhãn đã kiểm = chưa tính được %
Lỗi nhẹ: chưa xác nhận
Ca chờ lead: 2
Quyết định (Release / Hold / Rework): Hold (tạm thời)
Lý do (theo luật của phiếu): Còn câu hỏi chưa có lời đáp có thể ảnh hưởng tới kết luận. Chưa xác nhận cảnh báo lint thành lỗi QC1; chưa đủ số liệu để tính tỷ lệ lỗi chính.

## Bổ sung đối chiếu ảnh gốc

- A05: Đã xem ảnh gốc, không thấy vạch sơn L1/R1. Đề xuất ngoại lệ QC1-02, chờ coach xác nhận.
- B11: Đã xem ảnh gốc, chỉ thấy vạch ô đỗ xe và vùng gạch chéo khu vực đỗ xe; không thấy vạch phân làn L1/R1. Không xem việc không có lane shape là lỗi thiếu lane.
