## Math (40pts)
**Challenge**

url: http://218.100.84.112:9091

**Solution**

Эхлээд өгөгдсөн хаяг руу хандаж үзвэл

![md5](https://github.com/enhbold/HZU18-2018/blob/master/include/md5.png)

Даалгаварын гол зориго бол уг хаяг дээрх тоонуудыг арифметик үйлдэл хийн 5 секундын дотор серверлүү явуулах ёстой байв. Амархан мэт сонсогдож байгаа боловч нэг асуудал нь тоонуудыг md5-аар хаш хийсэн бөгөөд тоонууд нь зөвхөн 1-999 хүртэл байв.
Нийлбэрийг илгээхдээ **GET** хүсэлт авсан **cookie** гээ ашиглан буцаагаад илгээнэ.
```python
#coding: utf-8
import hashlib
import requests
import re
response = requests.get("http://127.0.0.1/math.php")
cookie = response.cookies['PHPSESSID']
numbers = re.findall(r"([a-fA-F\d]{32})", response.text)
flag=''
too=[]
for j in numbers:
    for i in range(0,1000):
        m = hashlib.md5()
        m.update(str(i).encode('utf-8'))
        m.hexdigest()
        if m.hexdigest()==j:
            flag=flag+str(i)+" "
#results = [int(i) for i in flag]
results=flag.split(" ")
too1=results[0]
too2=results[1]
too3=results[2]
flag1=(int(too1)*int(too2))/int(too3)
print 'flag:',flag1

r = requests.post("http://127.0.0.1/math.php", data={'answer':int(flag1),'sum': 'Илгээх'}, headers={'Cookie': 'PHPSESSID='+cookie})
print r.text[0:150]
```
Үүнийг бодохдоо 1-999 хүртэл тоонуудаар **dictionary** үүсгэн арифметик үйлдэлээ хийсэн болно.

**Flag**
```
HZU18{S1mPl3_M4th}
```








