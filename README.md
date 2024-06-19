# CHƯƠNG TRÌNH QUẢN LÝ KHO VÀ BÁN CỦA CỬA HÀNG CÀ PHÊ HIỀN ANH
***
**Tác Giả: Hoàng Đức Thuần**

**MSSV: K215480106046**

**Lớp: K57KMT**

**Ngày Hoàn Thành: 19/6/2024**

Mô tả bài toán quản lý: Cửa hàng Hiền Anh là một trong những cửa hàng bán hàng lớn và uy tín. Để quản lý cửa hàng lớn như vậy cần sự quản lý thật tốt để đảm bảo lợi nhuận và doanh thu. Giúp tối ưu hoá công việc, giúp báo cáo chính xác về tình hình kinh doanh. Bài tập này sẽ sử dụng ngôn ngữ SQL để quản lý kho nhập - xuất sản phẩm và việc bán hàng của của hàng.
### Những chức năng xây dựng để quản lý kho và bán hàng:<p>
1.	Quản lý sản phẩm<p>
  •	Thêm, sửa đổi, xoá sản phẩm<p>
  •	Tìm kiến, lọc sản phẩm theo các tiêu chí của người dùng<p>
  •	Xem thông tin chi tiết từng sản phẩm<p>
  •	Xem số lượng tồn kho của mỗi sản phẩm<p>
2.	Quản lý kho<p>
  •	Khi bán sản phẩm hoặc nhập thêm nguyên liệu cập nhật số lượng hàng còn lại trong kho.<p>
  •	Xem số lượng và thống kê sản nguyên liệu hàng tồn kho<p>
Nhập xuất và báo cáo các thông tin liên quan đến kho và việc bán hàng<p>
1.	Nhập hàng:<p>
  •	Quản lý việc nhập hàng từ nhà cung cấp vào kho hàng.<p>
  •	Ghi nhận thông tin về sản phẩm, số lượng, giá cả và nhà cung cấp.<p>
  •	Cập nhật lại số hàng tồn kho sau mỗi lần bán hoặc nhập hàng về.<p>
  •	Theo dõi đơn hàng từ nhà cung cấp và xác nhận quản lý khi hàng đã vào kho.<p>
2.	Xuất hàng:<p>
  •	Quản lý việc xuất các mặt hàng từ kho hàng để bán cho khách hàng.<p>
  •	Ghi nhận thông tin về sản phẩm, số lượng, giá cả và thông tin khách hàng.<p>
  •	Cập nhật tồn kho sau mỗi lần xuất hàng.<p>
  •	Theo dõi đơn hàng và xác nhận khi đã được giao.<p>
3.	Báo cáo<p>
  •	Báo cáo về doanh thu theo ngày, doanh thu theo tháng,... giúp quản lý được lợi nhuận.<p>
  •	Tạo và xem báo cáo hoạt động kinh doanh của cửa hàng, số lượng hàng tồn kho nhiều nhất, số lượng hàng bán chạy nhất,....<p>
1.	Sản phẩm sẽ quản lý những thông tin như: 🔑Mã sản phẩm, tên sản phẩm, thông tin, giá, số lượng còn lại, mô tả.<p>
2.	Khách hàng: 🔑Mã khách hàng, tên khách hàng, số điện thoại, địa chỉ, loại khách hàng.<p>
3.	Đơn hàng: 🔑Mã đơn hàng, mã khách hàng, ngày bán hàng, tổng tiền, mã sản phẩm, số lượng, giá, ghi chú.<p>
4.	Nhà cung cấp: 🔑Mã nhà cung cấp, tên nhà cung cấp, số điện thoại nhà cung cấp, tên người liên hệ, số điện thoại người liên hệ, địa chỉ.<p>
5.	Danh mục: 🔑Mã danh mục, tên danh mục, ghi chú.<p>
6.	Giao Dịch kho: 🔑Mã giao dịch, mã sản phẩm, số lượng, ngày nhập kho, ngày xuất kho.<p>
Như vậy, dựa theo những thông tin mà ta đã thu thập được chúng ta sẽ xây dựng các bảng đáp ứng yêu cầu quản lý của của hàng.
---
## Tạo các bảng như mô tả trong SQL Sever:<p>
1.Bảng Sản Phẩm<p>
![image](https://github.com/lazy1st/B-i-t-p-L-N-CSDL/assets/166302644/e5740186-0416-4e70-96da-0527f341431f)


Chú thích cho từng giá trị trong bảng SanPham:<p>
    •	MaSanPham: Mã định danh duy nhất cho mỗi sản phẩm, sử dụng làm khóa chính để đảm bảo tính duy nhất.<p>
    •	TenSanPham: Tên của sản phẩm, là một chuỗi ký tự có độ dài tối đa 255 ký tự và bắt buộc phải có giá trị.<p>
    •	ThongTin: Các thông tin chung về sản phẩm, thường là mô tả ngắn gọn hoặc thông tin kỹ thuật.<p>
    •	Gia: Giá bán của sản phẩm, được định dạng dưới dạng số thập phân với tối đa 10 chữ số trong đó có 2 chữ số sau dấu thập phân.<p>
    •	SoLuongConLai: Số lượng sản phẩm còn lại trong kho, là một số nguyên và bắt buộc phải có giá trị.<p>
    •	MoTa: Mô tả chi tiết hơn về sản phẩm, có thể bao gồm các thông tin như đặc điểm, công dụng, hướng dẫn sử dụng, v.v.<p>
2.Bảng Khách Hàng<p>
	![image](https://github.com/lazy1st/B-i-t-p-L-N-CSDL/assets/166302644/98b27901-face-4708-a700-49fdb1b714c3)
 
Chú thích cho từng giá trị trong bảng KhachHang:<p>
  •	MaKhachHang: Mã định danh duy nhất cho mỗi khách hàng, sử dụng làm khóa chính để đảm bảo tính duy nhất.<p>
  •	TenKhachHang: Tên của khách hàng, là một chuỗi ký tự có độ dài tối đa 255 ký tự và bắt buộc phải có giá trị.<p>
  •	SoDienThoai: Số điện thoại của khách hàng, là một chuỗi ký tự có độ dài tối đa 15 ký tự và bắt buộc phải có giá trị. Đây là thông tin liên lạc quan trọng.<p>
  •	DiaChi: Địa chỉ của khách hàng, là một chuỗi ký tự có độ dài tối đa 255 ký tự và bắt buộc phải có giá trị.<p>
  •	LoaiKhachHang: Loại khách hàng, là một chuỗi ký tự có độ dài tối đa 50 ký tự, dùng để phân loại khách hàng theo các nhóm khác nhau như khách hàng thường, khách hàng VIP, v.v. Đây là một trường tùy chọn, không bắt buộc phải có giá trị.<p>
2.bảng Đơn hàng<p>
 ![image](https://github.com/lazy1st/B-i-t-p-L-N-CSDL/assets/166302644/d96a65e6-9bea-4884-88b8-887db3c5abe2)

Chú thích cho từng giá trị trong bảng DonHang:<p>
    •	MaDonHang: Mã định danh duy nhất cho mỗi đơn hàng, sử dụng làm khóa chính để đảm bảo tính duy nhất.<p>
    •	MaKhachHang: Mã định danh của khách hàng, liên kết với bảng KhachHang để xác định khách hàng đã đặt hàng. Đây là một khóa ngoại.<p>
    •	NgayBanHang: Ngày bán hàng, là một giá trị ngày tháng để xác định ngày đơn hàng được tạo ra, bắt buộc phải có giá trị.<p>
    •	TongTien: Tổng số tiền của đơn hàng, được định dạng dưới dạng số thập phân với tối đa 10 chữ số, trong đó có 2 chữ số sau dấu thập phân.<p>
    •	MaSanPham: Mã định danh của sản phẩm, liên kết với bảng SanPham để xác định sản phẩm trong đơn hàng. Đây là một khóa ngoại.<p>
    •	SoLuong: Số lượng sản phẩm trong đơn hàng, là một số nguyên và bắt buộc phải có giá trị.<p>
    •	Gia: Giá của sản phẩm trong đơn hàng, được định dạng dưới dạng số thập phân với tối đa 10 chữ số, trong đó có 2 chữ số sau dấu thập phân.<p>
    •	GhiChu: Các ghi chú bổ sung về đơn hàng, có thể chứa các thông tin thêm như yêu cầu đặc biệt, ghi chú về giao hàng, v.v.<p>
    •	Các khóa ngoại: FOREIGN KEY (MaKhachHang) REFERENCES KhachHang(MaKhachHang) và FOREIGN KEY (MaSanPham) REFERENCES SanPham(MaSanPham) đảm bảo rằng mã khách hàng và mã sản phẩm trong đơn hàng phải tồn tại trong bảng KhachHang và SanPham tương ứng.<p>
 
4.Nhà Cung Cấp<p>	
![image](https://github.com/lazy1st/B-i-t-p-L-N-CSDL/assets/166302644/ccf03f69-78d1-4883-bc11-fb4255e5d7c6)
	 
Chú thích cho từng giá trị trong bảng NhaCungCap:<p>
  •	MaNhaCungCap: Mã định danh duy nhất cho mỗi nhà cung cấp, sử dụng làm khóa chính để đảm bảo tính duy nhất.<p>
  •	TenNhaCungCap: Tên của nhà cung cấp, là một chuỗi ký tự có độ dài tối đa 255 ký tự và bắt buộc phải có giá trị.<p>
  •	SoDienThoaiNhaCungCap: Số điện thoại của nhà cung cấp, là một chuỗi ký tự có độ dài tối đa 15 ký tự và bắt buộc phải có giá trị.<p>
  •	TenNguoiLienHe: Tên của người liên hệ tại nhà cung cấp, là một chuỗi ký tự có độ dài tối đa 255 ký tự và bắt buộc phải có giá trị.<p>
  •	SoDienThoaiNguoiLienHe: Số điện thoại của người liên hệ tại nhà cung cấp, là một chuỗi ký tự có độ dài tối đa 15 ký tự và bắt buộc phải có giá trị.<p>
  •	DiaChi: Địa chỉ của nhà cung cấp, là một chuỗi ký tự có độ dài tối đa 255 ký tự và bắt buộc phải có giá trị.<p>
5.bảng Danh Mục sản phẩm<p>
	 ![image](https://github.com/lazy1st/B-i-t-p-L-N-CSDL/assets/166302644/3c082c6b-1868-49de-865b-f2db32e81ff6)

Chú thích cho từng giá trị trong bảng DanhMuc:<p>
  •	MaDanhMuc: Mã định danh duy nhất cho mỗi danh mục, sử dụng làm khóa chính để đảm bảo tính duy nhất.<p>
  •	TenDanhMuc: Tên của danh mục, là một chuỗi ký tự có độ dài tối đa 255 ký tự và bắt buộc phải có giá trị.<p>
  •	GhiChu: Các ghi chú bổ sung về danh mục, có thể chứa các thông tin thêm như mô tả chi tiết, mục đích sử dụng, v.v. Đây là một trường tùy chọn và có thể để trống.<p>  
6.bảng giao dịch kho :<p>
	 ![image](https://github.com/lazy1st/B-i-t-p-L-N-CSDL/assets/166302644/662476e3-d28d-4313-ba32-8a964cad7437)

Chú thích cho từng giá trị trong bảng GiaoDichKho:<p>
  •	MaGiaoDich: Mã định danh duy nhất cho mỗi giao dịch kho, sử dụng làm khóa chính để đảm bảo tính duy nhất.<p>
  •	MaSanPham: Mã định danh của sản phẩm, liên kết với bảng SanPham để xác định sản phẩm trong giao dịch kho. Đây là một khóa ngoại.<p>
  •	SoLuong: Số lượng sản phẩm trong giao dịch kho, là một số nguyên và bắt buộc phải có giá trị.<p>
  •	NgayNhapKho: Ngày sản phẩm được nhập vào kho, là một giá trị ngày tháng. Đây là trường tùy chọn và có thể để trống nếu giao dịch chỉ là xuất kho.<p>
  •	NgayXuatKho: Ngày sản phẩm được xuất khỏi kho, là một giá trị ngày tháng. Đây là trường tùy chọn và có thể để trống nếu giao dịch chỉ là nhập kho.<p>
  •	Khóa ngoại FOREIGN KEY (MaSanPham) REFERENCES SanPham(MaSanPham) đảm bảo rằng mã sản phẩm trong giao dịch kho phải tồn tại trong bảng SanPham.<p>		
Tạo sơ đồ thực thể liên kết giữa các bảng :<p>
 ![image](https://github.com/lazy1st/B-i-t-p-L-N-CSDL/assets/166302644/2adaade6-72aa-4298-88f2-a553c0258e60)


Thêm dữ liệu vào các bảng<p>
1.	Dữ liệu thêm vào bảng SanPham<p>
-- Chèn dữ liệu vào bảng Danh mục sản phẩm<p>
INSERT INTO DanhMucSanPham (MaDanhMuc, TenDanhMuc, GhiChu)<p>
VALUES<p>
    '('muc1', 'Cà Phê Đen', ''),<p>
    ('muc2', 'Cà Phê Sữa', ''),<p>
    ('muc3', 'Cà Phê Phin', ''),<p>
    ('muc4', 'Cà Phê Capuchino', ''),<p>
    ('muc5', 'Cà Phê Trứng', '');<p>
    
2.Chèn dữ liệu vào bảng Sản phẩm

INSERT INTO SanPham (MaSanPham, TenSanPham, Gia, MoTa, MaDanhMuc)<p>
VALUES<p>
    ('M01', 'Cà Phê Đen',  15000,'Cà Phê Đen', 'muc1'),<p>
    ('M02', 'Cà Phê Sữa' , 20000, 'Cà Phê Sữa', 'muc1'),<p>
    ('M03', 'Cà Phê Phin' , 15000, 'Cà Phê Phin' , 'muc2'),<p>
    ('M04', 'Cà Phê Capuchino' , 20000,'Cà Phê Capuchino' , 'muc3'),<p>
    ('M05', 'Cà Phê Trứng' , 25000,'Cà Phê Trứng' , 'muc4');<p>

3.Chèn dữ liệu vào bảng Khách hàng<p>

INSERT INTO KhachHang (MaKhachHang, TenKhachHang, SoDienThoai, DiaChi, LoaiKhachHang)<p>
VALUES<p>
    ('KH001', 'Nguyen Van A', '0912345678', '123 Le Loi, TP.HCM', 'VIPP'),<p>
    ('KH002', 'Tran Thi B', '0987654321', '456 Hai Ba Trung, Ha Noi', 'VIP'),<p>
    ('KH003', 'Le Van C', '0909123456', '789 Nguyen Trai, Da Nang', 'New'),<p>
    ('KH004', 'Pham Thi D', '0934567890', '321 Tran Hung Dao, Can Tho', 'VIPP'),<p>
    ('KH005', 'Hoang Van E', '0976543210', '654 Le Duan, Hue', 'VIP');<p>
    
4.Chèn dữ liệu vào bảng Đơn Hàng<p>

INSERT INTO DonHang (MaDonHang, MaKhachHang, NgayBanHang, TongTien, MaSanPham, SoLuong, Gia, GhiChu)<p>
VALUES<p>
    ('DH001', 'KH001', '2024-06-19', 30000, 'M01', 2, 15000, 'Uống lạnh'),<p>
    ('DH002', 'KH002', '2024-06-20', 40000, 'M02', 2, 20000, 'Uống nóng'),<p>
    ('DH003', 'KH003', '2024-06-21', 30000, 'M03', 2, 15000, 'Không đá'),<p>
    ('DH004', 'KH004', '2024-06-22', 40000, 'M04', 2, 20000, 'Mang đi'),<p>
    ('DH005', 'KH005', '2024-06-23', 50000, 'M05', 2, 25000, '');<p>

5.Chèn dữ liệu vào bảng Nha Cung Cấp<p>

INSERT INTO NhaCungCap (MaNhaCungCap, TenNhaCungCap, SoDienThoaiNhaCungCap, TenNguoiLienHe, SoDienThoaiNguoiLienHe, DiaChi)<p>
VALUES<p>
    ('NCC01', 'Nhà Cung Cấp Phúc Long', '0903456789', 'Nguyễn Văn Long', '0912345678', '12 Trần Hưng Đạo, Hoàn Kiếm, Hà Nội'),<p>
    ('NCC02', 'Nhà Cung Cấp Trung Nguyên', '0909876543', 'Trần Thị Trung', '0918765432', '34 Lý Thái Tổ, Hoàn Kiếm, Hà Nội'),<p>
    ('NCC03', 'Nhà Cung Cấp Highland', '0901122334', 'Lê Văn Cao', '0911122334', '56 Hai Bà Trưng, Hoàn Kiếm, Hà Nội'),<p>
    ('NCC04', 'Nhà Cung Cấp Starbucks', '0902233445', 'Phạm Thị Hoa', '0912233445', '78 Bà Triệu, Hai Bà Trưng, Hà Nội'),<p>
    ('NCC05', 'Nhà Cung Cấp Coffee House', '0903344556', 'Hoàng Minh', '0913344556', '90 Đinh Tiên Hoàng, Hoàn Kiếm, Hà Nội');<p>

6.Chèn dữ liệu vào bảng giao dịch Kho<p>
	INSERT INTO GiaoDichKho (MaGiaoDich, MaSanPham, SoLuong, NgayNhapKho, NgayXuatKho, MaNhaCungCap)<p>
VALUES<p>
    ('GD01', 'M01', 100, '2024-06-19', NULL, 'NCC01'),<p>
    ('GD02', 'M02', 150, '2024-06-18', NULL, 'NCC02'),<p>
    ('GD03', 'M03', 120, '2024-06-17', NULL, 'NCC03'),<p>
    ('GD04', 'M04', 80, '2024-06-16', NULL, 'NCC04'),<p>
    ('GD05', 'M05', 200, '2024-06-15', NULL, 'NCC05');<p>
7.Kiểm tra dữ liệu trong các bảng đã tạo<p>
  SELECT * FROM DanhMucSanPham;<p>
![image](https://github.com/lazy1st/B-i-t-p-L-N-CSDL/assets/166302644/b94f0c9b-ba04-4a38-987a-e42d530b1f09)

 SELECT * FROM SanPham;<p>
 ![image](https://github.com/lazy1st/B-i-t-p-L-N-CSDL/assets/166302644/3fbdfabf-916f-44cf-a992-ee3a3144c3ba)

 SELECT * FROM KhachHang;<p>
 ![image](https://github.com/lazy1st/B-i-t-p-L-N-CSDL/assets/166302644/3fec97b7-cea5-4b36-8364-cf10fab06a95)

 SELECT * FROM DonHang;<p>
 ![image](https://github.com/lazy1st/B-i-t-p-L-N-CSDL/assets/166302644/98f2b2dd-d457-4e05-9ca4-d3c90f50ed5c)

 SELECT * FROM NhaCungCap;<p>
 ![image](https://github.com/lazy1st/B-i-t-p-L-N-CSDL/assets/166302644/27b9f70c-5a22-4326-b253-53e333318d9f)

 SELECT * FROM GiaoDichKho;<p>
![image](https://github.com/lazy1st/B-i-t-p-L-N-CSDL/assets/166302644/a56af0ac-3319-45c5-b408-a42f0db97d76)
 
XÂY DỰNG CÁC THỦ TỤC THEO CÁC CHỨC NĂNG MONG MUỐN
Yêu cầu<p>
1.	Quản lý việc bán hàng<p>
  •	Thêm, sửa, xoá sản phẩm<p>
  •	Tìm kiếm sản phẩm, lọc sản phẩm theo các tiêu chí của người quản lý hoặc của khách hàng<p>
  •	Xem thông tin chỉ tiết mỗi sản phẩm<p>
  •	Doanh thu của một ngày, một tháng,...<p>
  •	Số lượng sản phẩm bán chạy nhất.<p>
2.	Quản lý kho<p>
  •	Thống kê số lượng hàng trong kho<p>
  •	Báo cáo tình trạng hàng trong kho, số hàng tồn, số hàng đã hết chưa nhập về.<p>
Xây dựng<p>
 
<code> -- thêm sản phẩm
CREATE PROCEDURE themsanpham
    @MaSanPham NVARCHAR(255),
	@TenSanPham NVARCHAR(250),
    @Gia DECIMAL(10, 2),
    @MoTa NVARCHAR(50),
	@MaDanhMuc NVARCHAR(50)
 AS
BEGIN
    SET NOCOUNT ON;

 -- Kiểm tra xem sản phẩm có tồn tại hay không trước khi chèn
    IF NOT EXISTS (SELECT 1 FROM SanPham WHERE TenSanPham = @TenSanPham)
    BEGIN
        INSERT INTO SanPham (MaSanPham,TenSanPham, Gia ,MoTa, MaDanhMuc )
        VALUES (@MaSanPham,@TenSanPham ,@Gia ,@MoTa,@MaDanhMuc);
        SELECT 'Thêm sản phẩm thành công' AS [Result];
    END
    ELSE
    BEGIN
        SELECT 'Tên sản phẩm đã tồn tại. Không thể thêm sản phẩm.' AS [Result];
    END
END;
GO

--thêm sản phẩm <p>
EXEC themsanpham
    @MaSanPham = 'M06',
    @TenSanPham = N'Cà Phê Sữa Đá',
    @Gia = 35000,
    @MoTa = N'Cà phê sữa đá thơm ngon',
    @MaDanhMuc = 'muc4';


CREATE PROCEDURE XoaSanPham
    @MaSanPham NVARCHAR(50)
AS
BEGIN
    SET NOCOUNT ON;

-- Kiểm tra sản phẩm có tồn tại trong bảng SanPham không
    IF EXISTS (SELECT 1 FROM SanPham WHERE MaSanPham = @MaSanPham)
    BEGIN
  -- Xóa các bản ghi liên quan trong bảng DonHang trước (nếu cần)
        DELETE FROM DonHang WHERE MaSanPham = @MaSanPham;

     -- Xóa các bản ghi liên quan trong bảng GiaoDichKho trước (nếu cần)
        DELETE FROM GiaoDichKho WHERE MaSanPham = @MaSanPham;

    -- Xóa sản phẩm khỏi bảng SanPham
        DELETE FROM SanPham WHERE MaSanPham = @MaSanPham;

        SELECT 'Xóa sản phẩm thành công' AS [Result];
    END
    ELSE
    BEGIN
        SELECT 'Sản phẩm không tồn tại. Không thể xóa sản phẩm.' AS [Result];
    END
END;
GO

EXEC XoaSanPham @MaSanPham = 'M01';<p>
 
CREATE PROCEDURE CapNhatSanPham
    @MaSanPham NVARCHAR(50),
    @TenSanPham NVARCHAR(255) = NULL,
    @Gia DECIMAL(10, 2) = NULL,
    @MoTa NVARCHAR(50) = NULL,
    @MaDanhMuc NVARCHAR(50) = NULL
AS
BEGIN
    SET NOCOUNT ON;

-- Kiểm tra sản phẩm có tồn tại trong bảng SanPham không
    IF EXISTS (SELECT 1 FROM SanPham WHERE MaSanPham = @MaSanPham)
    BEGIN
    -- Cập nhật thông tin sản phẩm
        UPDATE SanPham
        SET 
            TenSanPham = ISNULL(@TenSanPham, TenSanPham),
            Gia = ISNULL(@Gia, Gia),
            MoTa = ISNULL(@MoTa, MoTa),
            MaDanhMuc = ISNULL(@MaDanhMuc, MaDanhMuc)
        WHERE MaSanPham = @MaSanPham;

        SELECT 'Cập nhật sản phẩm thành công' AS [Result];
    END
    ELSE
    BEGIN
        SELECT 'Sản phẩm không tồn tại. Không thể cập nhật sản phẩm.' AS [Result];
    END
END;
GO<p>

EXEC CapNhatSanPham 
    @MaSanPham = 'M01',
    @TenSanPham = N'Cà Phê Đen Đá',
    @Gia = 16000,
    @MoTa = N'Cà Phê Đen Đá',
    @MaDanhMuc = 'muc1';
-- tìm kiếm sản phẩm 
 
CREATE PROCEDURE TimKiemSanPham
    @MaSanPham NVARCHAR(50) = NULL,
    @TenSanPham NVARCHAR(255) = NULL,
    @MaDanhMuc NVARCHAR(50) = NULL
AS
BEGIN
    SET NOCOUNT ON;

    SELECT MaSanPham, TenSanPham, Gia, MoTa, MaDanhMuc
    FROM SanPham
    WHERE 
        (@MaSanPham IS NULL OR MaSanPham = @MaSanPham) AND
        (@TenSanPham IS NULL OR TenSanPham LIKE '%' + @TenSanPham + '%') AND
        (@MaDanhMuc IS NULL OR MaDanhMuc = @MaDanhMuc);
END;
GO<p>
EXEC TimKiemSanPham @MaSanPham = 'M01';
 
 --Tính tổng doanh thu của ngày được chỉ định
USE BTLSQL;
GO

CREATE PROCEDURE TinhDoanhThuNgay
    @NgayBanHang DATE
AS
BEGIN
    SET NOCOUNT ON;

-- Hàm Tính tổng doanh thu của ngày được chỉ định
    SELECT SUM(TongTien) AS DoanhThu
    FROM DonHang
    WHERE NgayBanHang = @NgayBanHang;
END;
GO 
EXEC TinhDoanhThuNgay @NgayBanHang = '2024-06-21'; 
 
-- Sản phẩm bán chạy nhất tháng

CREATE PROCEDURE SanPhamBanChayNhatoTrongThang
    @Thang INT,
    @Nam INT
AS
BEGIN
    SET NOCOUNT ON; -- Tắt thông báo số bản ghi bị ảnh hưởng

 -- Khai báo biến để lưu ngày bắt đầu và ngày kết thúc của tháng cần thống kê
    DECLARE @StartDate DATE, @EndDate DATE;
    SET @StartDate = DATEFROMPARTS(@Nam, @Thang, 1); -- Ngày đầu tiên của tháng
    SET @EndDate = DATEADD(DAY, -1, DATEADD(MONTH, 1, @StartDate)); -- Ngày cuối cùng của tháng

 -- Sử dụng CTE để tính tổng số lượng sản phẩm bán ra và lấy sản phẩm bán chạy nhất
    WITH BanChayNhat AS (
        SELECT TOP 1
            DH.MaSanPham,
            SUM(DH.SoLuong) AS TongSoLuongBan 
        FROM DonHang DH
        WHERE DH.NgayBanHang >= @StartDate AND DH.NgayBanHang <= @EndDate -- Điều kiện: Đơn hàng trong tháng
        GROUP BY DH.MaSanPham 
        ORDER BY SUM(DH.SoLuong) DESC -- Sắp xếp giảm dần theo tổng số lượng bán
    )
-- Truy vấn để lấy thông tin chi tiết của sản phẩm bán chạy nhất
    SELECT 
        BC.MaSanPham, 
        SP.TenSanPham, 
        SP.Gia, 
        SP.MoTa,
        BC.TongSoLuongBan 
    FROM BanChayNhat BC
    INNER JOIN SanPham SP ON BC.MaSanPham = SP.MaSanPham;-- Liên kết với bảng SanPham để lấy thông tin chi tiết
END;
GO 
 
- Tạo stored procedure ThongKeSoLuongHangTrongKho
CREATE PROCEDURE ThongKeSoLuongHangTrongKho
AS
BEGIN
    SET NOCOUNT ON;

    SELECT 
        SP.MaSanPham,
        SP.TenSanPham,
        ISNULL(SUM(GDK.SoLuong), 0) AS TongSoLuongTon
    FROM 
        SanPham SP
    LEFT JOIN 
        GiaoDichKho GDK ON SP.MaSanPham = GDK.MaSanPham
    GROUP BY 
        SP.MaSanPham, SP.TenSanPham
    ORDER BY 
        SP.TenSanPham;
END;
GO

-- Tạo trigger để cập nhật số lượng tồn kho khi có thay đổi trong bảng GiaoDichKho
CREATE TRIGGER trg_UpdateInventory
ON GiaoDichKho
AFTER INSERT, UPDATE, DELETE
AS
BEGIN
    SET NOCOUNT ON;

    DECLARE @MaSanPham INT;

-- Con trỏ để xử lý các bản ghi bị ảnh hưởng
    DECLARE cur CURSOR FOR
    SELECT DISTINCT MaSanPham FROM (
        SELECT MaSanPham FROM inserted
        UNION
        SELECT MaSanPham FROM deleted
    ) AS affected;

    OPEN cur;

    FETCH NEXT FROM cur INTO @MaSanPham;

    WHILE @@FETCH_STATUS = 0
    BEGIN
    -- Cập nhật số lượng tồn kho cho sản phẩm hiện tại
        UPDATE SanPham
        SET TongSoLuongTon = 
            (SELECT ISNULL(SUM(GDK.SoLuong), 0)
             FROM GiaoDichKho GDK
             WHERE GDK.MaSanPham = @MaSanPham)
        WHERE MaSanPham = @MaSanPham;

        FETCH NEXT FROM cur INTO @MaSanPham;
    END;

    CLOSE cur;
    DEALLOCATE cur;
END;
 
