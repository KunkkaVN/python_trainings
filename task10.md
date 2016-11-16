#Task 10: challenge python lever 6 : oxygen

##1. Code: 
----------

http://codepad.org/52b68oVg

```sh
import zipfile,re
file = "90052.txt"
f= zipfile.ZipFile('channel.zip','r')
line = f.open(file,'r')
line2=line.read()
line3 = re.findall("[0-9]+",line2)
ketqua =''
while len(line3)==1:
	file = line3[-1]+".txt"
	line = f.open(file,'r')
	ketqua=ketqua+f.getinfo(file).comment
	line2=line.read()
	line3 = re.findall("[0-9]+",line2)
print ketqua
```

##2. Ý tưởng giải challenge:
----------------------------

link challenge: http://www.pythonchallenge.com/pc/def/channel.html

1. Việc đầu tiên bao giờ cũng là xem source

<img src="http://i.imgur.com/4Wx8dhC.jpg">

Lúc đầu bạn có thể bị đánh lừa bởi trang paypal + với hint. Ở đây, bạn hãy thử thay gì đó như channel.jpg vào giống như bài trước xem sao. Mình mò một hồi được `zip.html` vì hint cho zip ở góc trên thì được `yes. find the zip.` .Có vẻ chúng ta đi đúng hướng rồi

2. `http://www.pythonchallenge.com/pc/def/channel.zip`

Đây chính là thứ chúng ta tìm được từ gợi ý zip. Mở lên thì có dạng quen thuộc như challenge trước 

<img src="http://i.imgur.com/iAP5Ox6.jpg"> 

Sau khi xử lý đống đó giống challenge trước ta được kết quả

<img src="http://i.imgur.com/eYYBZIz.jpg">

3. Collect the comment

dựa vào giợi ý này ta sẽ phải thu thập các comment trong file zip và kết quả là: 

<img src="http://i.imgur.com/i2mDCvV.jpg">

Mừng quá, tưởng ngày đáp án là hockey, sau khi submit thì lại nhận được `it's in the air. look at the letters.` . Để ý lại trong chữ hockey thì mới thấy nó được cấu tạo bởi các chữ cái và chữ đó là `oxygen` @@