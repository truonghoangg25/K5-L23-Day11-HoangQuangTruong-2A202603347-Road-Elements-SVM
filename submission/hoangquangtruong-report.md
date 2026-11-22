# Báo cáo cá nhân — Ngày 11
Họ tên: Hoàng Quang Trường Mã học viên: 2A202603347  
Phiên bản CVAT (Help → About): 2.74.1  
Guideline: Road v1.0 Lần nộp (`revision` trong manifest): 1  
Thời điểm export (ngày giờ trên CVAT): [CẦN XÁC NHẬN] Số lần nộp lại sau Rework: [CẦN XÁC NHẬN]

## 1. Kiểm project
| Mục | Tiêu chuẩn theo guideline Road v1.0 | Kết quả đối chiếu |
| --- | --- | --- |
| 6 label, đúng kiểu | lane—polyline; road_curb—polyline; crosswalk—polygon; drivable—polygon; traffic_light—rectangle; traffic_sign—rectangle. | Đã kiểm tra XML của cả hai ZIP: không phát hiện shape sai kiểu. |
| Thuộc tính và giá trị | lane(position, style, color, kind); drivable(area_type); traffic_light(color, type, facing, edge_zone); traffic_sign(group, facing, edge_zone); road_curb và crosswalk không có thuộc tính. | Đã trích xuất thuộc tính từ XML. Ba lane L1 trong fisheye đều thuộc fisheye_front/rear, đúng quy tắc camera; 15 ảnh front có 85 lane shape và tất cả đang là L1; A05 không có lane shape trong XML. Cần rà soát vị trí từng vạch trên ảnh trước khi kết luận. |
| 4 tag ảnh | Có | Manifest ghi nhận đủ tag cho 16/16 ảnh front và 12/12 ảnh fisheye; B11 có đủ camera, timeofday, weather, source. |
Cách kết thúc polyline trên bản CVAT này: Nhấp đúp chuột tại điểm cuối để kết thúc đường.  
Cách đặt tag ảnh trên bản CVAT này: Mở phần Tags của ảnh, chọn tag và giá trị tương ứng rồi áp dụng cho ảnh.

## 2. Số lượng đã gán
| Task | Ảnh | lane | road_curb | crosswalk | drivable | traffic_light | traffic_sign |
| --- | ---: | ---: | ---: | ---: | ---: | ---: | ---: |
| front | 12 | 59 | 27 | 36 | 24 | 4 | 7 |
| front-extra (đã làm 4 / 4) | 4 | 26 | 7 | 3 | 4 | 15 | 14 |
| fisheye | 8 | 8 | 27 | 13 | 10 | 3 | 9 |
| fisheye-extra (đã làm 4 / 4) | 4 | 0 | 6 | 5 | 3 | 0 | 0 |

## 3. Kết quả QC và các điểm cần xác nhận

Kết quả lint trên 28 ảnh ghi nhận 69 cảnh báo: 17 cảnh báo QC1-02, 25 QC1-04, 14 QC1-05, 2 QC1-08, 1 QC1-10 và 10 QC1-11. Đây là cảnh báo do công cụ phát hiện, không tự động được tính là lỗi QC đã xác nhận. Cần đối chiếu ảnh gốc, annotation và guideline trước khi ghi nhận lỗi hoặc quyết định Rework.

| Mã QC | Cảnh báo lint | Ghi chú |
|---|---:|---|
| QC1-02 | 17 | Gợi ý thiếu lane L1/R1; cần xác minh vạch có nhìn thấy trên ảnh hay không |
| QC1-04 | 25 | Gợi ý hướng polyline; cần đối chiếu hướng vẽ theo guideline |
| QC1-05 | 14 | Gợi ý số lượng/vị trí L1; cần xác minh trên ảnh |
| QC1-08 | 2 | Gợi ý hộp traffic light nhỏ; chưa xác nhận là lỗi |
| QC1-10 | 1 | Gợi ý hộp traffic sign nhỏ; chưa xác nhận là lỗi |
| QC1-11 | 10 | Gợi ý hình học/thuộc tính fisheye; cần đối chiếu ảnh và annotation |
| **Tổng** | **69** | **Cảnh báo lint, không phải tổng lỗi đã xác nhận** |

Các trường hợp cần làm rõ trước khi chốt QC:

- **A05 / QC1-02:** lint báo thiếu L1/R1. Chỉ áp dụng ngoại lệ khi coach xác nhận trực tiếp rằng vạch lane không nhìn thấy được và ghi image ID cùng lý do vào form.
- **B11 / fisheye_rear:** XML có 0 shape và 4 image tags. Cần xác nhận phạm vi gán nhãn của ảnh này; không tự suy ra rằng ảnh được chấp nhận chỉ vì không có lane markings.
- Không dùng riêng số cảnh báo lint làm bằng chứng kết luận lỗi. Chỉ ghi lỗi khi đã đối chiếu trực tiếp ảnh, shape/tag và quy tắc QC tương ứng.

Theo thang severity, một lỗi Severe đã xác nhận dẫn đến Rework; lỗi Major chỉ vượt ngưỡng khi tỷ lệ lớn hơn 5% số label đã kiểm tra (shape + tag). Vì các cảnh báo trên chưa được xác nhận thành lỗi, hiện chưa đủ căn cứ để tính tỷ lệ Major hoặc kết luận Release/Rework. Trường hợp còn chờ coach xác nhận được giữ ở trạng thái Hold cho đến khi có kết luận.

## 4. Phiếu QC 1

Đây là bài cá nhân nên người học tự kiểm tra bài của mình; không có phiếu peer-QC nhận từ học viên khác để báo cáo. Kết quả tự kiểm và các trường hợp cần lead/coach xác nhận được ghi trong `submission/hoangquangtruong-qc1-self-review.md`. Quyết định hiện tại: **Hold tạm thời**, chưa chốt Release/Rework.

## 5. Kiểm file export
| File | Mở lại được? | Số shape ảnh 1 (job / file) | Số shape ảnh 2 (job / file) | Tag camera có trong XML? |
| --- | --- | --- | --- | --- |
| hoangquangtruong-front.zip | Có — ZIP đọc được, có annotations.xml | Job: chưa đối chiếu / XML A01: 15 | Job: chưa đối chiếu / XML A02: 12 | Có |
| hoangquangtruong-fisheye.zip | Có — ZIP đọc được, có annotations.xml | Job: chưa đối chiếu / XML B01: 12 | Job: chưa đối chiếu / XML B02: 5 | Có |

## 6. Bằng chứng kiểm tra

Bằng chứng hiện có gồm kết quả lint, manifest, XML trong hai file export và ghi chú đối chiếu ảnh A05/B11 trong phiếu self-review. Chưa có ảnh chụp màn hình CVAT được lưu trong bộ hồ sơ, nên không khai là đã nộp screenshot.

- XML: có thể đối chiếu tag camera, shape và polyline trực tiếp trong `annotations.xml` của từng ZIP.
- Kết quả lint: `submission/lint-review.txt`; các cảnh báo được xem là gợi ý cần xác minh, không tự động tính thành lỗi QC.
- Ghi chú kiểm tra trực quan: `submission/hoangquangtruong-qc1-self-review.md`.

## 7. Tự đánh giá

Kết quả lint có nhiều cảnh báo nhất ở QC1-02 (17 cảnh báo gợi ý thiếu L1/R1). Đây là điểm cần ưu tiên tự kiểm tra, nhưng không đồng nghĩa 17 lỗi đã được xác nhận. Khi kiểm bài, cần nhìn ảnh gốc để xác định vạch làn có thực sự nhìn thấy hay không; chỉ ghi lỗi thiếu lane khi có bằng chứng, và chỉ dùng ngoại lệ khi coach xác nhận theo guideline.

Nếu nhãn lane bị thiếu hoặc đặt sai, dữ liệu huấn luyện có thể khiến model bỏ sót vạch làn hoặc học sai vị trí biên làn, ảnh hưởng đến việc xác định vùng chạy và hỗ trợ giữ làn. Đây là tác động có thể xảy ra của loại lỗi này, không phải kết luận rằng một lỗi cụ thể đã được xác nhận và sửa trong bài này.

## 8. (Tùy chọn, buffer) Từ polyline đến đích row-anchor

Không thực hiện phần buffer tùy chọn trong lần nộp này.
