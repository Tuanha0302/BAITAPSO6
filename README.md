# <p align="center">***Bài tập 6: Hệ quản trị CSDL***</p>
# <p align="center">***Ngụy Đình Tuấn Hà_K225480106011***</p>
# Yêu cầu bài toán: 
Cho file sv_tnut.sql (1.6MB)
1. Hãy nêu các bước để import được dữ liệu trong sv_tnut.sql vào sql server của em
2. dữ liệu đầu vào là tên của sv; sđt; ngày, tháng, năm sinh của sinh viên (của sv đang làm bài tập này)
3. nhập sql để tìm xem có những sv nào trùng hoàn toàn ngày/tháng/năm với em?
4. nhập sql để tìm xem có những sv nào trùng ngày và tháng sinh với em?
5. nhập sql để tìm xem có những sv nào trùng tháng và năm sinh với em?
6. nhập sql để tìm xem có những sv nào trùng tên với em?
7. nhập sql để tìm xem có những sv nào trùng họ và tên đệm với em.
8. nhập sql để tìm xem có những sv nào có sđt sai khác chỉ 1 số so với sđt của em.
9. BẢNG SV CÓ HƠN 9000 ROWS, HÃY LIỆT KÊ TẤT CẢ CÁC SV NGÀNH KMT, SẮP XẾP THEO TÊN VÀ HỌ ĐỆM, KIỂU TIẾNG  VIỆT, GIẢI THÍCH.
10. HÃY NHẬP SQL ĐỂ LIỆT KÊ CÁC SV NỮ NGÀNH KMT CÓ TRONG BẢNG SV (TRÌNH BÀY QUÁ TRÌNH SUY NGHĨ VÀ GIẢI NHỮNG VỨNG MẮC)

# 1. Hãy nêu các bước để import được dữ liệu trong sv_tnut.sql vào sql server
để import được dữ liệu trong sv_tnut.sql thì đầu tiên em tải file sv_tnut.sql về máy. Sau đó tạo 1 database mới mang tên sv_tnut rồi em mở file sv_tnut.sql vừa tải về -> execute toàn bộ file sv_tnut.sql 
![image](https://github.com/user-attachments/assets/c335fc63-b9c8-4d63-a901-d2d3f834c6e6)
Sau khi đã chạy em được bảng dữ liệu dbo.SV như hình:
![image](https://github.com/user-attachments/assets/83523af0-8fd8-4186-a881-d8162bcf84a1)

# 2. dữ liệu đầu vào là tên của sv; sđt; ngày, tháng, năm sinh của sinh viên (của sv đang làm bài tập này)
Để thêm dữ liệu đầu vào là tên của sv, sdt, ngày, tháng, năm sinh thì em sử dụng câu lệnh sau ví dụ: thông tin của em
![image](https://github.com/user-attachments/assets/8b6df949-5300-44f5-9acc-ee29dc3ffdf0)

Khi thêm dữ liệu xong em thử lấy tên để kiểm tra xem dữ liệu đã được thêm vào hay chưa 
![image](https://github.com/user-attachments/assets/a9359fff-884b-4df3-b098-9b209b206305)
Nếu sau khi ta chạy câu lệnh ra được thông tin ta vừa thêm thì là đã đã hoàn tất việc thêm dữ liệu mới vào bảng 

# 3. nhập sql để tìm xem có những sv nào trùng hoàn toàn ngày/tháng/năm với em?
Để tìm xem có nhưng sv nào trùng hoàn toàn ngày/tháng/năm hay không em dùng câu lệnh sau để kiểm tra dữ liệu trong bảng:
![image](https://github.com/user-attachments/assets/50ce54df-8faa-4945-9f4b-299d1a245640)

# 4. nhập sql để tìm xem có những sv nào trùng ngày và tháng sinh với em?
Để tìm xem có những sv nào trùng ngày và tháng sinh với em thì em dùng DAY() và MONTH() để so sánh ngày và tháng ( không dùng năm sinh )
![image](https://github.com/user-attachments/assets/9ffc6766-8ce2-4124-9c72-9737a279f598)

# 5. nhập sql để tìm xem có những sv nào trùng tháng và năm sinh với em?
Với yêu cầu của câu 5 thì em sử dụng câu lệnh gần giống như câu 4 nhưng ở đâu em không dùng DAY() nữa vì yêu cầu bài toán là tìm tháng, năm lên em sử dụng MONTH() và YEAR() thay vì sử dụng DAY(), MONTH()
![image](https://github.com/user-attachments/assets/02d2b196-8715-48b5-8086-c86c26d9bd78)

# 6. nhập sql để tìm xem có những sv nào trùng tên với em?
Để tìm xem có những sv nào trùng tên với em thì em sử dụng câu lệnh truy vấn sau: 
![image](https://github.com/user-attachments/assets/0016aa4d-e760-4174-8971-db6060ff5fa5)

# 7. nhập sql để tìm xem có những sv nào trùng họ và tên đệm với em.
Để tìm xem có những sv nào trùng họ và tên đệm với em thì em dùng câu lệnh truy vẫn sau:
![image](https://github.com/user-attachments/assets/5e3581e6-68db-4c6f-bf23-556839c2d821)

# 8. nhập sql để tìm xem có những sv nào có sđt sai khác chỉ 1 số so với sđt của em.
Để tìm xem có những sv nào có sdt sai khác chỉ 1 số với sdt của em thì em dùng câu lệnh sau:
![image](https://github.com/user-attachments/assets/731e335b-6bf0-4724-b382-63fe4449a1ed)
Giải thích lênh:
+ SUBSTRING(sdt,i,1) lấy i là số thứ tự trong số điện thoại ở đây em có tổng cộng 10 con số
+ SUBSTRING('0396988607',i,1) là số điện thoại của em muốn so sánh
+ Dùng IIF(..., 1,0) để cộng dồn các ký tự khác nhau nếu có từ 2 hay giống số khác với sdt của em thì nó sẽ bị loại. Ở dòng lệnh này chỉ khi nào sdt khác chỉ 1 số thì mới đúng.

# 9. BẢNG SV CÓ HƠN 9000 ROWS, HÃY LIỆT KÊ TẤT CẢ CÁC SV NGÀNH KMT, SẮP XẾP THEO TÊN VÀ HỌ ĐỆM, KIỂU TIẾNG  VIỆT, GIẢI THÍCH.
Để liệt kê tất cả cac ngành KMT, sắp xếp tên và họ đệm, kiểu tiếng việt thì em dùng câu lệnh truy vấn sau:
![image](https://github.com/user-attachments/assets/bc542e12-ddc7-4e19-a940-43ebdb659162)
Giải thích lệnh:
+ Để lọc các sinh viên có (lop) thuộc KMT và KTP thì em sử dụng LIKE '%KMT%' và LIKR'%KTP%' để lọc dữ liệu
+ Để sắp xếp theo tên và họ đệm thì em dùng lệnh ORDER BY ten COLLATE Vietnamese_CI_AS, hodem COLLATE Vietnamese_CI_AS;
  + Vietnamese là để sắp xếp theo thứ tự bảng chữ cái tiếng việt
  + 'CI'(Case-Insensitive) dùng để không phân biệt chữ hoa/thường
  + 'AS'(Accent-Sensitive) dùng để phân biệt dấu (ví dụ: a khác á)

# 10. HÃY NHẬP SQL ĐỂ LIỆT KÊ CÁC SV NỮ NGÀNH KMT CÓ TRONG BẢNG SV (TRÌNH BÀY QUÁ TRÌNH SUY NGHĨ VÀ GIẢI NHỮNG VỨNG MẮC)
Để liệt kê các sv nữ ngành KMT có trong bảng sv thì em dùng câu lênh sau: 
![image](https://github.com/user-attachments/assets/a184e6ab-79f1-42bd-ace7-5660228d6027)
Giải thích:
+ vì trong bảng sv không có cột giới tính nên em dựa vào họ đêm. Em lọc những sinh viên có họ đêm là 'Thị' làm 1 điều kiện để lọc sinh viên
+ Tiếp theo em truy vấn 1 số cái tên nữ mà em biết để lọc bước 2 rồi hiển thị ra bảng sv nữ ngành KMT và KTP.









