# Báo cáo cá nhân — Ngày 11
Họ tên: Hoàng Quang Trường               Mã học viên: 2A202603347  
Phiên bản CVAT (Help → About): 2.74.1  
Guideline: Road v1.0    Lần nộp (`revision` trong manifest): 1  
Thời điểm export (ngày giờ trên CVAT): Chưa xác nhận    Số lần nộp lại sau Rework: Chưa xác nhận  

## 1. Kiểm project
| Mục | Đúng như guideline Road v1.0? | Ghi chú |
| --- | --- | --- |
| 6 label, đúng kiểu | Đã kiểm tra cấu trúc export | Không ghi nhận lỗi file đã xác nhận |
| Thuộc tính và giá trị | Chưa xác nhận đầy đủ | Chưa hoàn tất kiểm tra trực quan toàn bộ ảnh |
| 4 tag ảnh | Có tag trong export | Front: 16/16 ảnh có tag; fisheye: 12/12 ảnh có tag |

Cách kết thúc polyline trên bản CVAT này: Chưa ghi nhận.  
Cách đặt tag ảnh trên bản CVAT này: Chưa ghi nhận.  

## 2. Số lượng đã gán
| Task | Ảnh | lane | road_curb | crosswalk | drivable | traffic_light | traffic_sign |
| --- | ---: | ---: | ---: | ---: | ---: | ---: | ---: |
| front | 12 | 59 | 27 | 36 | 24 | 4 | 7 |
| front-extra (đã làm 4 / 4) | 4 | 26 | 7 | 3 | 4 | 15 | 14 |
| fisheye | 8 | 8 | 27 | 13 | 10 | 3 | 9 |
| fisheye-extra (đã làm 4 / 4) | 4 | 0 | 6 | 5 | 3 | 0 | 0 |

## 3. Bảng ca khó
| Ảnh | Nhãn | Phân vân giữa | Đã chọn | Lý do |
| --- | --- | --- | --- | --- |
| A05 | lane / L1, R1 | Có cần nhãn khi không thấy vạch L1/R1? | Chưa chốt | Cần lead xác nhận trường hợp miễn nhãn |
| B11 | lane | Vạch đỗ xe/vùng gạch chéo có thuộc phạm vi lane không? | Chưa chốt | Cần lead xác nhận phạm vi trên ảnh fisheye |

## 4. Phiếu QC 1 nhận được
Bạn kiểm lô của tôi: Chưa nhận phiếu QC từ bạn học    Quyết định nhận được: Chưa có  
| Mã lỗi | Số lỗi | Đồng ý? | Đã sửa? |
| --- | ---: | --- | --- |
| Chưa có phiếu QC peer | — | — | — |

## 5. Kiểm file export
| File | Mở lại được? | Số shape ảnh 1 (job / file) | Số shape ảnh 2 (job / file) | Tag camera có trong XML? |
| --- | --- | --- | --- | --- |
| hoangquangtruong-front.zip | Có; export có 16 ảnh | Chưa đối chiếu | Chưa đối chiếu | Có tag trong export; chưa đối chiếu riêng XML |
| hoangquangtruong-fisheye.zip | Có; export có 12 ảnh | Chưa đối chiếu | Chưa đối chiếu | Có tag trong export; chưa đối chiếu riêng XML |

## 6. Ảnh chụp màn hình
1. Tab Labels của project: Chưa đính kèm.
2. Một ảnh camera trước đã gán đủ (làn, vùng lái, đèn/biển): Chưa đính kèm.
3. Một ảnh fisheye đã gán, phóng to đoạn polyline cong: Chưa đính kèm.
4. Một đoạn XML có `<polyline label="lane">`: Chưa đính kèm.

## 7. Tự đánh giá
Lỗi bạn mắc nhiều nhất hôm nay (theo mã QC1-xx), và cách tránh ở Ngày 20: Chưa xác định được mã lỗi mắc nhiều nhất vì chưa có lỗi nào được xác nhận qua kiểm trực quan. Ở Ngày 20, đối chiếu guideline theo từng ảnh trước khi kết thúc nhãn và ghi lại các ca cần hỏi lead.  
Nhãn của bạn đi vào model ở đâu? Chọn một lỗi đã sửa và nói nó làm model học sai thế nào: Chưa có lỗi đã sửa được xác nhận để làm ví dụ; không tự tạo ví dụ như lỗi thực tế của bài.

## 8. (Tùy chọn, buffer) Từ polyline đến đích row-anchor
| y | 720 | 680 | 640 | 600 | 560 |
| --- | ---: | ---: | ---: | ---: | ---: |
| x của chúng tôi | Chưa đo | Chưa đo | Chưa đo | Chưa đo | Chưa đo |
| x của bạn kia | Chưa có dữ liệu | Chưa có dữ liệu | Chưa có dữ liệu | Chưa có dữ liệu | Chưa có dữ liệu |

Trả lời 3 câu:
1. Năm số x đó chính là đích mà một model row-anchor học cho vạch này. Nếu bạn dừng polyline sớm 40 px, hàng nào đổi thành "không có làn"? Chưa xác định; cần tọa độ polyline và ảnh cụ thể.
2. So với bạn được kiểm (cùng ảnh): ở hàng 720 và hàng 560, hai bạn lệch nhau bao nhiêu pixel? Lệch ở hàng nào ảnh hưởng LKA nhiều hơn (slide 25)? Chưa có dữ liệu tọa độ của hai bên để tính độ lệch.
3. Nếu polyline vẽ từ xa về gần (ngược quy tắc 2), cách tính trên có đổi không? Script nào sẽ gặp khó? Chưa xác định theo script của bài; cần đối chiếu quy tắc 2 và script được cung cấp.
