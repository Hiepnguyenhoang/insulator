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

Phương pháp sử dụng cv2.warpperspective, với ý tưởng cơ bản là xác định obb của vật thể xong kéo các tọa độ đỉnh (đưa qua ma trận pt - perspective) về tọa độ của hình ảnh. Lưu ý kéo tọa độ nào về đỉnh nào thì ma trận pt cũng thay đổi theo. Ví dụ như trên hình đang kéo thứ tự obb 0,1,2,3 về [0,h], [0,0], [w,0], [w,h] thứ tự như vậy cũng là ma trận pt luôn 

<p align="center">
  <img src="https://raw.githubusercontent.com/Hiepnguyenhoang/insulator/main/obb_crop_img.png" alt="OBB Crop Example" width="600"/>
</p>

Nguồn tham khảo: [cv2.warpPerspective](https://theailearner.com/tag/cv2-warpperspective/)


 
