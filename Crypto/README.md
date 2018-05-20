# U18 Эхний шатны даалгаварууд
## Бие халаалт (5pts)
**Даалгавар**
```
SFpVMTh7VzNsY29tZV90b19IWlUxOF8weGQ3czg3ZDkyZDNhMn0=
```
[Base64](https://en.wikipedia.org/wiki/Base64) шифр ба үүнийг тайлснаар туг гарж ирнэ.
```python
import base64
base64.b64decode('SFpVMTh7VzNsY29tZV90b19IWlUxOF8weGQ3czg3ZDkyZDNhMn0=')
```
> flag: HZU18{W3lcome_to_HZU18_0xd7s87d92d3a2}

## 13р зуун (5pts)
**Даалгавар**
```
UMH18{2EBG13or5gp1cu3e}
```
13р зуун буюу бидний сайн мэдэхээр [ROT13](https://en.wikipedia.org/wiki/ROT13) ба терминал орчинд дараах кодыг бичсэнээр тугыг хэвлэх юм.
```shell
echo "2EBG13or5gp1cu3e" | tr '[A-Za-z]' '[N-ZA-Mn-za-m]'
```
> flag: HZU18{2ROT13be5tc1ph3r}

## Alice and Bob (Part1)
**Challenge**
``` 
n : 1007
e : 5
c : 436
```
> flag: HZU18{18}

## Alice and Bob (Part2)
**Даалгавар**
```
n= 58900433780152059829684181006276669633073820320761216330291745734792546625247
e= 65537
c=38625589080883093104580367978310695507327838321390248676015440812648307006611
```
> flag : **HZU18{RS4_is_v3ry_EZ}**

## New Crypto
**Challenge**
```
437 732 y24 u29 i20 y18 H0 07 x36 y33 }51 717 312 a48 543 _34 e45 Z1 U2 s11 s26 438 Y6 _22 e41 035 444 m23 _19 r42 r30 u8 u14 r9 c28 116 447 {5 _10 13 131 84 546 249 440 c13 521 b50 327 r15 e39 _25
```
**Solution**

Уг даалгавар нь HZU18{flag} хэсгийг нэг нэгээр нь салгаж авсан байх бөгөөд сайн анзаарч харвал H**0** Z**1** U**2** 1**3** U**4** гэх мэтчилэн явсаар b**50** }**51** гэж дууссанаар манай туг гарж ирэх юм.


**Flag**
```
HZU18{Y0ur_s3cur17y_i5_my_s3cur17y_0x44e4er54e54a2b}
```
