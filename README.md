# insulator

Gen thêm dữ liệu về lỗi trên thiết bị: dữ liệu từ khách hàng ít, mô hình thứ 2 xác định lỗi đạt hiệu quả không ổn lắm

Cấu tạo ý tưởng thao tác một label segment: thường bao gồm
- class_id: poly[0] object id
- coords: chứa toàn bộ thông tin về các điểm polygon cấu tạo nên mask object
  - points: tọa độ [x,y] của từng điểm
  - poly: một nhóm các điểm  

## Crop thiết bị bbox dựa vào mask segment

## Crop ảnh obb
Một hình ảnh nếu như crop bbox theo class_id thì nếu như object có hình dạng cong, chéo khiến cho kích thước hình ảnh từ đó mà to lên, vì vậy hình ảnh có thể sẽ bao gồm lỗi + thiết bị khác. Nên sử dụng obb giảm thiểu hiện tượng này

<p align="center">
  <img src="https://raw.githubusercontent.com/Hiepnguyenhoang/insulator/main/obb_crop_img.png" alt="OBB Crop Example" width="400"/>
</p>



 
