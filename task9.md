#Mục lục:

[**1. Challenge 4**](#phan1)

[**2. Challenge 5**](#phan2)

[**3. Thư viện pickle**](#phan3)

<a name="phan1"></a>
##1. Challenge python 4:
------------------------

Challenge này chỉ đưa ra cho chúng ta 1 bức hình và chẳng có gợi ý gì cả, tất nhiên nhìn bức hình thì chả hiểu nó có ý nghĩa quần què gì cả

Việc đầu tiên nghĩ tới là xem source cửa wed thì may quá được cái này `<!-- urllib may help. DON'T TRY ALL NOTHINGS, since it will never 
end. 400 times is more than enough. -->` .Đọc qua thì có thể biết được gợi ý là dùng thư viện urllib giúp giải bài này. click vào bức ảnh thì được đoạn chữ sau `and the next nothing is 44827` . Lúc này ta có thể hiểu ngay vấn đề là chỉ việc thay dãy số cửa url vào cho tới khi nhận dược key cửa challenge này. Việc này lặp khoảng 400 lần nên cần dùng thư viện urllib.

Code chương trình: http://codepad.org/ybOn2QRM

```sh
import re
import requests

link=12345
source = requests.get('http://www.pythonchallenge.com/pc/def/linkedlist.php?nothing='+str(link))
line=source.text
line2 = re.findall("[0-9]+",line)

while len(line2)==1:
	link=line2[-1]
	source = requests.get('http://www.pythonchallenge.com/pc/def/linkedlist.php?nothing='+str(link))
	line=source.text
	line2 = re.findall("[0-9]+",line)
print link
print line
```

<a name="phan2"></a>
##2. Challenge python 5:
------------------------

Code: http://codepad.org/7NbKcn2I

```sh
import pickle,urllib2
file = urllib2.urlopen('http://www.pythonchallenge.com/pc/def/banner.p')
line = pickle.load(file)
ketqua= ''
for i in line:
	for j,k in i:
		ketqua = ketqua + j*k
	ketqua =ketqua + '\n'
print ketqua
```

Đề bài:

<img src="http://i.imgur.com/khzn62v.jpg">

Challenge này nó đưa ra cái hình kèm gợi ý `pronounce it ` chả hiểu đó là gì cả :D

- Việc đầu tiên thì tất nhiên xem source, sau đó mò thì thấy `banner.p` chứa cái chuỗi gì đó

- Dùng thư viện pickle và hàm `pickle.load` thì ta lại phát hiện nó được như sau

<img src="http://i.imgur.com/DWlaIcE.jpg">

khi in ra ta để ý điều đặc biệt sau như [('',95)] cấu trúc như vậy lặp lại rất nhiều lần như thể in dấu '' 95 lần vậy

- Từ đó thì ta giải quyết challenge này dựa trên ý tưởng là dùng hàm for đọc lần lượt sau đó dùng cặp biến để đọc cặp ('',95) chẳng hạn rồi

<a name="phan3"></a>
##3. tìm hiểu thư viện pickle:
------------------------------

Các chuỗi có thể được ghi hoặc đọc dễ dàng từ một tập tin. Các số cần một ít cố gắng hơn, vì phương thức read() chỉ trả về chuỗi, và cần được truyền vào một hàm như int(), nó sẽ nhận một chuỗi như '123' và trả về giá trị số 123 của nó. Tuy nhiên, khi bạn muốn lưu các kiểu dữ liệu phức tạp hơn như danh sách, từ điển, hoặc các đối tượng, việc này trở nên rắc rối hơn nhiều.

Thay vì để người dùng luôn viết và gỡ rối mã để lưu các kiểu dữ liệu phức tạp, Python cung cấp một mô-đun chuẩn gọi là pickle. Đây là một mô-đun tuyệt diệu có thể nhận hầu hết mọi đối tượng Python (ngay cả một vài dạng mã Python!), và chuyển nó thành một chuỗi; quá trình này được gọi là giầm (pickling). Tạo lại đối tượng từ một chuỗi được gọi là vớt (unpickling). Giữa việc giầm và vớt, biểu diễn dạng chuỗi của đối tượng có thể được lưu vào tập tin, hoặc gửi qua mạng đến một máy ở xa.

**pickle.dump(obj, file, protocol=None, *, fix_imports=True)**

Cú pháp đơn giản `pickle.dump(obj,file)`. Hàm này có thể hiểu như là một hàm write() nhưng không bị gò bó mà có thể sử dụng với nhiều đối tượng obj khác nhau sẽ được chú thích ở dưới

**pickle.load(file, *, fix_imports=True, encoding="ASCII", errors="strict")**

Cú pháp đơn giản `pickle.load(file)`. Hàm này có thể hiểu như là một hàm read() có 2 cách đọc là đọc theo `errors` còn nếu để trống thì sẽ đọng theo line-từng dòng

**Điểm đặc biệt của dump và load so với write, read**

Hàm write, read chỉ đọc được các đối tượng là tringbuffer còn với dump và load đó là:

- None, True và False

- số nguyên, số dấu chấm động, số phức, chuỗi, byte, bytearrays

- tuples, lists, sets, and dictionaries

- các hàm chức năng