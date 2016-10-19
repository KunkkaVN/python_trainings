<a name="phan1"></a>
##1. Sử dụng python như một máy tính:
-------------------------------------
Việc python là một trình thông dịch nên có thể thực hiện chức năng tính toán như một máy tính thông thường
Ví dụ: `2*2` sẽ hiển thị ra `4` hay các biểu thức phức tạp như `(9-10)*2+2`
<img src="http://i.imgur.com/08wS71E.jpg">

<a name="phan2"></a>
##2. Tìm hiểu về kiểu dữ liệu number.
-------------------------------------
Kiểu dữ liệu Number lưu trữ các giá trị số. Chúng là các kiểu dữ liệu immutable, hay là kiểu dữ liệu không thay đổi, nghĩa là các thay đổi về giá trị của kiểu dữ liệu số này sẽ tạo ra một đối tượng được cấp phát mới.

Các đối tượng Number được tạo khi bạn gán một giá trị cho chúng. Ví dụ:
``number1=1
number2=100``
Bạn cũng có thể xóa tham chiếu tới một đối tượng Number bởi sử dụng lệnh `del`. Ví dụ `del number1`

Python hỗ trợ 4 kiểu dữ liệu số, đó là:

- Kiểu int: kiểu số nguyên không có dấu thập phân.

- Kiểu long: là các số nguyên không giới hạn kích cỡ, được theo sau bởi một chữ l hoặc chữ L.

- Kiểu float: số thực với dấu thập phân. Kiểu này cũng có thể được viết ở dạng số mũ của 10 với E hoặc e như (2.5e2 = 2.5 x 102 = 250).

- Kiểu số phức: là trong dạng a + bJ, với a và b là số thực và J (hoặc j) biểu diễn căn bậc hai của -1. Phần thực là a và phần ảo là b. Nói chung, số phức không được sử dụng nhiều trong lập trình Python.
**Chuyển đổi kiểu số trong python**
Python chuyển đổi các số một cách nội tại bên trong một biểu thức chứa các kiểu phức tạp thành một kiểu chung để ước lượng. Tuy nhiên có đôi khi bạn cần chuyển đổi tường minh một số từ kiểu này sang kiểu khác để thỏa mãn yêu cầu của một toán tử hoặc một hàm.
- Để chuyển đổi số x thành số thuần nguyên, bạn gõ int(x).

- Để chuyển đổi số x thành số long, bạn gõ `long(x)`.

- Để chuyển đổi số x thành số thực, bạn gõ `float(x)`.

- Để chuyển đổi số x thành số phức với phần thực là x và phần ảo là 0, bạn gõ `complex(x)`.

- Để chuyển đổi số x và y thành số phức với phần thực là x và phần ảo là y, bạn gõ `complex(x, y)`.
**Một số hàm toán học trong python**

|Hàm|Miêu tả|
|---|-------|
|Hàm abs(x)|Trị tuyệt đối của x|
|Hàm ceil(x)|Số nguyên nhỏ nhất mà không nhỏ hơn x|
|Hàm cmp(x, y)|Trả về -1 nếu x < y, trả về 0 nếu x == y, hoặc 1 nếu x > y|
|Hàm exp(x)|Trả về ex|
|Hàm fabs(x)|Giá trị tuyệt đối của x|
|Hàm floor(x)|Số nguyên lớn nhất mà không lớn hơn x|
|Hàm log(x)|Trả về lnx, với x> 0|
|Hàm log10(x)|Trả về log10(x), với x> 0 .|
|Hàm max(x1, x2,...)|Trả về số lớn nhất|
|Hàm min(x1, x2,...)|Trả về số nhỏ nhất|
|Hàm modf(x)|
|Trả về phần nguyên và phần thập phân của x. Cả hai phần có cùng dấu với x và phần nguyên được trả về dưới dạng một số thực|
|Hàm pow(x, y)||Trả về giá trị của x**y.|
|Hàm round(x [,n])|Làm tròn x về n chữ số sau dấu thập phân. Python làm tròn theo cách sau: round(0.5) là 1.0 và round(-0.5) là -1.0|
|Hàm sqrt(x)|Trả về căn bậc hai của x, với x > 0|

- Kiểu dữ liệu number trong python khác với C ở đặc điểm nó tự trả về kiểu giá trị đúng sau phép tính, như khi chia 2 số nguyên int thì trong python sẽ tự động gán kết quả là float còn C thì không