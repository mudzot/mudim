Các phiên bản test : Mudim 0.6-[r64](https://code.google.com/p/mudim/source/detail?r=64), Avim 20071102, CHIM 0.9.3, BIM 0.0.3

Bảng so sánh này hiện nay không cập nhật và không đầy đủ, hãy xem bảng so sánh đầy đủ hơn tại đây http://www.1ec5.org/software/avim/compare.html

| |Mudim|AVIM|CHIM|BIM|mViet|
|:|:----|:---|:---|:--|:----|
|Kích thước khi sử dụng|19KB |28KB|29KB|35KB|29.5KB|
|Tích hợp sẵn bảng điều khiển|+    |-   |-   |+  |-    |
|Kiểu bỏ dấu|mới/cũ|cũ/mới|mới|mới|cũ  |
|3 kiểu gõ VNI, Telex, Viqr|+    |+   |+   |+  |+    |
|Kiểu gõ tổng hợp cả 3|+    |+   |-   |-  |+    |
|Tự nhận dạng lỗi chính tả|+ -  |+ - |+ - |+ -|+ -  |
|Bỏ dấu ở cuối từ|+    |+   |+ - |+ -|+ -  |
|Tự chuyển vị trí bỏ dấu|+    |+   |-   |-  |+    |
|Hỗ trợ [tinymce](http://tinymce.moxiecode.com/) và [fckeditor](http://www.fckeditor.net/)|+    |+   |+   |+  |+    |
|Tự động nhận các ô nhập văn bản|+    |+ - |+ - |+ -|+ -  |
|Hỗ trợ nhiều loại trình duyệt web|+    |+   |+   |+  |+    |
|Bản Firefox extension| | | | | |
|Tính tương thích với các trang web|Tốt|Tốt |Vừa phải |x  |x    |
|Xung đột với bộ gõ trong trang web|Không|Có |Không|x  |x    |

Chi tiết về ưu điểm của Mudim so với các bộ gõ khác (Avim và mViet):
  * Với Mudim bạn không cần làm gì khác ngoài việc thêm 1 dòng include bộ gõ vì bảng điều khiển đã có sẵn
  * Khả năng tự động nhận các ô nhập văn bản rất cao
    * Với các bộ gõ khác khi trang web có dùng fckeditor bạn phải chèn dòng include bộ gõ vào cả trang _fckeditor.original.html_. Tổng quát hơn, Avim và mViet không _tự động_ được nếu bạn cần gõ tiếng Việt trong 1 iframe mà iframe này lại nằm trong 1 iframe khác. (1)
    * Tình hình tương tự nếu trang của bạn là trang 

&lt;frameset&gt;

 chứa các 

&lt;frame&gt;

, bạn cũng phải chèn dòng include bộ gõ vào các trang chứa trong tag 

&lt;frame&gt;


    * Với Mudim bạn chỉ cần chèn vào trang chính là đủ.
  * Khả năng bỏ dấu ở cuối từ và tự chuyển vị trí bỏ dấu rất tốt
    * mViet không thể bỏ dấu móc hoặc dấu mũ ở cuối từ (với Mudim, bạn gõ có thể gõ chữ "hơn" bằng cách gõ "hown", mViet thì không)
    * Avim có thể bỏ dấu mũ và móc ở cuối từ nhưng không tự chuyển dấu móc (gõ "luwfoi với Avim được "lừoi", với Mudim được "lười")
  * Khả năng tắt tạm thời bộ gõ và kiểm tra chính tả đối với 1 từ sắp gõ. Bạn có thể dùng Ctrl để tạm thời tắt chức năng kiểm tả chính tả đối với từ đang/sắp gõ, sẽ rất có ích khi bạn gõ những từ không thuộc hệ thống tiếng Việt chuẩn hoặc các từ phiên âm tiếng nước ngoài, ví dụ như alô (gõ {Ctrl}aloo) hay Lagrăng (gõ Lagr{Ctrl}awng). Tương tự như vậy, phím Shift dùng để tạm thời tắt bộ gõ với từ sắp gõ. Chi tiết hơn xem tại trang [HuongDanSuDung](HuongDanSuDung.md)

(1) Bản Firefox extension mới của Avim đã loại bỏ nhược điểm này