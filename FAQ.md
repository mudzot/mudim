# Giới thiệu #

Trang này giải đáp vấn đề thường gặp trong quá trình tích hợp Mudim vào trang web, giúp Mudim bạn hiệu chỉnh Mudim một cách phù hợp nhất với hệ thống của bạn. Tài liệu này được viết dưới dạng hỏi đáp, chủ yếu hướng tới developer.

Tuy phần code chính của Mudim đã được pack lại, không thể đọc hiểu nhưng nó vẫn tuân theo [MudimAPI](MudimAPI.md) và bạn hoàn toàn có thể viết thêm code hiệu chỉnh Mudim ở cuối file mudim.js. Những hàm và thuộc tính được nhắc đến trong bài viết này bạn có thể tham khảo [MudimAPI](MudimAPI.md).

Phiên bản Mudim được dùng phải từ [r58](https://code.google.com/p/mudim/source/detail?r=58) trở đi.

Từ [r133](https://code.google.com/p/mudim/source/detail?r=133), cơ chế tuỳ biến Mudim được cải thiện với 2 hàm Mudim.BeforeInit() và Mudim.AfterInit(). Hàm Mudim.BeforeInit() được gọi **trước** khi kích hoạt Mudim.AfterInit() được gọi **sau** khi kích hoạt. Quy tắc chung khi tuỳ biến là khi gán những hằng số, thuộc tính của Mudim thì nên để trong BeforeInit, còn khi gọi các hàm thì nên để trong AfterInit().

# Nội dung #

### 1. Làm thế nào tuỳ biến giao diện của bảng điều khiển ? ###

Bạn có thể tuỳ biến các thuộc tính sau của giao diện: màu chữ, màu nền, ngôn ngữ hiển thị.
  * **Màu chữ** : quy định bởi Mudim.COLOR, mặc định mang giá trị
```
Mudim.COLOR='Black';
```
bạn có thể thay đổi `Black` thành bất cứ màu hợp lệ nào của HTML, ví dụ `Orange` hoặc `#FFFFAA`.
  * **Màu nền** : quy định bởi PANEL\_BACKGROUND với giá trị mặc định
```
Mudim.PANEL_BACKGROUND='lightYellow';
```
bạn có thể thay đổi theo cách tương tự như màu chữ.
  * **Ngôn ngữ hiển thị** : tên gọi các kiểu gõ và chức năng, nếu không muốn dùng giá trị mặc định bạn hãy thay đổi ở mạng LANG, chú ý đến thứ tự của các từ

```
Mudim.LANG=['Tắt','VNI','Telex','Viqr','Tổng hợp','Chính tả','Bỏ dấu kiểu mới','Bật/Tắt','Ẩn/Hiện bảng điều khiển'];
```

### 2. Nếu tôi không muốn gõ tiếng Việt trên một textbox ? ###

Bạn hãy đặt id của textbox đó vào mảng Mudim.IGNORE\_ID. Ví dụ bạn có textbox

```
<input id='en_text' type='text' name='englishtext'>
<input id='notViet' type='text' name='test'>
```

và bạn không muốn gõ tiếng Việt trong 2 ô này hãy đặt
```
Mudim.IGNORE_ID=['en_text','notViet'];
```

Cách này có thể áp dụng với bất kỳ ô nhập văn bản nào, bao gồm textbox, textarea và iframe .

### 3. Làm thế nào để bảng điều khiển không hiện theo mặc định ? ###

Gán giá trị cho Mudim.showPanel ở cuối file mudim.js. Ví dụ:
```
Mudim.showPanel = false;
```

### 4. Làm thế nào để đặt kiểu gõ mặc định ? ###

Bạn hãy gán giá trị trực tiếp cho biến **Mudim.method** (xem [MudimAPI](MudimAPI.md)). Lưu ý không nên gọi hàm Mudim.SetMethod vì hàm này sẽ lưu lại thiết lập hiện tại vào cookie, có thể không đúng với ý muốn của người dùng.

### 5. Làm thế nào để ẩn hiện bằng bảng điều khiển dùng button hoặc link ###

Bạn hãy đặt hàm xử lý event `onclick="Mudim.TogglePanel()"`. Ví dụ:
```
<input type="button" value="Bật tắt bộ gõ" onclick="Mudim.TogglePanel()">
```
hoặc
```
<a href="#" onclick="Mudim.TogglePanel()">Bật tắt bộ gõ</a>
```

### 6. Nếu tôi muốn tự làm radio button mà không muốn dùng bảng điều khiển ? ###

Bạn sẽ cần bộ 5 radio buttons cho 5 kiểu gõ với hàm xử lý event onclick là **Mudim.SetMethod** tương ứng (xem [MudimAPI](MudimAPI.md)). Ngoài ra cần 1 checkbox cho kiểu bỏ dấu, 1 checkbox cho kiểm tra chính tả. ID của tất cả các thành phần này phải được gán vào hằng số tương ứng của Mudim là **Mudim.DIPSPLAY\_ID**, **Mudim.SPELLCHECK\_ID** và **Mudim.ACCENTRULE\_ID** như ví dụ dưới đây
```
Mudim.DISPLAY_ID=['my-off','my-vni','my-telex','my-viqr','my-auto'];
Mudim.SPELLCHECK_ID='my-checkspell';
Mudim.ACCENTRULE_ID='my-accentrule';

<input id="my-off" onclick="Mudim.SetMethod(0);" type=radio name=my-method>Tắt
<input id="my-vni" onclick="Mudim.SetMethod(1);" type=radio name=my-method>Vni
<input id="my-telex" onclick="Mudim.SetMethod(2);" type=radio name=my-method>Telex 
<input id="my-viqr" onclick="Mudim.SetMethod(3);" type=radio name=my-method>Viqr
<input id="my-auto" onclick="Mudim.SetMethod(4);" type=radio name=my-method>Tự động 
<input id="my-checkspell" onclick="Mudim.ToggleSpeller();" type=checkbox>Kiểm tra chính tả 
<input id="my-accentrule" onclick="Mudim.ToggleAccentRule();" type=checkbox>Bỏ dấu kiểu mới
```

Lưu ý: các giá trị sau đã được sử dụng cho bảng điều khiển, bạn không nên đặt ID trùng với những giá trị này.
```
Mudim.DISPLAY_ID=['mudim-off','mudim-vni','mudim-telex','mudim-viqr','mudim-auto'];
Mudim.SPELLCHECK_ID='mudim-checkspell';
Mudim.ACCENTRULE_ID='mudim-accentrule';
```

### 7. Nếu tôi muốn tự mình sửa source code thì sao ? ###

Bạn hãy vào tab **Source**, browse đến thư mục trunk và lấy về bản Mudim đang phát triển mang tên mudim-dev.js. Bạn có thể tuỳ ý sửa chữa theo ý mình. Tuy nhiên file mudim-dev.js được khuyến cáo không nên dùng trong môi trường production với các lý do:
  * Kích thước file mudim-dev.js to gần gấp 3 lần file mudim.js của phiên bản release.
  * Có rất nhiều dòng lệnh phục vụ cho việc debug trong mudim-dev.js dẫn đến hệ quả performance giảm nghiêm trọng trên những máy dùng firefox có firebug hoặc phải chịu rất nhiều popup trong những trường hợp còn lại. Bạn có thể gán console.debug thành 1 hàm rỗng hoặc tìm xoá tất cả các dòng console.debug trong mudim-dev.js nhưng đấy không phải cách tối ưu.

Giải pháp được khuyến khích là hãy checkout nguyên folder trunk trong đó đã có 2 file python có nhiệm vụ nén mudim-dev.js thành mudim.js trong cùng thư mục bằng lệnh:
```
build.py js
```
File mudim.js nhận được sẽ có kích thước khoảng 19KB.

### 8. Làm thế nào để luôn được dùng Mudim bản mới nhất ? ###

Mục Downloads không phải lúc nào cũng được cập nhật phiên bản mới nhất. Phiên bản này luôn có trong svn theo địa chỉ http://mudim.googlecode.com/svn/trunk/mudim/mudim.js

Đối với bản Firefox extension, bạn có thể tải từ địa chỉ http://mudim.googlecode.com/svn/trunk/mudim-ffx/mudim.xpi

### 9. Tôi muốn tuỳ biến nhiều hơn với Panel, chẳng hạn như kích cỡ font, kiểu font, ... ###
Bạn có thể nhận được style object của panel với hàm Mudim.GetPanelStyle(). Với object này bạn có thể tuỳ ý chỉnh style với cú pháp javascript. Lưu ý, việc diều chỉnh này nên đặt trong hàm Mudim.AfterInit(). Bạn có thể xem phần cuối file mudim.js để có ví dụ rõ ràng hơn:
```
Mudim.AfterInit = function() {
	//s = Mudim.GetPanelStyle();
	//s.fontSize = '14pt';
	//s.fontFamily = 'Serif';
};
```

### 10. Đối với các trang chưa cài sẵn mudim hoặc không có bộ gõ tiếng Việt thì có thể sử dụng mudim được không? ###

**Có!!!**

Bạn hãy lưu dòng này ở đâu đó, để khi cần chỉ cần copy/paste nó vào ô địa chỉ của trình duyệt và bấm Enter. Hoặc tốt nhất hãy lưu nó vào bookmark của trình duyệt như địa chỉ của một trang web. Sau đó bạn sẽ có bộ gõ Mudim giống như nó được cài đặt trên trang web bạn đang xem vậy.

javascript:(function(){var%20s=document.createElement(%22script%22);s.src=%22http://mudim.googlecode.com/svn/trunk/mudim/mudim.js%22;document.body.appendChild(s);})();


_Mẹo này do akia.myopenid.com đóng góp_