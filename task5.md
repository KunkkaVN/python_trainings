<a name="phan1"></a>
##1. Tìm hiểu về các lệnh if else, for else, while:
---------------------------------------------------
###1.1 Lệnh if...elif...else trong Python

Lệnh if trong Python là giống như trong ngôn ngữ C. Lệnh này được sử dụng để kiểm tra một điều kiện, nếu điều kiện là true thì lệnh của khối if sẽ được thực thi, nếu không nó sẽ thực hiện khối lệnh của khối else.

Cú pháp của lệnh if...else là:

``if bieu_thuc:
   cac_lenh
else:
   cac_lenh``

Ví dụ minh họa:

<img src="http://i.imgur.com/kI0CfUf.jpg">

**Lệnh elif trong Python**

Giống như lệnh if....else if...else trong python thì thay bằng `if....elif....else` , nếu điều kiện nào đúng sẽ thực thi khối lệnh của elif đó.

Cú pháp của lệnh elif là:

``if bieu_thuc1:
   cac_lenh
elif bieu_thuc2:
   cac_lenh
elif bieu_thuc3:
   cac_lenh
else:
   cac_lenh``

Chú ý:

- không giới hạn lệnh elif 

- Python không cung cấp các lệnh switch hoặc case như trong các ngôn ngữ lập trình khác, tuy nhiên bạn có thể sử dụng các lệnh if…elif để thực hiện vai trò như của switch hoặc case như trong ví dụ trên.

ví dụ:

<img src="http://i.imgur.com/87pIz1p.jpg">

###1.2 Vòng lặp for trong Python

Vòng lặp for được sử dụng để lặp một biến qua một dãy (List hoặc String) theo thứ tự mà chúng xuất hiện. Sau đây là cú pháp của vòng lặp for:

``**for** bien_vong_lap **in** day_sequense:
   cac_lenh``

Nếu một dãy day_sequense gồm một danh sách các biểu thức, nó được ước lượng đầu tiên. Sau đó, item đầu tiên trong dãy được gán cho biến vòng lặp bien_vong_lap. Tiếp theo, các khối lệnh cac_lenh được thực thi và khối lệnh này được thực thi tới khi dãy này đã được lặp xong.

Dưới đây là ví dụ minh họa vòng lặp for trong Python:

``for letter in 'Python':     # Vi du dau tien
   print ("Chu cai hien tai :", letter)

for num in range(1,5): #vong lặp với num =1 sau đó tăng dần lên 5 rồi dừng
	print(num)``

<img src="http://i.imgur.com/Qc5I6E3.jpg">

**Sử dụng lệnh else với vòng lặp for trong Python**

Python cho phép bạn có một lệnh else để liên hợp với một lệnh vòng lặp. Với vòng lặp for, lệnh else được thực thi khi vòng lặp đã lặp qua hết các phần tử trong list.

Ví dụ sau minh họa sự kết hợp của một lệnh else với một lệnh for để tìm kiếm các số nguyên tố từ 10 tới 20.

``
for i in range(10,20):
   for j in range(2,i): #vòng lặ từ 2 tới i
      if i%j == 0:      #kiểm tra xem i có chia hết cho số nào từ 2 tới i không
         break #thoát khỏi vòng lặp nếu xảy ra 1 trường hợp
   else:                  # lệnh trong phần else sẽ được thực hiện nếu vòng for được chạy hết mà không bị break ra
      print (i, "la so nguyen to")``

<img src="http://i.imgur.com/xw8hpZl.jpg">

###1.3 Vòng lặp while trong Python

Vòng lặp while trong Python thực thi lặp đi lặp lại các lệnh hoặc phần thân của vòng lặp miễn là điều kiện đã cho là true. Khi điều kiện là false, thì điều khiển sẽ thoát ra khỏi vòng lặp. Dưới đây là cú pháp của vòng lặp while trong Python:

``**while** bieu_thuc:
   cac_lenh``

Ở đây, cac_lenh có thể là một lệnh đơn hoặc một khối lệnh. Bieu_thuc có thể là bất kỳ biểu thức nào. Điều đáng chú ý về vòng lặp while là vòng lặp này có thể không chạy. Bởi vì khi điều kiện được kiểm tra là false, thì phần thân vòng lặp sẽ bị bỏ qua và lệnh đầu tiên ngay sau vòng lặp sẽ được thực thi.

Ví dụ: 

<img src="http://i.imgur.com/1WyYvQs.jpg">

- Một vòng lặp vô hạn là vòng lặp mà điều kiện của nó là luôn true. Bạn phải đặc biệt chú ý khi sử dụng các vòng lặp while bởi vì tồn tại khả năng là điều kiện của nó sẽ không bao giờ false, tức là làm cho vòng lặp không bao giờ kết thúc.

**Sử dụng lệnh else với vòng lặp while trong Python**

Python cho phép bạn có một lệnh else được sử dụng kết hợp với một lệnh vòng lặp. Khi else được sử dụng với một vòng lặp while, thì lệnh else được thực thi khi điều kiện là false.

<a name="phan2"></a>
##2. Tìm hiểu về một số lệnh như range(), break, continue, pass:
----------------------------------------------------------------

###2.1. Lệnh ranage()

Cú pháp:

``range([start], stop[, step])``

Lệnh range sẽ tạo ra một mãng số bắt đầu từ 0 đến stop. Ví dụ: `range(3) == [0,1,2]`

Start: bắt đầu ở số này
Step: bước nhảy 

Ví dụ: 

``>>> for i in range(5):

...     print(i)

... 

0

1

2

3

4

>>> 

>>> for i in range(3, 6):

...     print(i)

... 

3

4

5

>>> 

>>> for i in range(4, 10, 2):

...     print(i)

... 

4

6

8

>>> 

>>> for i in range(0, -10, -2):

...     print(i)

... 

0

-2

-4

-6

-8``

###2.2. Lệnh break

Cú pháp của lệnh break là khá đơn giản:`break`

Tương tự bên C, lệnh break dùng để thoát khỏi vòng lặp for hay while hiện tại mà không làm ảnh hưởng đến các vòng lặp trước nếu có (các vòng lặp lồng nhau)

Ví dụ:

``>>>for letter in 'Python':  

...   if letter == 'h':

...      break

...   print 'Chu cai hien tai :', letter

...
Chu cai hien tai : P

Chu cai hien tai : y

Chu cai hien tai : t

>>>``

###2.3. Lệnh continue

Lệnh continue trả về điều khiển tới phần ban đầu của vòng lặp. Lệnh này bỏ qua lần lặp hiện tại và bắt buộc lần lặp tiếp theo của vòng lặp diễn ra. Lệnh continue có thể được sử dụng trong vòng lặp while hoặc vòng lặp for. Dưới đây là cú pháp của lệnh continue: `continue`

Ví dụ:

``>>>for letter in 'Python':    

...   if letter == 'h':

...      break

...   print 'Chu cai hien tai :', letter

...

Chu cai hien tai : P

Chu cai hien tai : y

Chu cai hien tai : t

Chu cai hien tai : o

Chu cai hien tai : n

>>>``

- Nhận xét: lệnh continue khác lệnh break ở chỗ lệnh break thoát khỏi vòng lặp tại đó còn lên continue chỉ thoát khỏi giá trị hiện tại và vẫn tiếp tục vòng lặp với giá trị tiếp theo.

###2.4. Lệnh pass

Lệnh pass, giống như tên của nó, được sử dụng khi một lệnh là cần thiết theo cú pháp nhưng bạn không muốn bất cứ lệnh hoặc khối code nào được thực thi. Lệnh pass là một hoạt động null và không có gì xảy ra khi nó thực thi. Dưới đây là cú pháp của lệnh pass: `pass`

Ví dụ:

``>>>for letter in 'Python':   

...   if letter == 'h':

...      pass

...      print 'Day la khoi pass'

...   print 'Chu cai hien tai :', letter

...

Chu cai hien tai : P

Chu cai hien tai : y

Chu cai hien tai : t

Day la khoi pass

Chu cai hien tai : h

Chu cai hien tai : o

Chu cai hien tai : n``

<a name="phan3"></a>
##3. Tìm hiểu về hàm:
---------------------

Hàm, là một khối code được tổ chức và có thể tái sử dụng, để thực hiện một hành động nào đó. Trong các chương trước, bạn đã làm quen với một số hàm đã được xây dựng sẵn trong Python, điển hình như hàm print(). Tuy nhiên bạn cũng có thể tạo riêng cho mình một hàm với cách định nghĩa và kiểu giá trị cho riêng bạn. Các hàm này được gọi là user-defined function.

**Khai báo một hàm trong Python**

Khi khai báo các hàm để cung cấp một tính năng nào đó, bạn cần theo các qui tắc sau:

- Từ khóa **def** được sử dụng để bắt đầu phần định nghĩa hàm. Def xác định phần bắt đầu của khối hàm.

- def được theo sau bởi ten_ham được theo sau bởi các dấu ngoặc đơn ().

Các tham số được truyền vào bên trong các dấu ngoặc đơn. Ở cuối là dấu hai chấm.

- Trước khi viết một code, một độ thụt dòng được cung cấp trước mỗi lệnh. Độ thụt dòng này nên giống nhau cho tất cả các lệnh bên trong hàm đó.

- Lệnh đầu tiên của hàm là tùy ý, và nó là Documentation String của một hàm đó.

- Sau đó là lệnh để được thực thi.

``def ten_ham( cac_tham_so ):
   "function_docstring"
   function_suite
   return [bieu_thuc]``

**Triệu hồi một hàm trong Python**

Để thực thi một hàm, bạn cần gọi hàm đó. Phần định nghĩa hàm cung cấp thông tin về tên hàm các tham số và định nghĩa những hoạt động nào được thực hiện bởi hàm đó. Để thực thi phần định nghĩa của hàm, bạn cần gọi hàm đó. Cú pháp như sau:

``ten_ham( cac_tham_so )``

Ví dụ:

<img src="http://i.imgur.com/P023ReO.jpg">

Hàm return() trong Python:

Hàm return(bieu_thuc) được sử dụng để gửi điều khiển quay trở lại người gọi với bieu_thuc đã cho. Trong trường hợp không cung cấp bieu_thuc, thì hàm return này sẽ trả về None. Nói cách khác, lệnh return được sử dụng để thoát khỏi định nghĩa hàm.

Ví dụ:

<img src="http://i.imgur.com/afXV53E.jpg">

**Phân biệt argument và parameter trong Python**

Có hai kiểu dữ liệu được truyền trong hàm:

- Kiểu dữ liệu đầu tiên là dữ liệu được truyền trong lời gọi hàm. Dữ liệu này được gọi là argument. Argument có thể là hằng, biến hoặc biểu thức.

- Kiểu dữ liệu thứ hai là dữ liệu được nhận trong phần định nghĩa hàm. Dữ liệu này được gọi là parameter. Parameter phải là biến để giữ các giá trị đang đến.

**Phạm vi biến trong Python**

Tất cả các biến trong một chương trình không phải là có thể truy cập tại tất cả vị trí ở trong chương trình đó. Điều này phụ thuộc vào nơi bạn đã khai báo một biến.

Phạm vi biến quyết định nơi nào của chương trình bạn có thể truy cập một định danh cụ thể. Trong Python, có hai khái niệm về phạm vi biến là:

- Biến toàn cục

- Biến cục bộ

|Biến cục bộ trong Python|Biến toàn cục trong Python|
|------------------------|--------------------------|
|Các biến được khai báo bên trong một thân hàm là biến cục bộ|Biến được định nghĩa bên ngoài hàm được gọi là biến toàn cục|
|các biến cục bộ này chỉ có thể được truy cập ở bên trong hàm mà bạn đã khai báo, không thể được truy cập ở bên ngoài thân hàm đó|Biến toàn cục có thể được truy cập bởi tất cả các hàm ở khắp nơi trong chương trình. Do đó phạm vi của biến toàn cục là rộng nhất|

Ví dụ:

<img src="http://i.imgur.com/FiJl05G.jpg">

**Tham số hàm trong Python**

Python hỗ trợ các kiểu tham số chính thức sau:

- Tham số bắt buộc

- Tham số mặc định

- Tham số từ khóa (tham số được đặt tên)

- Số tham số thay đổi

|Tham số bắt buộc|Tham số mặc định|Tham số từ khóa|Số tham số thay đổi|
|----------------|----------------|---------------|-------------------|
|các tham số được truyền tới một hàm theo một thứ tự chính xác|tham số mà cung cấp các giá trị mặc định cho các tham số được truyền trong phần định nghĩa hàm, trong trường hợp mà giá trị không được cung cấp trong lời gọi hàm|Sử dụng tham số từ khóa, tham số được truyền trong lời gọi hàm được kết nối với phần định nghĩa hàm dựa trên tên của tham số|Bạn có thể cần xử lý một hàm mà có số tham nhiều hơn là bạn đã xác định trong khi định nghĩa hàm|

Ta có thể thấy rõ `tham số bắt buộc` ở các ví dụ trên, tức là ta phải truyền đầy đủ theo thứ tự khi gọi hàm nếu thiếu sẽ báo lỗi

Còn tham số mặc định có thể hiểu là tham số được định nghĩa sẵn khi xây dựng hàm. Khi gọi hàm ta có thể truyền hoặc không đối với tham số này. Ví dụ:

``def sum3so (a,b,c=3):

	return (a+b+c);
>>>

>>>x=sum3so(5,2)

>>>y=sum3so(5,2,4)

>>>print (x)

10

>>>print(y)

11``

Cú pháp cho một hàm có số thay đổi là:

``def tenham([tham_so_chinh_thuc,] *var_args_tuple ):

   "function_docstring"

   function_suite

   return [bieu_thuc]``

Một dấu * được đặt trước tên biến để giữ các giá trị của các tham số loại này. Tuple này vẫn là **trống** nếu không có tham số bổ sung nào được xác định trong khi gọi hàm. Dưới đây là ví dụ đơn giản.

<img src="http://i.imgur.com/7QBHlM7.jpg">
