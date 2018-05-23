## Prime (20pts)
**Challenge**

1-ээс 1337 хүртэлх тоонууд дундаас бүх анхны тооны нийлбэр хэд вэ?
flag format : HZU18{answer}

**Solution**
```python
count=0
for num in range(2,1337):
    prime = True
    for i in range(2,num):
        if (num%i==0):
            prime = False
    if prime:
       print num
       count+=num
       print coun
```
**Flag**
```
HZU18{133386}
```
