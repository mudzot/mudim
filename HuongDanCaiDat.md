# Hướng dẫn chung #

### Cài đặt Mudim ###

Để tích hợp Mudim vào trang web của bạn, tất cả những gì bạn cần làm là thêm **một dòng** dưới đây vào bất kỳ vị trí nào trang web, giữa 2 tag 

&lt;head&gt;



&lt;/head&gt;

 chẳng hạn.

`<script src="/path/to/mudim.js"></script>`

Trong đó /path/to/mudim.js là đường dẫn tuyệt đối hoặc tương đối tới file mudim.js của bạn.

**Ví dụ 1 - đưòng dẫn tương đối**

Giả sử trang web của bạn là http://www.abc.com/index.html và bạn đặt file mudim.js tại địa chỉ http://www.abc.com/scripts/mudim.js thì bạn chỉ cần thêm dòng sau vào **ngay trước** tag **Unknown end tag for &lt;/body&gt;** trong trang đó

`<script src="scripts/mudim.js"></script>`

**Ví dụ 2 - đường dẫn tuyệt đối**
Chẳng hạn bạn muốn dùng chùa file script của một site khác, với địa chỉ là http://www.def.com/free/scripts/mudim.js thì bạn cần thêm dòng sau:

`<script src="scripts/mudim.js"></script>`

### Hiệu chỉnh Mudim ###
Nếu bạn cảm thấy giao diện mặc định của Mudim đã phù hợp với trang web của bạn, bạn có thể bỏ qua phần này. Nếu không, bạn hãy mở file mudim.js nhìn những dòng cuối cùng. Có 3 giá trị bạn có thể thay đổi

**Màu nền và màu chữ của bảng điều khiển**

Mặc định màu nên là lightYellow, bạn có thể đổi thành bất cứ màu nào hợp lệ trong HTML, ví dụ như `Mudim.PANEL_BACKGROUND='lightBlue';` hoặc `Mudim.PANEL_BACKGROUND='#FFDDDD';`. Tương tự với màu chữ `COLOR='Black'`

**Ngôn ngữ**

Ngôn ngữ mặc định trên bảng điều khiển là tiếng Việt và bạn có thể thay đổi nếu muốn. Những giá trị VNI, Telex, Viqr không thể thay đổi.

`Mudim.LANG=['Tắt','VNI','Telex','Viqr','Tự động','Chính tả','Bỏ dấu kiểu mới','Bật/Tắt','Ẩn/Hiện bảng điều khiển'];`

**Những ô nhập văn bản ngoại lệ**

Nếu trang web của bạn có những ô nhập văn bản bạn không muốn gõ tiếng Việt trong đó, hãy đặt id của các ô đó vào mảng IGNORE\_ID:

`Mudim.IGNORE_ID = ['englishform','notViet','camgotiengviet'];`

# Hướng dẫn cụ thể cho từng ứng dụng web #



&lt;TODO&gt;

