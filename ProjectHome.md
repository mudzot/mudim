# Giới thiệu #

Mudim là bộ gõ tiếng Việt viết trên Javascript đùng để tích hợp vào các trang web. Mudim được phát triển dựa trên bộ gõ [CHIM](http://xvnkb.sourceforge.net/chim/) của MrChuoi, ngoài ra tham khảo ý tưởng và do đó mang nhiều nhiều ưu điểm của các bộ gõ khác cùng loại.  Tổng hợp lại, Mudim trở thành bộ gõ đặc biệt dễ sử dụng, cài đặt đối với các nhà phát triển web cũng như tiện dùng cho khách viếng thăm trang web.

Để tiện dụng hơn nữa cho những ai dùng trình duyệt Firefox, Mudim có phiên bản Firefox Extension tích hợp trực tiếp vào Firefox, giúp bạn gõ tiếng Việt trên bất kỳ trang web nào , đặc biệt không xung đột với bộ gõ tích hợp trên trang web nếu có.

Trong quá trình sử dụng nếu bạn có ý kiến đóng góp hoặc thắc mắc gì, xin hãy đọc kỹ các trang wiki ở cột bên phải, nếu thắc mắc chưa được giải đáp xin hãy tạo mục mới trong trang [Issues](http://code.google.com/p/mudim/issues/list), nhưng bạn cũng nên tìm trong các issues có trước, có thể có ai đã đưa ra cùng ý kiến với bạn rồi.

Bạn cũng có thể ghé qua trang [PhanHoi](PhanHoi.md) để biết ý kiến của những người đã ứng dụng Mudim thành công. Nếu bạn đã ứng dụng thành công Mudim vào trang web của mình hãy vào đó để giới thiệu với mọi người.

# Tính năng #
  * Bảng điều khiển rất thuận tiện
  * Lưu lại thiết lập của bạn tương ứng với từng trang web (bạn cần chấp nhận cookie)
  * Hỗ trợ 3 kiểu gõ thông dụng Telex, VNI và VIQR.
  * Bỏ dấu theo quy tắc mới (khuyến khích) hoặc nếu bạn thực sự không ưa kiểu bỏ dấu này, bạn có thể chuyển về quy tắc bỏ dấu cũ.
  * Chức năng bỏ dấu thông minh, tự động bỏ dấu đúng chỗ
  * Chạy tốt trên nhiều loại trình duyệt web thông dụng (Firefox, Internet Explorer, Opera, Konqueror)

Bạn có thể tham khảo BangSoSanh

# Tải về #

Bạn hãy vào trang [Downloads](http://code.google.com/p/mudim/downloads/list) để tải cho mình bản phù hợp.
  * mudim-x.y-rN.js : File duy nhất bạn cần nếu tất cả những gì bạn muốn chỉ là tích hợp mudim vào trang web của bạn.
  * mudim-x.y-rN.zip : Ngoài file mudim.js trong file zip này có chứa trang thử nghiệm tính năng để bạn làm quen với mudim.

Với bản Mudim Firefox extension bạn nên cài đặt trực tiếp từ trang addons của mozilla tại địa chỉ https://addons.mozilla.org/en-US/firefox/addon/7224

Mudim plugin cũng được cung cấp sẵn cho các ứng dụng web nổi tiếng. Bạn hãy vào trang MudimPlugins, rất có thể plugin cho ứng dụng bạn cần đã có sẵn.

# Hướng dẫn #

## _Bản dùng cho trang web_ ##

### Dành cho khách viếng thăm trang web ###

Lần đầu viếng thăm trang web bảng điều khiển sẽ tự động bật ra để bạn chọn kiểu gõ, các thiết lập này sẽ được lưu lại và sử dụng trong những lần viếng thăm sau đó, bạn sẽ không phải chọn lại nữa

Trong quá trình viếng thăm bạn vẫn có thể Mở hoặc đóng bảng điều khiển với phím tắt **F8**. Bạn cũng có thể tạm thời bật hoặc tắt bộ gõ với phím tắt **F9** hoặc **F10**

Hướng dẫn đầy đủ có tại trang [HuongDanSuDung](HuongDanSuDung.md)

### Dành cho nhà phát triển web ###

Để tích hợp Mudim vào trang web của bạn, tất cả những gì bạn cần làm là thêm **một dòng** dưới đây vào đầu hoặc cuối hoặc giữa trang web tuỳ ý bạn.

`<script src="/path/to/mudim.js"></script>`

Trong đó /path/to/mudim.js là đường dẫn tuyệt đối hoặc tương đối tới file mudim.js của bạn.

Hướng dẫn chi tiết hơn bạn hãy xem mục HuongDanCaiDat

## _Bản Firefox extension_ ##

  * Dùng phím tắt: Alt-/ dùng để bật tắt bộ gõ và Alt-, (dấu phẩy) để chuyển đổi cách gõ.
  * Dùng chuột: kích chuột trái vào biểu tượng của Mudim ở góc dưới để chuyển đổi cách gõ, kích chuột phải để mở menu popupu hiệu chỉnh Mudim.

Hướng dẫn đầy đủ có tại trang [HuongDanSuDung](HuongDanSuDung.md)

# Demo thử nghiệm #

Bạn có thể thử nghiệm tính năng của mudim tại [đây](http://www.anhn.net/test/mudim/), thử Mudim trong các tình huống khác nhau và các web edior khác nhau. Bản Mudim tại đó luôn được cập nhật từ bản trong svn do vậy luôn được fix issues sớm nhất, và bạn có thể lưu file mudim.js tại đây để dùng nếu muốn.

# Bản quyền #
Mudim được phát hành theo giấy phép GPLv2, có tại địa chỉ http://www.gnu.org/licenses/gpl.html . Bạn có toàn quyền sửa chữa file script theo ý mình nhưng  hãy tôn trọng công sức đã bỏ ra của những người viết nên phần mềm này và giữ lại thông tin về tác giả trong đó. Xin cảm ơn.

# Thông tin #
  * **Ngày 11.12.2008**
    * rev 153 sau gần nửa năm, thêm kiểu gõ tự động, sửa lỗi khá nghiêm trọng với IE

  * **Ngày 03.06.2008**
    * Phát hành Mudim 0.8. Điểm mới ở bản này là chức năng tạm thời tắt bộ gõ hoặc tắt kiểm tra chính tả.

  * **Ngày 27.05.2008**
    * Đã có plugin cho Joomla (xem [MudimPlugins](MudimPlugins.md))

  * **Ngày 21.05.2008**
    * Cập nhật bản FF extension tương thích với Firefox 3.0 RC1 mới ra
    * Đã có plugin cho Wordpress và VBB (xem [MudimPlugins](MudimPlugins.md))

  * **Ngày 19.05.2008**:
    * Call for developers: kêu gọi các developers về vấn đề Mudim plugin cho các loại CMS và forum thông dụng ([Issue #27](https://code.google.com/p/mudim/issues/detail?id=#27))
    * Sau khi tích cóp được kha khá những lần sửa lỗi và cải tiến, bản 0.7 đã được phát hành bắt đầu từ [r76](https://code.google.com/p/mudim/source/detail?r=76). Một vài điểm thay đổi đáng chú ý : thắt chặt kiểm tra chính tả, rút kiểu Viqr khỏi kiểu gõ tổng hợp, lưu lại các thiết lập ẩn hiện bảng điều khiển và kiểu bỏ dấu.

  * **Ngày 14.05.2008**
    * Phát hành Mudim 0.6. Thêm cách gõ Auto, tổng hợp của cả 3 cách gõ. Thêm một số quy tắc soát lỗi chính tả.

  * **Ngày 11.05.2008**
    * Phát hành Mudim 0.5. Sửa [issue 5](https://code.google.com/p/mudim/issues/detail?id=5), [issue 6](https://code.google.com/p/mudim/issues/detail?id=6) và [issue 7](https://code.google.com/p/mudim/issues/detail?id=7). Từ bản này Mudim được pack và đóng gói bằng script.

  * **Ngày 10.05.2008**
    * Phát hành bản 0.4. Cũng từ bản này trở đi Mudim được phát hành ở dạng thu gọn (~17KB), sửa [issue 3](https://code.google.com/p/mudim/issues/detail?id=3) và [issue 4](https://code.google.com/p/mudim/issues/detail?id=4) cùng một lỗi nhỏ khi xoá và điền lại dấu.