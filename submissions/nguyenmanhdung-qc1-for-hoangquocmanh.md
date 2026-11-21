# Phiếu QC 1 — Road v1.0

Lô được kiểm (học viên): Hoàng Quốc Mạnh    Người kiểm (học viên): Nguyễn Mạnh Dũng  
Ngày: 20/11/2026    Phiên bản guideline: Road v1.0  
File được kiểm: hoangquocmanh-front.zip (A09–A12), femanh.zip (B01–B02) | Revision: chưa xác nhận cho cả hai ZIP vì chưa có manifest đối chiếu  
Số ảnh kiểm: 6 (A09, A10, A11, A12, B01, B02)   Số nhãn đã kiểm (shape + tag): 81  

## Tổng hợp theo mã
| Mã | Loại lỗi | Số mục kiểm | Số lỗi | Mức |
| --- | --- | ---: | ---: | --- |
| QC1-01 tag camera | sai thuộc tính / bỏ sót | 6 | 2 | nặng |
| QC1-02 đủ L1, R1 | bỏ sót | 12 | 0 | nặng |
| QC1-03 position | sai thuộc tính / thừa | 12 | 0 | nặng |
| QC1-04 tâm vạch, chiều, điểm dừng | sai phạm vi / bỏ sót | 12 | 1 | chính |
| QC1-05 vạch đứt, che | sai phạm vi / sai thuộc tính | 12 | 0 | chính |
| QC1-06 style, color, kind | sai thuộc tính | 12 | 0 | chính |
| QC1-07 vùng lái | sai phạm vi / bỏ sót / thừa | 21 | 5 | chính |
| QC1-08 đèn, màu | bỏ sót / sai phạm vi / sai thuộc tính | 14 | 2 | nặng / chính |
| QC1-09 facing, type, group, biển phụ | sai thuộc tính | 24 | 0 | chính |
| QC1-10 hình in, đủ biển | bỏ sót / sai phạm vi | 10 | 0 | chính |
| QC1-11 fisheye | sai phạm vi / sai thuộc tính | 10 | 0 | chính |
| QC1-12 file | lỗi file | 2 | 0 | nhẹ / nặng |

**Cách đếm.** Số mục kiểm được đối chiếu từ hai ZIP gốc trên 6 ảnh đã rà. QC1-02 đếm 2 vị trí L1/R1 mỗi ảnh. QC1-03 đến QC1-06 đếm các nhãn `lane` trong mẫu. QC1-07 đếm `drivable`, `crosswalk` và `road_curb`. QC1-08 đếm đèn, QC1-09 đếm đèn và biển, QC1-10 đếm biển, QC1-11 đếm các shape trên B01–B02 và QC1-12 đếm ZIP. Một nhãn có thể được đối chiếu theo nhiều mã. `0` là chưa ghi nhận lỗi cho mã đó trong lần rà này.

## Danh sách lỗi (mỗi lỗi một dòng)
| # | Mã | Ảnh | Nhãn (label, id) | Mức | Mô tả ngắn |
| --- | --- | --- | --- | --- | --- |
| 1 | QC1-07 | A12 | road_curb, ID 181 | Chính | Gán thừa polyline ở đoạn không có mép lề đường. |
| 2 | QC1-08 | A12 | traffic_light | Chính | Bỏ sót hộp đèn giao thông (1/2). |
| 3 | QC1-08 | A12 | traffic_light | Chính | Bỏ sót hộp đèn giao thông (2/2). |
| 4 | QC1-07 | A11 | road_curb | Chính | Polyline vẽ lệch khỏi mép lề đường. |
| 5 | QC1-04 | A10 | lane (L2) | Chính | Bỏ sót một vạch trắng ở vị trí L2. |
| 6 | QC1-07 | A10 | road_curb | Chính | Bỏ sót một mép lề đường. |
| 7 | QC1-07 | A10 | drivable (area_type = alternative) | Chính | Bỏ sót vùng lái được ở làn cùng chiều bên cạnh. |
| 8 | QC1-07 | A09 | drivable (area_type) | Chính | Vùng direct bao cả làn cùng chiều bên cạnh. Tách thành hai polygon: direct cho làn xe đang đi, alternative cho làn bên cạnh. |
| 9 | QC1-01 | B01 | camera | Nặng | ZIP gốc ghi front; đúng là fisheye_front (hậu tố FV). |
| 10 | QC1-01 | B02 | camera | Nặng | ZIP gốc ghi fisheye_rear; đúng là fisheye_front (hậu tố FV). |

## Ca mơ hồ
| Ảnh | Câu hỏi cho lead | Lời đáp (nếu có) |
| --- | --- | --- |
| B02 (femanh.zip) | Thiếu polygon drivable. Bảng kế hoạch trong repo chỉ ghi traffic_light / traffic_sign cho B02. Coach xác nhận B02 có yêu cầu drivable không? | Chờ xác nhận; chưa tính lỗi. |

### Ghi nhận ngoài mẫu 6 ảnh

- B03: Không ghi nhận lỗi.

## Quyết định bản gốc
Lỗi nặng: 2 (tag camera B01/B02). Lỗi chính đã ghi: 8 / 81 nhãn = 9,88%. Lỗi nhẹ: chưa ghi nhận. Ca chờ lead: 1 (drivable B02).  
Quyết định (Release / Hold / Rework): **Rework**.  
Lý do (theo luật của phiếu): Có 2 lỗi nặng. Tỉ lệ lỗi chính là 8/81 (9,88%), vượt ngưỡng 5%.  

## Kiểm lại sau Rework

Người kiểm lại: Nguyễn Mạnh Dũng  
Kết quả: Tôi đã kiểm lại bản Hoàng Quốc Mạnh gửi sau khi sửa. Các mục kiểm lại đều đạt.  
Quyết định sau kiểm lại: **Release**.  
Revision bản sau sửa: Chưa xác nhận. Manifest đối chiếu ghi `revision: 1`. Chưa xác minh được hai ZIP đã kiểm lại có khớp mã SHA-256 trong manifest.  

Loại lỗi: bỏ sót = thiếu nhãn phải có; thừa = gán cái không phải đối tượng; sai phạm vi = hình lệch, sai chiều, dừng sai chỗ, tràn vùng. Ba loại này theo cách chia lỗi gán nhãn của ISO/IEC 5259-4 (mục 8.4.2); "sai thuộc tính" và "lỗi file" là khóa học thêm. Cách xếp mức: [thang mức lỗi](../docs/qc_severity_road_v1.0.md).
