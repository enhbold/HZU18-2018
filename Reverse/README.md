## Baby Win Reverse (5pts)
**Challenge**

DOS Executable файлыг таних header-ийн утгыг оруулна уу.

>Flag формат: HZU18{Таны хариулт}

**Solution**

Энэ даалгаварын хариу нь EXE файлын **signature** утга болох **MZ** оруулсан боловч болохгүй байсан тул тус утгыг **4D5A** гэж 
hex утгаар нь оруулж үзэхэд зөв болсон.

**Flag**
```
HZU18{4D5A}
```

## Baby Linux Reverse (10pts)
**Challenge**

sub $0x48, %esp mov %esp, %ebp

Дээрх ямар Assembly syntax вэ?

>Flag формат: HZU18{Таны хариулт}
