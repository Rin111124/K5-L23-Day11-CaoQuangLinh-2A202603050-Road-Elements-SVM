# Phiếu QC 1 — Road v1.0

Lô được kiểm (học viên): Đặng Minh Quân        Người kiểm (học viên): Cao Quang Linh  
Ngày: 2026-11-21                          Phiên bản guideline: Road v1.0  
File được kiểm (tên + `revision` trong manifest): DangMinhQuan-front.zip, DangMinhQuan-fisheye.zip (revision 1)  
Số ảnh kiểm: 6 (+ 2 ảnh thêm, ghi riêng)   Số nhãn đã kiểm (shape + tag): 48  

## Tổng hợp theo mã
| Mã | Loại lỗi | Số mục kiểm | Số lỗi | Mức |
| --- | --- | ---: | ---: | --- |
| QC1-01 tag camera | sai thuộc tính / bỏ sót | 8 | 0 | nặng |
| QC1-02 đủ L1, R1 | bỏ sót | 6 | 0 | nặng |
| QC1-03 position | sai thuộc tính / thừa | 12 | 0 | nặng |
| QC1-04 tâm vạch, chiều, điểm dừng | sai phạm vi / bỏ sót | 12 | 1 | chính |
| QC1-05 vạch đứt, che | sai phạm vi / sai thuộc tính | 6 | 0 | chính |
| QC1-06 style, color, kind | sai thuộc tính | 12 | 0 | chính |
| QC1-07 vùng lái | sai phạm vi / bỏ sót / thừa | 10 | 0 | chính |
| QC1-08 đèn, màu | bỏ sót / sai phạm vi / sai thuộc tính | 8 | 0 | nặng / chính |
| QC1-09 facing, type, group, biển phụ | sai thuộc tính | 8 | 0 | chính |
| QC1-10 hình in, đủ biển | bỏ sót / sai phạm vi | 8 | 0 | chính |
| QC1-11 fisheye | sai phạm vi / sai thuộc tính | 6 | 0 | chính |
| QC1-12 file | lỗi file | 2 | 0 | nhẹ / nặng |

## Danh sách lỗi (mỗi lỗi một dòng)
| # | Mã | Ảnh | Nhãn (label, id) | Mức | Mô tả ngắn |
| --- | --- | --- | --- | --- | --- |
| 1 | QC1-04 | A02 | lane (id: 3) | chính | Polyline dừng hơi sớm so với điểm khuất tầm nhìn của vạch R1 |

## Ca mơ hồ
| Ảnh | Câu hỏi cho lead | Lời đáp (nếu có) |
| --- | --- | --- |
| A05 | Đoạn vạch mờ dưới bóng cây bên phải có cần vẽ tiếp R1 không? | Chỉ vẽ đến điểm còn nhìn rõ trên mặt đường |

## Quyết định
Lỗi nặng: 0   Lỗi chính: 1 / 48 nhãn = 2.1 %   Lỗi nhẹ: 0   Ca chờ lead: 0  
Quyết định (Release / Hold / Rework): Release  
Lý do (theo luật của phiếu): Không có lỗi nặng; tỉ lệ lỗi chính đạt 2.1% (thấp hơn ngưỡng tối đa 5%); các shape và tag được gắn đầy đủ và chính xác theo guideline Road v1.0.
