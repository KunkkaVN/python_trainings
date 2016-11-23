#Mục lục:

[**1. Challenge 7**](#phan1)

[**2. Thư viện image**](#phan2)

<a name="phan1"></a>
##1.Challenge python 7: integrity:
---------------------------------

```sh
from PIL import Image
import re
ketqua=''
im=Image.open('oxygen.png')
rgb_im = im.convert('RGB')
for i in range(1,629,7):
	a,b,c=rgb_im.getpixel((i, 47))
	ketqua= ketqua + chr(a)
line = re.findall("[0-9]+",ketqua)
line2=""
for i in line:
	i = int(i)
	line2=line2+chr(i)
print line2	
```


Tải ảnh về:

```sh
from PIL import Image
ketqua=''
im=Image.open('oxygen.png')
rgb_im = im.convert('RGB')
for i in range(1,629,7):
	a,b,c=rgb_im.getpixel((i, 47))
	ketqua= ketqua + chr(a)
print ketqua
```

Ta được hint mới : `smart guy, you made it. the next level is [105, 110, 116, 101, 103, 114, 105, 116, 121]njb`

Nhìn vào thấy chỉ cần dịch `105, 110, 116, 101, 103, 114, 105, 116, 121` ra là có kết quả:

```sh
x = ketqua.index('[')
y = ketqua.index(']')
t=ketqua[(x+1):y]
ketqua = ''
j=0
for i in t:	
	if (i == ','):
		ketqua=ketqua + chr(j)
		j=0
	else:
		if (i.isalnum()):
			j=j*10+int(i)
ketqua=ketqua + chr(j)
print ketqua
```

<a name="phan2"></a>
##2. Dịch thư viện image:
-------------------------

 - Image.open(file, mode) ⇒ mở image

 - Image.blend(image1, image2, alpha) => tạo một ảnh mới, ảnh mới cùng kích thước, cùng mode nhưng khác ở out = image1 * (1.0 - alpha) + image2 * alpha 

 - Im.crop(box) ⇒ image : cắt ảnh theo 1 box ( box đc xác định bới các pixcel)

 - im.getbbox() ⇒ 4-tuple or None

 - im.getcolors() ⇒ trả về list (count, color) tuples or None

 - im.getdata() => trả về thông tin của ảnh

 - im.getpixel(xy) ⇒ lấy thông tin pixcel ở vị trí mình cần

 - im.load() => lấy tất cả các pixel của ảnh sau đó có thế lấy vị trí cần giống như getpixel 

 ```sh
 pix = im.load()
print pix[x, y]
pix[x, y] = value
```