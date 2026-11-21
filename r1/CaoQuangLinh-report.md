# Báo cáo cá nhân — Ngày 11
Họ tên: Cao Quang Linh               Mã học viên: 2A202603050  
Phiên bản CVAT (Help → About): v2.82.0  
Guideline: Road v1.0    Lần nộp (`revision` trong manifest): 1  
Thời điểm export (ngày giờ trên CVAT): 2026-11-21 01:27 UTC    Số lần nộp lại sau Rework: 0  

## 1. Kiểm project
| Mục | Đúng như guideline Road v1.0? | Ghi chú |
| --- | --- | --- |
| 6 label, đúng kiểu | Đúng | lane (polyline), road_curb (polyline), crosswalk (polygon), drivable (polygon), traffic_light (box), traffic_sign (box) |
| Thuộc tính và giá trị | Đúng | Khớp hoàn toàn với configs/road_v1_labels.json |
| 4 tag ảnh | Đúng | camera, timeofday, weather, source đều có thuộc tính select value |
Cách kết thúc polyline trên bản CVAT này: Nhấn phím N (hoặc click chuột phải / đúp chuột vào điểm cuối).  
Cách đặt tag ảnh trên bản CVAT này: Chọn công cụ Tag ở thanh bên trái, chọn label tag, sau đó mở bảng Details bên phải để kiểm tra và chọn giá trị cho thuộc tính `value`.  

## 2. Số lượng đã gán
| Task | Ảnh | lane | road_curb | crosswalk | drivable | traffic_light | traffic_sign |
| --- | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: |
| front | 12 | 30 | 12 | 8 | 28 | 24 | 24 |
| front-extra (đã làm 4 / 4) | 4 | 11 | 4 | 2 | 8 | 13 | 12 |
| fisheye | 8 | 7 | 11 | 9 | 7 | 3 | 5 |
| fisheye-extra (đã làm 4 / 4) | 4 | 0 | 3 | 4 | 2 | 0 | 0 |

## 3. Bảng ca khó
| Ảnh | Nhãn | Phân vân giữa | Đã chọn | Lý do |
| --- | --- | --- | --- | --- |
| A05 | lane | Vẽ ước lượng L1/R1 hay bỏ qua | Bỏ qua vạch L1/R1 | Mặt đường nhiều xe đỗ sát lề, không nhìn thấy vệt sơn phân làn rõ ràng; chỉ gán road_curb ở mép lề theo đúng hướng dẫn |
| A04 | lane | Vẽ 2 polyline riêng hay 1 polyline kind=double | kind=double | Vạch vàng đôi tim đường phân cách hai chiều xe chạy, gán 1 nét kind=double theo guideline |
| B11 | lane | Gán vạch ô đỗ xe hay bỏ qua | Bỏ qua vạch ô đỗ xe | Guideline mục 4 nêu rõ: vạch ô đỗ xe không gán lane, chỉ gán các vạch phân luồng dọc đường |
| B08 | lane | position = L1 hay position = other | position = other | Camera hai bên sườn (fisheye_right / MVR) bắt buộc dùng position = other theo quy tắc QC1-03 |

## 4. Phiếu QC 1 nhận được
Bạn kiểm lô của tôi: [Tên bạn ghép cặp]    Quyết định nhận được: Release  
| Mã lỗi | Số lỗi | Đồng ý? | Đã sửa? |
| --- | ---: | --- | --- |
| QC1-02 (A05 thiếu L1/R1) | 2 | Đồng ý | Không sửa (ảnh thực tế không thấy vạch sơn, được miễn theo quy định) |
| QC1-11 (B03/B04 edge_zone) | 2 | Đồng ý | Đã bật checkbox edge_zone do tâm box nằm ngoài 80% bán kính |

## 5. Kiểm file export
| File | Mở lại được? | Số shape ảnh 1 (job / file) | Số shape ảnh 2 (job / file) | Tag camera có trong XML? |
| --- | --- | --- | --- | --- |
| CaoQuangLinh-front.zip | Có | 9 | 7 | Có (`front`) |
| CaoQuangLinh-fisheye.zip | Có | 4 | 6 | Có (`fisheye_front`) |

## 6. Ảnh chụp màn hình
1. Tab Labels của project: [Đính kèm ảnh chụp màn hình tab Labels đủ 6 shape và 4 tag]
2. Một ảnh camera trước đã gán đủ (làn, vùng lái, đèn/biển): [Đính kèm ảnh chụp A01 hoặc A12]
3. Một ảnh fisheye đã gán, phóng to đoạn polyline cong: [Đính kèm ảnh chụp B01 hoặc B08 uốn cong]
4. Một đoạn XML có `<polyline label="lane">`: [Đính kèm ảnh chụp màn hình mở annotations.xml]

## 7. Tự đánh giá
Lỗi bạn mắc nhiều nhất hôm nay (theo mã QC1-xx), và cách tránh ở Ngày 20:  
- Lỗi hay gặp: Thuộc tính mặc định của CVAT tự điền `L1 / solid / white / single` cho lane và `clear` cho weather. Khi vẽ nhiều vạch, nếu quên chỉnh Details thì các vạch ngoài cũng bị gán L1.
- Cách tránh: Thiết lập thói quen ngay sau khi bấm N kết thúc polyline là mở bảng Details bên phải để rà soát thuộc tính `position`, `color`, `style` trước khi chuyển sang vẽ đối tượng tiếp theo.

Nhãn của bạn đi vào model ở đâu? Chọn một lỗi đã sửa và nói nó làm model học sai thế nào:  
- Nhãn đi vào mô hình phát hiện làn đường (Lane Detection / Row-Anchor Model) và phân vùng lái xe an toàn (Drivable Area Segmentation) trong hệ thống xe tự hành.
- Nếu gán nhầm thuộc tính `position` (ví dụ vạch tim đường L2 lại gán thành L1, hoặc nhầm L1 với R1), mô hình học sâu sẽ nhận diện sai làn xe đang di chuyển, dẫn đến hệ thống Giữ làn tự động (Lane Keeping Assist - LKA) tính toán sai độ lệch tâm của xe và có thể đánh lái sai, gây nguy hiểm khi vận hành xe thực tế.
