## Sum Part2 (50pts)
**Challenge**

Өмнөх 2-ийг бодсон гэж найдъя url: http://218.100.84.112:9090

**Solution**
Өгөгдсөн хаяг руу хандаж үзвэл

![HZU18](https://github.com/enhbold/HZU18-2018/blob/master/include/39091920-f5659102-4631-11e8-837f-3b2da95f3fae.png)

Даалгаварын гол зорилго нь уг хаяг дээрх **random** тоонуудын нийлбэрийг серверлүү 5секундын дотор хариуг **POST** хүсэлт явуулах байв.

```python
#!/usr/bin/python
#coding: utf-8
import requests
import re

response = requests.get("http://127.0.0.1", verify=False)
cookie = response.cookies['PHPSESSID']

target_numbers=re.findall(r'\d+\s\,',response.text)

listofnum=[(s.replace(" ,","")) for s in target_numbers]
results = [int(i) for i in listofnum]

r = requests.post("http://127.0.0.1", data={'answer':sum(results),'sum':'Илгээх'}, headers={'Cookie': 'PHPSESSID=' + cookie})
print r.text[0:150]
```
**Flag**
```
HZU18{M4th_Kill3r}
```
