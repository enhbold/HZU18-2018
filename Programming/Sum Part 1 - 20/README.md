## Sum Part1(20pts)
**Challenge**

Нийлбэр хэд вэ?

**Solution**
```python
f=open('random_numbers.txt').readlines()
total = 0
for line in f:
	line=line.replace("\n","")
	if line.isdigit():
		total+=int(line)
print total
```
**Flag**
```
HZU18{190141301939}
```
