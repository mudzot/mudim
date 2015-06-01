# Sơ lược #

Tất cả các hàm, thuộc tính và hằng số trong Mudim đều bắt đầu bằng CHIM. hoặc Mudim. tuy không đúng với bản chất class lắm, giống namespace hơn, cho biết những hàm nào thừa kế từ CHIM. Những mô tả dưới đây áp dụng từ [r58](https://code.google.com/p/mudim/source/detail?r=58) trở đi.


# Chi tiết #

## Các hằng số ##

|Tên|Tác dụng|
|:---|:----------|
| **Mudim.COLOR** |Quy định màu chữ trên bảng điều khiển|
| **Mudim.PANEL\_BACKGROUND** |Quy định màu nền bảng điều khiển|
| **Mudim.LANG** |Mảng chứa các từ mô tả kiểu gõ và chức năng trên bảng điều khiển|
| **Mudim.IGNORE\_ID** |Mảng chứa id của các ô nhập văn bản không có nhu cầu gõ tiếng Việt|

## Các thuộc tính ##

Lưu ý chung: các thuộc tính này quy định cách làm việc của Mudim, và sẽ ảnh hưởng ngay lập tức đến nó nếu được gán trực tiếp giá trị (trừ showPanel). Tuy nhiên khi đó những thiết lập sẽ không được lưu lại. Các thiết lập chỉ được lưu lại khi thuộc tính được thay đổi thông qua các hàm tương ứng.

**Mudim.method**

Quy định kiểu gõ với các giá trị 0(Tắt), 1(Vni), 2(Telex), 3(Viqr), 4(Tổng hợp 3 kiểu). Xem thêm hàm **Mudim.SetMethod**.

**Mudim.oldMethod**

Quy định kiểu gõ gần đây nhất, dùng khi bật/tắt bộ gõ.

**Mudim.newAccentRule**

Lựa chọn bỏ dấu kiểu mới : true hoặc false

**Mudim.showPanel**

Hiện hoặc ẩn bảng điều khiển : true hoặc false

**Mudim.displayMode**

Chế độ hiển thị đầy đủ (0) hoặc thu gọn (1)

## Các hàm ##

### Các hàm thay đổi kiểu gõ ###

**Mudim.SetMethod(m)**

Chọn kiểu gõ
  * m : kiểu gõ, nhận giá trị 0-4.
Hàm SetMethod làm 2 việc, thứ nhất là đặt lại giá trị cho Mudim.method, thứ hai là đặt lại giá trị cookie lưu thiết lập người dùng. Vì vậy nếu bạn thay đổi kiểu gõ không phải do người dùng làm (ví dụ như đặt kiểu gõ mặc định chẳng hạn), thì bạn nên dùng phương pháp gán giá trị trực tiếp cho **Mudim.method** chứ không nên gọi hàm này.

**Mudim.SwitchMethod()**

Thay đổi kiểu gõ theo hướng tăng dần và vòng tròn

**Mudim.Toggle()**

Bật tắt bộ gõ, đảo giá trị của Mudim.method và Mudim.oldMethod. Lưu ý rằng hàm này có đặt lại giá trị cookie. Xem thêm **Mudim.SetMethod**.

### Các hàm thay đổi kiểm tra chính tả và kiểu bỏ dấu ###

**Mudim.ToggleSpeller()**

Bật tắt chế độ kiểm tra chính tả.Lưu ý rằng hàm này có đặt lại giá trị cookie

**Mudim.ToggleAccentRule()**

Bật tắt chế độ bỏ dấu kiểu mới.Lưu ý rằng hàm này có đặt lại giá trị cookie

### Các hàm quản lý thuộc tính ###

**Mudim.SetPreference()**

Lưu các thuộc tính vào cookie

**Mudim.GetPreference()**

Lấy giá trị các thuộc tính từ cookie

### Các hàm liên quan đến bảng điều khiển ###

**Mudim.TogglePanel()**

Ẩn/Hiện bảng điều khiển.Lưu ý rằng hàm này có đặt lại giá trị cookie

**Mudim.ShowPanel()**

Hiện bảng điều khiển. Lưu ý rằng hàm này **không** đặt lại giá trị cookie

**Mudim.HidePanel()**

Ẩn bảng điều khiển. Lưu ý rằng hàm này **không** đặt lại giá trị cookie

**Mudim.GetPanelStyle()**

Trả về style của Panel như một javascript object. Dùng khi bạn muốn tuỳ biến các thuộc tính panel nhiều hơn những giá trị đã được hỗ trợ sẵn.

### Các hàm liên quan đến việc tìm và gắn bộ gõ vào các ô nhập văn bản ###

**CHIM.Activate**

**CHIM.Attach**

**CHIM.MouseDown**

**CHIM.KeyDown**

**CHIM.KeyHandler**

### Các hàm quyết định hoạt động của bộ gõ ###

**CHIM.AddKey**

Tiếp nhận 1 ký tự từ bàn phím để xử lý

**Mudim.FindAccentPos**

Tìm vị trí bỏ dấu dựa trên nội dung hiện tại của buffer và ký tự tiếp theo

**Mudim.PutMark**

Bỏ dấu phù hợp với ký tự cần bỏ dấu và bảng mã

**CHIM.Append**

Thêm ký tự vào buffer và kiểm tra chính tả nếu cần

**Mudim.AdjustAccent**

Điều chỉnh vị trí dấu nếu cần thiết

**Mudim.UpdateUI**

Cập nhật nội dung buffer vào ô văn bản

### Các hàm dùng để tuỳ biến Mudim ###

**Mudim.BeforeInit()**

Hàm này sẽ được gọi ngay trước khi kích hoạt bộ gõ. Nội dung của nó sẽ do web developer viết thêm, chủ yếu để gán các hằng số, thuộc tính mặc định cho bộ gõ.

**Mudim.AfterInit()**

Hàm này sẽ được gọi sau trước khi kích hoạt bộ gõ. Nội dung của nó sẽ do web developer viết thêm, chủ yếu để gọi các hàm và điều chỉnh các đối tượng liên quan đến bộ gõ.