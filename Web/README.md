## Logmein1 бие халаалт (5pts)
**Challenge**

http://218.100.84.112:9000

**Solution**

Өгөгдсөн хаяг руу хандаж үзвэл

![log1](https://github.com/enhbold/HZU18-2018/blob/master/include/log1.png)

**Source** кодыг нь харвал **JS** код байх бөгөөд

```javascript
<script>
    $(document).ready(function(){
        $("#login").submit(function(e){
            e.preventDefault();
            var username = $("#username").val();
            var password = $("#password").val();
            if(username == "admin" && password == "supersecure") {
                document.location = "success.php";
            } else {
                alert("Incorrect username and password!");
            }
        });
    });
</script>
```
Хэрэв хэрэглэгчийн **нэр** -  **admin** болон **нууц үг** - **supersecure** бол хариу болох тугыг хэвлэнэ.

**Flag**
```
HZU18{cl1ent_s1d3_auth_sux}
```

## Logmein2 (10pts)
**Challenge**

http://218.100.84.112:9003

**Solution**

Өгөгдсөн хаяг руу хандан **Source** кодыг нь харвал хамгийн доод хэсэгт нь <!-- delete it later index.phps --!> гэх үг байсан бөгөөд

![log2](https://github.com/enhbold/HZU18-2018/blob/master/include/log2.png)

Үүний тусламжтай http://218.100.84.112:9003/index.phps гэж хандаж үзвэл 

![log2-2](https://github.com/enhbold/HZU18-2018/blob/master/include/log2-2.png)

Өмнөх даалгавартай адил боловч хэрэглэгчийн нууц үгийг [md5](http://md5decrypt.net/)-хаш утгаар шифрлэсэн байх ба хэшлэсэн утгыг тайлан
тайлан нууц үгийг **SuperSecurePassword** гэж оруулахад тугыг бидэнд хэвлэнэ.

**Flag**
```
HZU18{you_kn0w_about_hash}
```
## Hacker Academy 1 (10pts)
**Challenge**

http://218.100.84.112:9101

**Solution**

Өгөгдсөн хаяг руу хандан **Source** кодыг нь харвал хамгийн доод хэсэгт нь 

**<!-- page: server.py -->** гэсэг comment байв.

http://218.100.84.112:9101/server.py/ - руу хандаж үзэхэв серверээс бидэнд тугыг хэвлэж өгөв.

**Flag**
```
HZU18{EZ_FIRST_BL00D}
```
## Logmein3 (50pts)
**Challenge**

http://218.100.84.112:9001

**Solution** 

Өгөгдсөн Веб хуудасруу хандаж үзтэл хэрэглэгчийн нэр нууц үг шалгах форм байх ба **php** source кодыг өгсөн байв. Тус **source** кодыг харвал
```php
<?php
include'flag.php';
if (isset($_POST['login'])) {
    if ($_POST['username']!=$_POST['password'] && md5($_POST['username'])==md5($_POST['password'])) {
        echo '<h1 style="color:red">'.$flag.'</h1>';
    }
    else{
        $sound_id =(rand(1,10));
        echo 'Username or password incorrect';
        echo '<audio autoplay>
          <source src="sound/Sound_Effect_HD_'.$sound_id.'.mp3" type="audio/mpeg">
        </audio>';
    }
}     
```
Тугыг авахын тулд **md5(username)==md5(password)** нөхцөлийг давах ёстой ба **PHP** хэлэнд тэнцүү нөхцөл шалгахдаа === гэж бичдэг боловч
уг тохиолдолд == ашигласан байх бөгөөд энэ нь бидэнд тугыг авахад амар болгож өгч байгаа юм.
Хэрэв == нөхцөл бичсэн бол энэ нь тухайн утгыг хүчээр тоо болгон өөрчилдөг ба. 

Уг алдааг ашиглан жоохон хайлт хийж үзвэл

```
var_dump(md5('240610708') == md5('QNKCDZO')) //true
```
гэж үзэхэд **true** гэж хэвлэж байна. 

Учир нь энэ хоёрыг [md5](https://md5decrypt.net) хашаар хашлаж үзвэл 
```
0e830400451993494058024219903391

0e462097431906509019562988736854
```
байх ба өмнө нь хэлсэнчлэн үүн дээр **==** нөхцөлийг ашиглавал хүчээр тоо болгох бөгөөд хоёр утга хоёулаа **0** болох бөгөөд үндсэндээ 0=0 болж хариулт үнэн болно.

**Flag**
```
HZU18{s1gns1gns1gnaftermd5}
```
## Baby Web (65pts)
**Challenge**

http://218.100.84.112:9004

**Hint!**
```
<html>
<head>
<title>BigNumber</title>
<link rel='stylesheet' href='style.css' type='text/css'>
</head>
<body>

<?php
require 'flag.php';
if (isset($_GET)) {
if (is_numeric($_GET)){
if (strlen($_GET) < 4){
if ($_GET > 999)
die('Flag: '.$flag);
else
print '<p class="alert">Baga bna, Tom Bai</p>';
} else
print '<p class="alert">Tom bna, Baga bai</p>';
} else
print '<p class="alert">No Number, No Cry</p>';
}
?>

<section class="login">
<form method="get">
<input type="text" required name="too" placeholder="Numbers Only" /><br/>
<input type="submit"/>
</form>
</section>
</body>
</html>
```
**Solution**

Уг даалгаварт тусламж өгөгдсөнөөр бидэнд тугыг олж авахад илүү амар болсон юм.
Бид 3 оронтой 999өөс их тоо оруулах бөгөөд энэ нь зөвхөн бүхэл тоо байна.

Дараах код нь is_numeric() гэх нөхцөл ашигласан ба энэ нь **hex,decimal,binary** утгуудыг **true** гэж үздэг бөгөөд гараас оруулах
999-өөс их тоог decimal утгаар **3e8** оруулж үзтэл тугыг бидэнд өгсөн.

> 3 x 10 ^ 8 = 300’000’000 энэ нь мэдээж 999 өөс их тоо болно.

**Flag**
```
HZU18{HEX_NUMBER>999}
```






