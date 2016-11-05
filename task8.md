#Mục lục
[**1. Ứng dụng Live HTTP Headers **](#phan1)

[**2. Đăng kí tài khoảng Hackthissite**](#phan2)

[**3. Challenege 1 programming**](#phan3)

<a name="phan1"></a>
##1. Live HTTP Headers:
-----------------------
Link: https://addons.mozilla.org/vi/firefox/addon/live-http-headers/

**Live HTTP Headers** là một add-on giúp chúng ta xem "header" của trang web trong khi đang duyệt. Ngoài ra, nó còn có thể Replay - tái tạo lại truy vấn bất kỳ và cho phép bạn chỉnh sửa các thông tin header cũng như nội dung, dữ liệu của truy vấn đó trước khi gửi đi.

Sau khi cài đặt plugin LHH bạn hãy khởi động lại firefox & mở LHH lên bằng cách:

Firefox Menu => Tools => Live HTTP Headers

Ví dụ:

HTTP/1.1 200 OK
Server: Apache
Last-Modified: Thu, 24 Mar 2011 15:32:01 GMT
Accept-Ranges: bytes
Content-Encoding: gzip
X-UA-Compatible: IE=EmulateIE7
Content-Length: 30204
Content-Type: text/html
Cache-Control: max-age=5
Date: Thu, 24 Mar 2011 16:26:22 GMT
Connection: keep-alive
Vary: Accept-Encoding

Ta bắt đầu bằng cách đọc header:

HTTP/1.1: Điều này có nghĩa là www.in.com đang xử dụng giao thức HTTP phiên bản 1.1 đễ truyền tín hiệu cho tôi.

200 OK: HTTP status 200 và thông báo là OK => www.in.com đang tồn tại và sẳn sàng trả lời truy vấn của tôi.

Server: Apache => Đây là một thông báo quan trọng trong header, thông tin này cho phép bạn định hình tốt hơn đối tượng đang truy vấn. Trong trường hợp này, www.in.com đang cố che dấu công nghệ mà họ đang xử dụng đễ phát hành website, môi trường vận hành...Chúng ta chỉ biết họ đang xử dụng Apache đễ làm máy chủ xuất bản website. Và đễ bạn hiểu thêm về cách tấn công bạn có thể tìm đọc các tài liệu về Apache Web Server.

Last-Modified: Thu, 24 Mar 2011 15:32:01 GMT => Thời gian vừa sửa chửa file, thông số này đôi khi không quan trọng, vì nó thường dùng đễ trình duyệt xác thực việc lưu lại bộ đệm của www.in.com trên máy bạn là lúc nào thôi.

Chúng ta chỉ nên chú ý những tín hiệu đặc biệt như: Content-Type, Content-Length, Content-Encoding. Nó ảnh hưởng đến nội dung trình chiếu trên trình duyệt của bạn nhiều hơn.

<a name="phan2"></a>
##2. Hướng dẫn đăng kí acc trên hackthissite:
---------------------------------------------

B1: vào trang https://www.hackthissite.org/register để tạo mới tạo khoảng

B2: Điền các thông tin tài khoảng

<img src="http://i.imgur.com/sfKAEUx.jpg">

- Ursename: tên tài khoản

- Passphrase: mật khẩu cho tài khoản. Bạn phải sử dụng đúng các yêu câu như: có chữ cái hoa, thường, số, dài ít nhất 15 ký tự

- Question: khi bạn mất mật khẩu có thể dùng nó để lấy lại

- Email Address: email cho tài khoản

B3: Sau khi điền đủ nội dung bạn ấn ok và vào mail để kích hoạt tài khoản

<a name="phan3"></a>
##3. Challenge1-progamming:
---------------------------

- **Đề bài** :

```sh
This level is about unscrambling words.
Find the original (unscrambled) words, which were randomly taken from a wordlist.<--
Send a comma separated list of the original words, in the same order as in the list below.
You have 30 seconds time to send the solution.
List of scrambled words:   	
legrda
encnotc
liaiwlms
asladl
tobtuns
erpcie
jcaiek
blolugd
nseulfwo
imspyt
Answer:            (Example:   word1,word2,word3, ... word9,word10)
```

- **Yêu cầu đề** : Cho file `worldlist.txt` chứa các tự nguyên thủy, nhiệm vụ là phải tiềm được 10 từ trong đấy với gợi ý là cho 10 từ đã bị xáo trộn, sau 10s sẽ hủy

- **Ý tưởng giải**: Để giải quyết challenge này thì chúng ta cần giải quyết các vấn đề như với 10 từ bị xáo trộn, lần lượt tìm kiếm so sánh với các từ trong `worldlist.txt`. tìm thấy thì in ra và submit trong vòng 30s.

Đối với bài này thì mình sử dụng file để lấy dữ liệu của challenge và ghi lại kết quả vào file đó:

Code: http://codepad.org/1uK7XzeV (có comment chú thích các phần)

```sh
##Copy 10 từ ở đề vào file
g=open("key.txt",'r')
list=[]
for line in iter(g):
	list.append(line)
g.close
list1=[]
for i in list:
	b=i.index('\n')
	j=i[:b]
	list1.append(j)
#Hàm chính thực hiện việc xắp xếp và tìm kiếm 10 từ		
f=open("wordlist.txt",'r')
word_list=[]
for line in iter(f):
	word_list.append(line)
f.close()
def timkiem(word):
	for line in word_list:
		b=line.index('\n')
		line1=line[:b]
		x=0
		y=[]
		for i in word:
			y.append(i)		
		for i in line1:
			for j in y:
				if i==j:
					x=x+1
					y.remove(j)
					break
		if (x== len(word)) & (len(y) ==0) & (len(word)==len(line1)):
			return line1
#Ghi đáp án vô file				
dapan=''			
for i in list1:
	dapan=dapan+timkiem(i)+','

g=open("key.txt","w")
g.write(dapan)
g.close	
```

