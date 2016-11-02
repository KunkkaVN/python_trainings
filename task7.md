<a name="phan1"></a>
##1. Ý tưởng giải challenge-lv3:
--------------------------------

Đầu tiên ta thử xen source của trang wed thì thấy được cho 1 đoạn code `<!--.....-->` như trong challenge trước nhưng lúc này toàn là ký tự hoa và thường chứ không phải là số

Lúc này ta để ý đến gợi ý của challenge `One small letter, surrounded by EXACTLY three big bodyguards on each of its sides` , hiểu nôm na là 1 chũ thường bị bao quanh bởi 3 chữ in hoa

Vậy để giải bài này chúng ta cần lấy được những chữ thường thõa mãn xung quanh nó có đúng 3 chữ in hoa.

<a name="phan2"></a>
##2. Các bước thực hiện:
------------------------

Đầu tiên chúng ta phải lấy source của trang wed về, sau đó bỏ những phần không cần thiết đi chỉ lấy phần bắt từ <!-- đến -->

Sau khi cắt xong thì mình lưu nó vào 1 file tên là task7.txt để thuận tiện cho phần lấy chữ hoặc tùy bạn có thể làm luôn

```sh
import requests

source = requests.get('http://www.pythonchallenge.com/pc/def/equality.html') #dùng thư viện requests đê lất source

line = source.text

a=line.index('**<!--**')

b=line.index('**-->**')

line2= line[a:b] #cắt source từ vị trí có kí tự **<!--** đến vị trí có kí tuwh **-->**

f = open('task7.txt','w') #tạo file sau đó viết vào file

f.write(line2)

f.close()```

Lúc này ta đã có file task7.txt chứa đoạn code cần xử lý. Ta sẽ sử dụng thư viện re-xử lý chuỗi nâng cao để lọc lấy những chữ cái này

```sh
import re

f = open('task7.txt','r')

line = f.read()

line2 = re.findall("[^A-Z]+[A-Z]{3}([a-z])[A-Z]{3}[^A-Z]+",line) #sử dụng thư viện re, kết nối tới chữ thõa [^A-Z] là từ không phải A-Z + 3 lần xuất hiện [A-Z] đặt kết nỗi tại [a-z] và phía sau cũng thõa mãn tính chất 3 hoa, 1 thường

print line2```

Code chương trình:

http://codepad.org/ewtXnChn

<img src="http://i.imgur.com/MBz6NPJ.jpg">

Kết quả challenge : `linkedlist`

<a name="phan3"></a>
##3. Dịch bài:re module
-----------------------

re — Regular expression operations (Khớp mẫu chuỗi)

Chuỗi nguyên Python cho các mẫu biểu thức chính quy; backslashes không được xử lý trong bất kỳ cách đặc biệt trong một chuỗi chữ bắt đầu bằng 'r'. Vì vậy, r "\ n" là một chuỗi hai ký tự có chứa '\' và 'n', trong khi "\ n" là một chuỗi một nhân vật có chứa một dòng mới.

Một biểu thức chính quy (hoặc RE) quy định cụ thể một chuỗi; mà các chức năng trong module này cho phép bạn kiểm tra xem một chuỗi cụ thể phù hợp với biểu thức quy định (hoặc có thể là nột chuỗi mà có các đặc điểm đã được miêu tả giống như biểu thức quy định).

Biểu thức quy định có thể được nối để tạo thành biểu thức quy định mới - tức là có thể kết hợp nhiều biểu thức quy định thành biểu thức quy định mới. Ví dụ như A,B là 2 biểu thức quy định để kiểm tra chuỗi thì AB cũng là biểu thức quy định

Biểu thức quy định có thể chứa các ký tự như in hoa, thường, số là cụ thể và đơn giản nhất hoặc có thể sử dụng các từ điều khiển như  (+ ? . * ^ $ ( ) [ ] { } | \)

Vòng lặp (*, +,?, {m, n}, vv) không thể được lồng trực tiếp mà chúng được sử dụng thông qua biểu thức trước đó

|Pattern|Miêu tả|
|-------|-------|
|$	|Kết nối với phần cuối của dòng|
|.	|Kết nối bất kỳ ký tự đơn nào ngoại trừ newline (dòng mới). Sử dụng tùy chọn m cho phép nó kết nối với newline (dòng mới)|
|*  |các RE kết quả phù hợp với 0 hoặc nhiều lần lặp lại của RE trước,. ab * sẽ phù hợp với 'a', 'ab', hay 'a' theo sau bởi bất kỳ số lượng 'b'|
|+ 	|các RE kết quả phù hợp với 1 hoặc nhiều lần lặp lại của RE trước. ab + sẽ phù hợp 'a' theo sau bởi số 'b',sẽ không phù hợp chỉ có 'a'|
|[...]	|Kết nối với bất kỳ ký tự đơn nào trong []|
|[^...]	|Kết nối với bất kỳ ký tự đơn nào không ở trong []|
|?	|Kết nối với 0 hoặc 1 sự xuất hiện của biểu thức đặt trước|
|{ n}	|Kết nối với n sự xuất hiện của biểu thức đặt trước|
|{ n,}	|Kết nối với n hoặc nhiều hơn sự xuất hiện của biểu thức đặt trước|
|{ n, m}	|Kết nối với ít nhất n và nhiều nhất m sự xuất hiện của biểu thức đặt trước|
|a | b	|Kết nối với a hoặc b|
|(re)|	Nhóm các Regular Expression và ghi nhớ text đã kết nối|
|(?imx)|	|Bật toggle tạm tời các tùy chọn i, m hoặc x bên trong một Regular Expression. Nếu trong cặp dấu ngoặc đơn thì chỉ khu vực đó bị ảnh hưởng|
|(?-imx)	|Tắt toggle tạm tời các tùy chọn i, m hoặc x bên trong một Regular Expression. Nếu trong cặp dấu ngoặc đơn thì chỉ khu vực đó bị ảnh hưởng|
|(?: ...)	|Nhóm các Regular Expression mà không ghi nhớ text đã kết nối|
|(?imx:...)	|Bật toggle tạm thời các tùy chọn i, m, hoặc x bên trong cặp dấu ngoặc đơn|
|(?-imx:...)	|Tắt toggle tạm thời các tùy chọn i, m, hoặc x bên trong cặp dấu ngoặc đơn|
|(?#...)	|Comment|
|(?=...)	|Xác định vị trí bởi sử dụng một pattern. Không có một dãy giá trị|
|(?!...)	|Xác định vị trí bởi sử dụng sự phủ định pattern. Không có một dãy giá trị|
|(?>...)	|Kết nối pattern độc lập mà không backtrack|
|\w	|Kết nối các ký tự từ|
|\W	|Kết nối các ký tự không phải là từ|
|\s|Kết nối với whitespace. Tương đương với [\t\n\r\f]|
|\S	|ết nối với các ký tự không là whitespace|
|\d	|Kết nối với các chữ số. Tương đương với [0-9]|
|\D	|Kết nối với các ký tự không là chữ số|
|\A	|Kết nối với phần đầu của chuỗi|
|\Z	|Kết nối với phần cuối của chuỗi. Nếu một newline (dòng mới) tồn tại, nó kết nối với phần ở trước newline (dòng mới)|
|\z	|Kết nối với phần cuối của chuỗi|
|\G	|Kết nối với điểm mà tại đó kết nối cuối cùng được tìm thấy|
|\b	|Kết nối với các giới hạn từ khi bên ngoài các dấu []. Kết nối với backspace (mã là 0x08) khi bên trong các dấu []|
|\B	|Kết nối với các giới hạn không phải là từ|
|\n, \t, etc.	|Kết nối với newline (dòng mới), carriage return, tab, ...|
|\1...\9	Kết nối với biểu thức con được nhóm thứ n|
|\10	Kết nối biểu thức con được nhóm thứ n nếu nó đã kết nối. Nếu không, tham chiếu tới biểu diễn bát phân của một mã ký tự|

**Các hàm trong module**

- re.compile(pattern, flags=0) : Biên dịch một biểu thức mà thông qua nó để tìm chuỗi có đặc điểm cần tìm

- re.search(pattern, string, flags=0) : tìm kiếm cho sự xuất hiện đầu tiên của pattern bên trong string với các flags tùy ý

- re.match(pattern, string, flags=0) : Hàm này cố gắng so khớp pattern với string với các flag tùy ý

- re.split(pattern, string, maxsplit=0, flags=0) : cắt chuỗi string với các đặc điểm pattern

- re.findall(pattern, string, flags=0) : Trả lại tất cả các chuỗi thõa mãn pattern không trùng lặp mẫu trong chuỗi thành một danh sách các chuỗi. Chuỗi string được quét từ trái sang phải, và chuỗi thõa pattern trả về theo thứ tự được tìm thấy

- re.sub(pattern, repl, string, max, flags=0) : Phương thức này thay thế tất cả sự xuất hiện của pattern trong string với repl. Phương thức này sẽ thay thế tất cả sự xuất hiện trừ khi bạn cung cấp tham số max. Phương thức này trả về chuỗi đã được sửa đổi