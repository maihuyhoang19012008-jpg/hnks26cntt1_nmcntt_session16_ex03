


# Vấn đề
>Khung "Nội dung bài học " đè lên "Video bài học " 
>Khi soi bằng F12, các thông số kích thước trông rất lộn xộn, không biết khoảng cách nào là do viền (border) hay do lề (margin).
  
# Yêu cầu 
 Tab Computed trong DevTools để phân tích 4 lớp của Box Model (Content, Padding, Border, Margin)
 
# Cách làm 
## Phần 1: Báo cáo phân tích (I/O)
- 
-  Phác thảo sơ đồ Box Model hiện tại của phần tử bị lỗi qua việc soi thực tế.
 **Sơ đồ Box Model**  
Content 
Padding 
Border
Margin 


## Phần 2: Thiết kế giải pháp
-  Nguyên nhân gốc rễ lỗi
Không tạo khoảng đệm bên trong lỗi  sát viền**Border**0 hoặc 1px (màu trong suốt)
 Không thấy được, dễ nhầm lẫn với margin**Margin**margin-right: -10px / 0 / quá lớn
  Đẩy/tràn sang khung bên cạnh dẫn đến  chồng lấn
1 không tính vào phần trăm  thực tế rộng hơn 65%
2.   Đẩy khung chồng lấn vào nhau thay vì tạo khoảng cách
3. Nội dung dài không tự cắt  tràn ra ngoài
4.  Thiếu `box-sizing: border-box`: Viền/padding không được tính vào `width` khai báo  thực tế rộng hơn dự kiến
