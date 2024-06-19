# CHƯƠNG TRÌNH QUẢN LÝ NHÂN VIÊN QUÁN KARAOKE 
 
 #### Họ Và Tên : DƯƠNG HOÀNG VŨ

#### Mã Số Sinh Viên : K215480106069

#### Lớp :  57KMT01

Mô tả bài toán quản lý: Hệ thống quản lý quán karaoke cần giúp quản lý thông tin của tất cả nhân viên, bao gồm thông tin cá nhân, lịch làm việc, tiền lương và các vấn đề liên quan đến quản lý công việc hàng ngày của nhân viên. Hệ thống cần đảm bảo tính chính xác, dễ truy xuất và bảo mật thông tin.

### Những chức năng xây dựng để quản lý quán karaoke:

1: Quản lý thông tin nhân viên:

Thêm, sửa, xóa thông tin nhân viên.

Xem danh sách nhân viên.

Tìm kiếm nhân viên theo các tiêu chí (tên, mã nhân viên, chức vụ, ...).


2: Quản lý ca làm việc:

Tạo và phân bổ ca làm việc cho nhân viên.
Xem lịch làm việc của nhân viên.
Điều chỉnh ca làm việc (đổi ca, hủy ca, ...).

3:Quản lý tiền lương:

Tính lương dựa trên giờ làm việc.

Lưu trữ thông tin về lương, thưởng, phạt.

Xuất báo cáo lương hàng tháng.


4: Quản lý chấm công:

Chấm công hàng ngày.

Theo dõi ngày nghỉ, ngày làm thêm giờ của nhân viên.

Xuất báo cáo chấm công.


5:Quản lý phòng hát:

Thêm, sửa, xóa thông tin phòng hát.

Xem danh sách phòng hát.

Quản lý tình trạng phòng (trống, đang sử dụng, bảo trì).

6:Quản lý đặt phòng:

Đặt phòng hát cho khách hàng.

Xác nhận và hủy đặt phòng.

 Quản lý lịch đặt phòng.

#### Tạo cơ sở dữ liệu quản lý hàng gồm các bảng :

NhanVien(🔑ID,MaNV,HoTen, NgaySinh, GioiTinh,DiaChi,SoDenThoai,ChucVu)

ChamCong(🔑ID,MaCC,MaNV,NgayChamCong, GioVao,GioRa )

Luong(🔑ID,MaLuong, MaNV,LuongCoBan,Thuong,Phat,TongLuong)

Phong(🔑ID, MaPhong, TenPhong, LoaiPhong,GiaPhong )

CaLamViec(🔑ID, MaCa,TenCa,ThoiGianBatDau,ThoiGianKetThuc)

DatPhong(🔑ID, MaDatPhong,MaPhong, MaNV, NgayDat,GioBatDau ,GioKetThuc )

#Dựa trên cơ sở sở dữ liệu trên ta tiến hành tạo các bảng như sau:

Bảng NhanVien (Phải tạo đầu tiên để các bảng khác tham chiếu tới)

MaNV: Khóa chính (Primary Key) tự tăng, định danh duy nhất cho mỗi nhân viên.
- HoTen: Tên đầy đủ của nhân viên.

- NgaySinh: Ngày sinh của nhân viên.

- GioiTinh: Giới tính của nhân viên.

- DiaChi: Địa chỉ cư trú của nhân viên.
  
- SoDienThoai: Số điện thoại liên lạc của nhân viên.

- ChucVu: Chức vụ hoặc vai trò của nhân viên trong quán karaoke.








