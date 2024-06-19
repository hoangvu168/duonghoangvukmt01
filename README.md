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

#### Các khóa trong bài toán:

#### 1 Tạo cơ sở dữ liệu quản lý hàng gồm các bảng :

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


![image](https://github.com/hoangvu168/duonghoangvukmt01/assets/169289491/9a7bf524-52ee-4335-ae8e-a2623b6c7173)


Bảng ChamCong:

Bảng này ghi nhận thông tin chấm công của từng nhân viên.
 
- MaCC: Khóa chính tự tăng cho bảng chấm công.

- MaNV: Khóa ngoại tham chiếu đến MaNV trong bảng NhanVien, xác định nhân viên được chấm công.
- 
- NgayChamCong: Ngày nhân viên được chấm công.

- GioVao, GioRa: Thời điểm vào và ra làm việc của nhân viên trong ngày.


![image](https://github.com/hoangvu168/duonghoangvukmt01/assets/169289491/a7d8b0e7-8a00-4706-a9fb-52e9fbef5ed0)


Bảng Luong:

Bảng này lưu trữ thông tin về lương của nhân viên

- MaLuong: Khóa chính tự tăng cho bảng lương.

- MaNV: Khóa ngoại tham chiếu đến MaNV trong bảng NhanVien, xác định nhân viên có liên quan đến bản ghi lương.

- LuongCoBan: Số tiền lương cơ bản của nhân viên.

- Thuong: Các khoản thưởng (nếu có) được áp dụng cho nhân viên.

- Phat: các khoản phạt (nếu có) được áp dụng cho nhân viên.
  
- TongLuong : Trường tính toán (PERSISTED) cho tổng số tiền lương thực nhận của nhân viên sau khi tính thưởng và phạt.

![image](https://github.com/hoangvu168/duonghoangvukmt01/assets/169289491/a48ea565-b5b4-4e9d-81c1-18171831a916)



Bảng Phong: 

Bảng này mô tả các phòng hát trong quán karaoke.

- MaPhong: Khóa chính tự tăng cho bảng phòng.

- TenPhong: Tên đặc điểm của phòng hát.
 
- LoaiPhong: Loại phòng hát (VIP, thường, ...).

- GiaPhong: Giá thuê của phòng hát cho mỗi giờ hoặc mỗi lượt sử dụng.

![image](https://github.com/hoangvu168/duonghoangvukmt01/assets/169289491/8c5db634-8113-4e02-bca3-14144b339616)



Bảng CaLamViec:

 Bảng này lưu trữ thông tin về các ca làm việc trong quán karaoke.

- MaCa: Khóa chính tự tăng cho bảng ca làm việc.

- TenCa: Tên của ca làm việc.
 
- ThoiGianBatDau, ThoiGianKetThuc: Thời gian bắt đầu và kết thúc của ca làm việc.

![image](https://github.com/hoangvu168/duonghoangvukmt01/assets/169289491/1ffbf40a-bbc4-4d70-9568-a3366856fd4d)

Bảng DatPhong:

Bảng này lưu trữ thông tin đặt phòng hát của khách hàng.

- MaDatPhong: Khóa chính tự tăng cho bảng đặt phòng.

- MaPhong: Khóa ngoại tham chiếu đến MaPhong trong bảng Phong, xác định phòng hát được đặt.

- MaNV: Khóa ngoại tham chiếu đến MaNV trong bảng NhanVien, xác định nhân viên phụ trách đặt phòng.
 
 - NgayDat: Ngày đặt phòng hát.

- GioBatDau, GioKetThuc: Thời gian bắt đầu và kết thúc sử dụng phòng hát.

![image](https://github.com/hoangvu168/duonghoangvukmt01/assets/169289491/bb14835f-56fa-4746-9506-aa6f25c101dc)

 
 ### Sơ đồ thực thể liên kết

 ![image](https://github.com/hoangvu168/duonghoangvukmt01/assets/169289491/da204f1c-0889-4d81-9954-15d49ff6b845)


 ### 2.Thêm dữ liệu vào các bảng

-- Thêm dữ liệu vào bảng NhanVien

INSERT INTO NhanVien (HoTen, NgaySinh, GioiTinh, DiaChi, SoDienThoai, ChucVu)
VALUES 

('Nguyen Van A', '1990-01-01', 'Nam', '123 Le Loi, HCM', '0901234567', 'Le tan'),

('Tran Thi B', '1992-02-02', 'Nu', '456 Tran Hung Dao, HCM', '0902345678', 'Phuc vu');

-- Thêm dữ liệu vào bảng ChamCong

INSERT INTO ChamCong (MaNV, NgayChamCong, GioVao, GioRa)
VALUES 

(1, '2024-06-01', '09:00:00', '17:00:00'),

(2, '2024-06-01', '10:00:00', '18:00:00');

-- Thêm dữ liệu vào bảng Luong

INSERT INTO Luong (MaNV, LuongCoBan, Thuong, Phat)
VALUES 

(1, 5000000, 500000, 100000),

(2, 6000000, 600000, 200000);

-- Thêm dữ liệu vào bảng Phong

INSERT INTO Phong (TenPhong, LoaiPhong, GiaPhong)
VALUES 

('Phong 1', 'VIP', 300000),

('Phong 2', 'Thuong', 150000);

-- Thêm dữ liệu vào bảng CaLamViec

INSERT INTO CaLamViec (TenCa, ThoiGianBatDau, ThoiGianKetThuc)
VALUES 
('Ca Sang', '08:00:00', '12:00:00'),

('Ca Chieu', '13:00:00', '17:00:00');

-- Thêm dữ liệu vào bảng DatPhong

INSERT INTO DatPhong (MaPhong, MaNV, NgayDat, GioBatDau, GioKetThuc)
VALUES 
(1, 1, '2024-06-01', '09:00:00', '11:00:00'),

(2, 2, '2024-06-01', '14:00:00', '16:00:00');

## Thiết lập chức năng

## 1.Chức năng cơ bản

INSERT INTO NhanVien

(HoTen, NgaySinh, GioiTinh, DiaChi, SoDienThoai, ChucVu)
VALUES 
('Nguyen Van A', '1990-01-01', 'Nam', '123 Le Loi, HCM', '0901234567', 'Le tan'),

('Tran Thi B', '1992-02-02', 'Nu', '456 Tran Hung Dao, HCM', '0902345678', 'Phuc vu');

*Chấm công cho nhân viên vào ngày cụ thể:

INSERT INTO ChamCong (MaNV, NgayChamCong, GioVao, GioRa)
VALUES 

(1, '2024-06-01', '09:00:00', '17:00:00'),

(2, '2024-06-01', '10:00:00', '18:00:00');

*Cập nhật thông tin nhân viên
UPDATE NhanVien

SET DiaChi = '789 Nguyen Trai, HCM'

WHERE MaNV = 1;

*Xóa thông tin nhân viên (cùng với các thông tin liên quan trong các bảng khác như chấm công, lương, đặt phòng):

DELETE FROM NhanVien WHERE MaNV = 2;

*Đặt phòng hát cho khách hàng vào ngày và giờ cụ thể:

INSERT INTO DatPhong (MaPhong, MaNV, NgayDat, GioBatDau, GioKetThuc)
VALUES 

(1, 1, '2024-06-01', '09:00:00', '11:00:00'),

(2, 2, '2024-06-01', '14:00:00', '16:00:00');

*Truy vấn thông tin nhân viên

SELECT * FROM NhanVien;

*Truy vấn thông tin chấm công của một nhân viên cụ thể

SELECT * FROM ChamCong WHERE MaNV = 1;

 Tính tổng lương của tất cả nhân viên

SELECT MaNV, TongLuong FROM Luong;

*Cập nhật thông tin nhân viên

UPDATE NhanVien

SET DiaChi = '789 Nguyen Trai, HCM'

WHERE MaNV = 1;

*Truy vấn thông tin đặt phòng hát của khách hàng:

SELECT * FROM DatPhong;


* Thêm dữ liệu vào các bảng (INSERT INTO):
* 
  ![image](https://github.com/hoangvu168/duonghoangvukmt01/assets/169289491/16fb061d-943c-41b3-a0ae-227b69c20f3b)

* Truy vấn dữ liệu từ các bảng (SELECT):
* 
![image](https://github.com/hoangvu168/duonghoangvukmt01/assets/169289491/392278de-d3db-49ba-bd8c-adf3f8d43253)

* Cập nhật thông tin (UPDATE) và Xóa dữ liệu (DELETE):
  
![image](https://github.com/hoangvu168/duonghoangvukmt01/assets/169289491/136158c3-05a5-418e-820d-80cd987a65ad)

*Bảng NhanVien

### Các khóa PK, FK, CK trong bài toán

- Bảng NhanVien

![image](https://github.com/hoangvu168/duonghoangvukmt01/assets/169289491/68fe287d-9f75-4df0-9674-ff82166d1c88)

PK: MaNV (Primary Key) - Đây là khóa chính của bảng NhanVien.

CK: Không có ràng buộc điều kiện nào được định nghĩa ở đây.


- Bảng ChamCong

![image](https://github.com/hoangvu168/duonghoangvukmt01/assets/169289491/5e8a712d-d5c6-4a60-8902-f9975829485a)

PK: MaCC (Primary Key) - Đây là khóa chính của bảng ChamCong.

FK: MaNV (Foreign Key) - Tham chiếu đến MaNV trong bảng NhanVien. Nếu nhân viên bị xóa (DELETE) từ bảng NhanVien, các bản ghi tương ứng trong bảng ChamCong cũng sẽ bị xóa (ON DELETE CASCADE).


- Bảng Luong

![image](https://github.com/hoangvu168/duonghoangvukmt01/assets/169289491/708b4bc2-983a-46b4-a384-8f8559b8f2bc)

PK: MaLuong (Primary Key) - Đây là khóa chính của bảng Luong.

FK: MaNV (Foreign Key) - Tham chiếu đến MaNV trong bảng NhanVien. Nếu nhân viên bị xóa từ bảng NhanVien, các bản ghi tương ứng trong bảng Luong cũng sẽ bị xóa (ON DELETE CASCADE).

Bảng Phong

![image](https://github.com/hoangvu168/duonghoangvukmt01/assets/169289491/9a3b77ea-247e-4646-8b4f-6bf3d5a419a2)   

PK: MaPhong (Primary Key) - Đây là khóa chính của bảng Phong.

CK: Không có ràng buộc điều kiện nào được định nghĩa ở đây.

Bảng CaLamViec

 ![image](https://github.com/hoangvu168/duonghoangvukmt01/assets/169289491/d7540929-a30d-4a5a-a2b2-34c42aed2095)   
 
PK: MaCa (Primary Key) - Đây là khóa chính của bảng CaLamViec.

CK: Không có ràng buộc điều kiện nào được định nghĩa ở đây.

Bảng DatPhong

![image](https://github.com/hoangvu168/duonghoangvukmt01/assets/169289491/73f1d7f1-5535-4f84-8bfd-e16967dd4040)

PK: MaDatPhong (Primary Key) - Đây là khóa chính của bảng DatPhong.

FK: MaPhong (Foreign Key) - Tham chiếu đến MaPhong trong bảng Phong.
MaNV (Foreign Key) - Tham chiếu đến MaNV trong bảng NhanVien. Nếu nhân viên bị xóa từ bảng NhanVien, các bản ghi tương ứng trong bảng DatPhong cũng sẽ bị xóa (ON DELETE CASCADE).

### -- Tạo VIEW mới để hiển thị thông tin

 ![image](https://github.com/hoangvu168/duonghoangvukmt01/assets/169289491/b1a74937-6de7-43a0-b297-efc9e166611c)



 ### Kết quả 

![image](https://github.com/hoangvu168/duonghoangvukmt01/assets/169289491/74c3ce3c-932a-4d66-a27d-82991a508af5)
 
