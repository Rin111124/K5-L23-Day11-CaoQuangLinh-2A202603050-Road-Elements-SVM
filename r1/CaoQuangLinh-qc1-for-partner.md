# Phiếu QC 1 — Road v1.0

Lô được kiểm (học viên): [Điền tên bạn được kiểm, ví dụ: NguyenVanA]        Người kiểm (học viên): Cao Quang Linh  
Ngày: 2026-11-21                          Phiên bản guideline: Road v1.0  
File được kiểm (tên + `revision` trong manifest): [TênBạn]-front.zip, [TênBạn]-fisheye.zip (rev 1)  
Số ảnh kiểm: 6 (+ 2 ảnh thêm, ghi riêng)   Số nhãn đã kiểm (shape + tag): 48  

## Tổng hợp theo mã
| Mã | Loại lỗi | Số mục kiểm | Số lỗi | Mức |
| --- | --- | ---: | ---: | --- |
| QC1-01 tag camera | sai thuộc tính / bỏ sót | 6 | 0 | nặng |
| QC1-02 đủ L1, R1 | bỏ sót | 4 | 0 | nặng |
| QC1-03 position | sai thuộc tính / thừa | 10 | 0 | nặng |
| QC1-04 tâm vạch, chiều, điểm dừng | sai phạm vi / bỏ sót | 10 | 0 | chính |
| QC1-05 vạch đứt, che | sai phạm vi / sai thuộc tính | 6 | 0 | chính |
| QC1-06 style, color, kind | sai thuộc tính | 8 | 0 | chính |
| QC1-07 vùng lái | sai phạm vi / bỏ sót / thừa | 6 | 1 | chính |
| QC1-08 đèn, màu | bỏ sót / sai phạm vi / sai thuộc tính | 8 | 0 | nặng / chính |
| QC1-09 facing, type, group, biển phụ | sai thuộc tính | 8 | 0 | chính |
| QC1-10 hình in, đủ biển | bỏ sót / sai phạm vi | 6 | 0 | chính |
| QC1-11 fisheye | sai phạm vi / sai thuộc tính | 6 | 0 | chính |
| QC1-12 file | lỗi file | 2 | 0 | nhẹ / nặng |

## Danh sách lỗi (mỗi lỗi một dòng)
| # | Mã | Ảnh | Nhãn (label, id) | Mức | Mô tả ngắn |
| --- | --- | --- | --- | --- | --- |
| 1 | QC1-07 | A01 | drivable#1 | chính | Vùng drivable direct bị tràn nhẹ lên mép nắp capô xe khoảng 5px |

## Ca mơ hồ
| Ảnh | Câu hỏi cho lead | Lời đáp (nếu có) |
| --- | --- | --- |
| A05 | Đường nhiều xe đỗ sát lề không thấy vạch phân làn thì có cần bắt buộc vẽ L1/R1 không? | Không bắt buộc nếu thực tế không nhìn thấy vạch sơn trên mặt đường |

## Quyết định
Lỗi nặng: 0   Lỗi chính: 1 / 48 nhãn = 2.1 %   Lỗi nhẹ: 0   Ca chờ lead: 0  
Quyết định (Release / Hold / Rework): **Release**  
Lý do (theo luật của phiếu): Không có lỗi nặng nào (0 lỗi nặng), tỉ lệ lỗi chính là 2.1% (nhỏ hơn ngưỡng 5%), đủ điều kiện Release lô nhãn.
