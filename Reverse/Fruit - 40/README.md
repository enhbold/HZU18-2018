## Fruit (40pts)
**Challenge**

Миний дуртай жимс ?
> attachment: hello

**Solution**

Өгөгдсөн файлын төрлийг харвал ELF 32-bit LSB pie executable байх бөгөөд үүнийг ./hello гэж ажилуулж үзвэл 

![hellofile](https://github.com/enhbold/HZU18-2018/blob/master/include/hellofile.png)

Гараас ямар нэгэн зөв өгөгдөл орох хүртэл ажилласаар байх ба уг файлыг **debug** хийж үзье.
Хэд хэдэн **debug** хийдэг tool байдаг боловч би энэ удаад **ltrace** гэх tool-ийг ашиглах болно.

![debugging](https://github.com/enhbold/HZU18-2018/blob/master/include/debugging.png)

Үүнийг харвал **strcmp** нь хоёр **string** төрлийн утгыг харьцуулж байна. Хэрэв гараас оруулсан өгөгдөл нь **Elderberry** байвал
тугыг бидэнд хэвлэх болно.

**Flag**
```
HZU18{Elderberry}
```
