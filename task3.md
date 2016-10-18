#Mục lục:
[**1.Cài đặt Python**](#phan1)

[**2.Tìm hiểu và cài đặt PIP**](#phan2)

[**3.Cài đặt biến môi trường**](#phan3)

[**4.Khái niệm về thông dịch và biên dịch**](#phan4)

[**5.Chương trình Hello World giữa biên dịch và thông dịch**](#phan5)
---------------------------------------------------------------------
<a name="phan1"></a>
##1.Cài đặt Python đối với windown
----------------------------------
- Vào trang https://www.python.org/ sau đó vào mục download tải bản python phù hợp với hệ điều hành đang dùng
<img src="http://i.imgur.com/GARKce8.jpg">

Lúc này bạn có thể chọn vào mục `Install Now` để cài theo mặc định hoặc `Customize installation` để cài đặt theo ý mình
Ở đây mình chọn cài theo tùy chọn
<img src="http://i.imgur.com/vg8J4wG.jpg">
<img src="http://i.imgur.com/Jr0b10N.jpg">
<img src="http://i.imgur.com/UB69DdM.jpg">

Tùy vào bạn muốn thư viện nào kèm theo thì có thể tích vào rồi chọn Next để cài đặt
<a name="phan2"></a>
##2. Tìm hiểu về Pip
--------------------
- Pip là 1 công cụ chuyên dùng để quản lý các gói phần mềm (thư viện) của Pythons
Để cài PIP thì ban nên làm như sau:
1. Cài setuptool trc: https://pypi.python.org/pypi/setuptools . Down bản phù hợp với Python của bạn. Setuptool cũng là 1 công cụ kiểu như pip, bạn có thể dùng nó thay pip nếu muốn, chỉ là cái này thì outdate rồi, bây h ngta dùng pip. Cài setuptool để có 1 số lib cần thiết cho việc cài pip
2. Download pip về: https://pypi.python.org/pypi/pip
3. Giải nén pip package vừa down. cd vào trong đó rồi chạy:
```python setup.py build
python setup.py install```
**Nếu bạn cài Python theo hướng dẫn ở mục 1 thì không cần cài pip nữa vì đã có mục cài sẵn cho mình**
<img src="http://i.imgur.com/L9gAl1k.jpg">
<a name="phan3"></a>
##3. Cài đặt biến môi trường
----------------------------
-Để cài đặt biến môi trường chỉ cần click như hình khi cài python là được.
<img src="http://i.imgur.com/jGz35GB.jpg">
<a name="phan4"></a>
##4. Khái niệm thông dịch và biên dịch
--------------------------------------
1. Trình biên dịch - Compiler

Trình biên dịch sẽ dịch mã nguồn thành mã máy trên một HĐH xác định và chỉ chạy trên hệ điều hành đó, do đó các chương trình được biên dịch sẽ phụ thuộc nhiều vào nền tảng và hệ điều hành

Ưu điểm:
- Ràng buộc chặt chẽ về kiểu trong ngôn ngữ.
- Hỗ trợ các tính năng đa tuyến, transtion ...
- Do đã biên dịch phụ thuộc vào hệ điều hành nên chương trình có thể tận dụng toàn bộ các tính năng đặc trưng của HĐH
- Tốc độ thực thi tốt
- Bảo mật tốt (không thể xâm phạm mã nguồn làm thay đổi chức năng của chương trình)

Nhược điểm:
- Sau khi biên dịch ra ngôn ngữ máy thì chỉ có thể chạy trên một HDH xác định.

2. Trình thông dịch - Interpreter

Trình thông dịch là một trình để thông dịch ngôn ngữ. Trong thông dịch mã nguồn của chương trình không được dịch trước thành ngôn ngữ máy, mà khi chạy chương trình mã nguồn mới được dịch và thực thi từng dòng lệnh 1. 

Tất cả các ngôn ngữ không biên dịch ra mã máy một lần duy nhất điều phải sử dụng trình thông dịch (PHP, WScripts, Perl, Linux Shell, Python....). Các ngôn ngữ theo trình thông dịch thường được gọi là script (kịch bản)

Như vậy chương trình viết bằng ngôn ngữ script phải có một trình thông dịch kèm theo khi chạy chương trình. 

Ưu điểm:
- Phát triển nhanh chóng
- Có thể chỉnh sửa mã nguồn bất kỳ khi nào
- Mạnh xử lý cú pháp 
- Uyển chuyển mềm dẻo.
- Có thể chạy trên mọi nền tảng (flatform, hệ điều hành) nếu có trình thông dịch tương ứng, tại vì không phải là ngôn ngữ máy(chỉ là file văn bản) nên không bị phụ thuộc vào HĐH. tiêu biểu là Perl, PHP, Python

Nhược điểm:
- Tại vì là ngôn ngữ thông dịch chạy line by line nên nên ngôn ngữ thông dịch không hỗ trợ đa luồn (multi thread), giao dịch (transaction)
- Cũng do chạy line by line nên tốc độ thực thi không nhanh bằng các chương trình viết bằng ngôn ngữ biên dịch (C, C++, VB...) đã chuyên trực tiếp ra ngôn ngữ máy.
<a name="phan5"></a>
##5. Chương trình Hello world
-----------------------------
Sự khác biết dễ thấy nhất khi dùng trình thông dịch và trình biên dịch (ở đây là Python và C) là
- Thông dịch: thực hiện theo từng dòng lên: `print ("Hello World")` là đã in ra màn hình kết quả `Hello World`
- Biên dịch: tiền hành dịch toàn bộ code ra file .exe khi muốn chạy thì phải chạy file exe đó dù cũng chỉ là 1 dòng code `printf("Hello World");` mà thôi
<img src="http://i.imgur.com/P6pT34k.jpg">
