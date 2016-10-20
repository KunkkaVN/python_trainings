#Mục lục
[**1.Sử dụng python như một máy tính**](#phan1)

[**2.Tìm hiểu về kiểu dữ liệu Number**](#phan2)

[**3.Tìm hiểu về kiểu dữ liệu String**](#phan3)

[**4.Tìm hiểu về List**](#phan4)

[**5.Tìm hiểu về kiểu Boolean**](#phan5)

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
|Hàm modf(x)||Trả về phần nguyên và phần thập phân của x. Cả hai phần có cùng dấu với x và phần nguyên được trả về dưới dạng một số thực|
|Hàm pow(x, y)||Trả về giá trị của x**y.|
|Hàm round(x [,n])|Làm tròn x về n chữ số sau dấu thập phân. Python làm tròn theo cách sau: round(0.5) là 1.0 và round(-0.5) là -1.0|
|Hàm sqrt(x)|Trả về căn bậc hai của x, với x > 0|

- Kiểu dữ liệu number trong python khác với C ở đặc điểm nó tự trả về kiểu giá trị đúng sau phép tính, như khi chia 2 số nguyên int thì trong python sẽ tự động gán kết quả là float còn C thì không

<a name="phan3"></a>
##3. Tìm hiểu về kiểu dữ liệu String.
-------------------------------------
String là một trong các kiểu phổ biến nhất trong Python. String trong Python là immutable. Chúng ta có thể tạo các chuỗi bằng cách bao một text trong một trích dẫn đơn hoặc trích dẫn kép. Python coi các lệnh trích dẫn đơn và kép là như nhau. Ví dụ: `name1="Dinh Tan Thien"`
**Truy cập các giá trị trong String**
Python không hỗ trợ một kiểu chữ cái; chúng được coi như các chuỗi có độ dài là 1. Trong Python, String được lưu giữ dưới dạng các ký tự đơn trong vị trí ô nhớ liên tiếp nhau. Lợi thế của sử dụng String là nó có thể được truy cập từ cả hai hướng
Việc lập chỉ mục của cả hai hướng đều được cung cấp bởi sử dụng String trong Python:
- Chỉ mục với hướng forward bắt đầu với 0,1,2,3,…
- Chỉ mục với hướng backward bắt đầu với -1,-2,-3,…

Để truy cập các giá trị trong String, bạn sử dụng các dấu ngoặc vuông có chỉ mục ở bên trong. Ví dụ:
``var1 = 'Hello World!'
var2 = "Python Programming"

print "var1[0]: ", var1[0]
print "var2[1:5]: ", var2[1:5]``

Khi code trên được thực thi sẽ cho kết quả:

``var1[0]:  H
var2[1:5]:  ytho``

**Các toán tử cơ bản để thao tác với String**

- Toán tử nối chuỗi + được sử dụng để nối hai chuỗi với nhau và tạo nên một chuỗi mới. Ví dụ: `"Tan "+"Thien"` kết quả `'Tan Thien'`
*Cả hai toán hạng được truyền cho phép nối chuỗi này phải cùng kiểu, nếu không sẽ tạo một lỗi
- Toán tử lặp chuỗi * sử dụng hai tham số. Một tham số là giá trị nguyên và tham số khác là chuỗi. Toán tử lặp chuỗi này được sử dụng để lặp đi lặp lại một chuỗi một số lần nào đó

**Các toán tử membership để thao tác với String**

- Toán tử in: trả về true nếu một ký tự là có mặt trong chuỗi đã cho, nếu không nó trả về false.
- Toán tử not in: trả về true nếu một ký tự là không tồn tại trong chuỗi đã cho, nếu không nó trả về false.
``>>> str1="javapoint"
>>> str2='sssit'
>>> str3="seomount"
>>> str4='java'
>>> st5="it"
>>> str6="seo"
>>> str4 in str1
True
>>> str5 in str2
>>> st5 in str2
True
>>> str6 in str3
True
>>> str4 not in str1
False
>>> str1 not in str4
True``

**Các toán tử quan hệ để thao tác với String**

Tất cả các toán tử quan hệ (như <,>, <=, >=, ==, !=, <>) cũng có thể áp dụng cho các String. Các chuỗi được so sánh dựa trên giá trị ASCII hoặc Unicode.

**Dấu chia chuỗi [] trong Python**

Có nhiều cách để chia một chuỗi. Khi chuỗi có thể được truy cập hoặc được lập chỉ mục từ cả hai hướng forward và backward thì chuỗi cũng có thể được chia theo hai hướng này. Dưới đây là cú pháp của dấu chia chuỗi [] trong Python:
``<ten_chuoi>[chi_muc_bat_dau:chi_muc_ket_thuc]
hoac
<ten_chuoi>[:chi_muc_ket_thuc]
hoac
<ten_chuoi>[chi_muc_bat_dau:]``

**Toán tử định dạng chuỗi trong Python**

Một trong những đặc điểm hay nhất trong Python là toán tử định dạng chuỗi %. Toán tử này là duy nhất cho các String và được sử dụng với hàm print(). Ví dụ:
`print "Ten toi la %s va toi nang %d kg!" % ('Xanh', 60) `
Khi code trên được thực thi sẽ cho kết quả:
`Ten toi la Xanh va toi nang 60 kg!`

Bảng dưới đây liệt kê danh sách đầy đủ các biểu tượng có thể được sử dụng với toán tử %:

|Biểu tượng định dạng|Chuyển đổi|
|--------------------|----------|
|%c|Ký tự|
|%s|Chuyển đổi thành chuỗi thông qua hàm str() trước khi định dạng|
|%i|Số nguyên thập phân có dấu|
|%d|Số nguyên thập phân có dấu|
|%u|Số nguyên thập phân không dấu|
|%o|Số nguyên hệ bát phân|
|%x|Số nguyên hệ thập lục phân (các chữ cái thường)|
|%e|Ký hiệu số mũ (với chữ thường 'e')|
|%E|Ký hiệu số mũ (với chữ hoa 'E')|
|%f|Số thực dấu chấm động|
|%g|Viết gọn của %f và %e|
|%G|Viết gọn của %f và %E|

<a name="phan4"></a>
##4. Tìm hiểu List
------------------
List trong Python là cấu trúc dữ liệu mà có khả năng lưu giữ các kiểu dữ liệu khác nhau.

List trong Python là thay đổi (mutable), nghĩa là Python sẽ không tạo một List mới nếu bạn sửa đổi một phần tử trong List.

List là một container mà giữ các đối tượng khác nhau trong một thứ tự đã cho. Các hoạt động khác nhau như chèn hoặc xóa có thể được thực hiện trên List.

Một List có thể được tạo ra bởi lưu trữ một dãy các kiểu giá trị khác nhau được phân biệt bởi các dấu phảy. Dưới đây là cú pháp để tạo List:
`<ten_list>=[giatri1, giatri2, ..., giatriN];`

Ví dụ:
``list1 = ['vatly', 'hoahoc', 1997, 2000];
list2 = [1, 2, 3, 4, 5 ];
list3 = ["a", "b", "c", "d"];``

- Để truy cập các giá trị trong List, bạn sử dụng cú pháp sau: `<ten_list>[index]`

Bạn có thể thực hiện các hoạt động nối với toán tử + hoặc hoạt động lặp với * như trong các chuỗi. Điểm khác biệt là ở đây nó tạo một List mới, không phải là một chuỗi.

**Cập nhật List trong Python**

- Bạn có thể cập nhật một hoặc nhiều phần tử của List bởi gán giá trị cho chỉ mục cụ thể đó. Cú pháp: 
`<ten_list>[index]=<giatri>`

Ví dụ:
``list = ['vatly', 'hoahoc', 1997, 2000];
print "Gia tri co san tai chi muc thu 2 : "
print list[2]
list[2] = 2001;
print "Gia tri moi tai chi muc thu 2 : "
print list[2]``
Khi code trên được thực thi sẽ cho kết quả:
``Gia tri co san tai chi muc thu 2 :
1997
Gia tri moi tai chi muc thu 2 :
2001``

- Phương thức append() được sử dụng để phụ thêm phần tử vào cuối một List. Cú pháp: `<ten_list>.append(item)`

- Để xóa một phần tử trong List, bạn có thể sử dụng lệnh del nếu bạn biết chính xác phần tử nào bạn muốn xóa hoặc sử dụng phương thức remove() nếu bạn không biết. 

**Các hàm và phương thức đã xây dựng sẵn để xử lý List trong Python**

|STT|Hàm và Miêu tả|
|---|--------------|
|1|Hàm cmp(list1, list2)

So sánh các phần tử trong cả hai list|
|2|	Hàm len(list)

Trả về độ dài của list|
|3|	Hàm max(list)

Trả về phần tử có giá trị lớn nhất trong list|
|4|	Hàm min(list)

Trả về phần tử có giá trị nhỏ nhất trong list|
|5|	Hàm list(seq)

Chuyển đổi một tuple thành list|

|STT|Phương thức và Miêu tả|
|---|----------------------|
|1|Phương thức list.append(obj)

Phụ thêm đối tượng obj vào cuối list|
|2|Phương thức list.count(obj)

Đếm xem có bao nhiêu lần mà obj xuất hiện trong list|
|3|Phương thức list.extend(seq)

Phụ thêm các nội dung của seq vào cuối list|
|4|Phương thức list.index(obj)

Trả về chỉ mục thấp nhất trong list mà tại đó obj xuất hiện|
|5|Phương thức list.insert(index, obj)

Chèn đối tượng obj vào trong list tại index đã cho|
|6|Phương thức list.pop(obj=list[-1])

Xóa và trả về phần tử cuối cùng hoặc đối tượng obj có chỉ mục đã cung cấp từ list đã cho|
|7|Phương thức list.remove(obj)

Xóa đối tượng obj từ list|
|8|Phương thức list.reverse()

Đảo ngược thứ tự các đối tượng trong list|
|9|Phương thức list.sort([func])

Sắp xếp các đối tượng của list, sử dụng hàm so sánh nếu được cung cấp|

<a name="phan5"></a>
##5. Tìm hiểu Boolean
---------------------
 là kiểu giá trị này chỉ có hai giá trị là đúng (**True**) và sai (**False**)

 Cú pháp: `bool()`
 Dùng để chuyển 1 kiểu dữ liệu khác về kiểu boolean
 Ngoài ra, còn có thể biểu diễn bằng các toán tử quan hệ như
 `` x != y               # x không bằng y
      x > y                # x lớn hơn y
      x < y                # x nhỏ hơn y
      x >= y               # x lớn hơn hoặc bằng y
      x <= y               # x nhỏ hơn hoặc bằng y
      x==y``
