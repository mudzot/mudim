# Giới thiệu #

Công cụ [mudimTest](http://mudim.googlecode.com/files/testTool.zip) được viết bằng [Autoit](http://www.autoitscript.com/autoit3/) với mục đích tự động hoá quá trình test mudim với các dữ liệu test khác nhau. File testmudim.exe đã được biên dịch sẵn, tuy nhiên do viết bằng Autoit, rất có thể nó sẽ bị các chương trình chống virus cảnh báo và chặn lại. Để chắc chắn tuyệt đối rằng trong chương trình không chứa mã độc hại, bạn có thể tải Autoit về và biên dịch lại file mã nguồn .au3 đi kèm.

# Hướng dẫn sử dụng #

### Nhập dữ liệu ###

Đặt file input.txt cùng thư mục với testmudim.exe; nhập dữ liệu các trường hợp test của bạn vào file này, mỗi trường hợp 1 dòng theo dạng

<nội dung test>**,**<số lần test>

Ví dụ bạn cần thử chuỗi 'huowng' 10 lần hãy nhập dòng sau vào file input.txt

**huowng,10**

### Chạy test ###

  * Mở trang thử nghiệm Mudim (có title là Mudim testing) và chọn kiểu gõ.
  * Chuyển con trỏ vào ô nhập văn bản cần thử (vào textarea chẳng hạn).
  * Chạy file testmudim.exe.
  * Chuyển về cửa sổ của trang thử nghiệm và nhìn các trường hợp test chạy tự động. Bạn nên ngồi chờ đến khi test xong, không nên làm gián đoạn quá trình này.
  * Nhìn lại kết quả xem có gì bất thường không, nếu có xin báo về trang [Issues](http://code.google.com/p/mudim/issues/list)