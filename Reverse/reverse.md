# C語言程式編譯與逆向

code : [getMax.c](/Reverse/file/getMax.c.md)

---
## 預處理階段(Preprocess)

> 預處理器(Preprocess)會在進行編譯前先處理原始碼內像#ifdef、#define相對簡單的詞句替換、和一些巨集代換的功能

`$ gcc -E getMax.c -o getMax.i`

產生[getMax.i](/Reverse/file/getMax.i)



---
## 編譯階段(Compile)

> 編譯器(compiler)是將高階語言所寫的原始程式，翻譯成機器語言組成的目的程式

`$ gcc –S getMax.i –o getMax.s`

產生組合語言[getMax.s](/Reverse/file/getMax.s)


---
## 組譯階段(Assemble)

> 組譯器(Assembler)會將組合語言的原始程式，翻譯成機器語言組成的中間檔 ".obj"或".o"

`$ gcc -c getMax.s -o getMax.o`

---
## 連結階段(Link)

> 連結器(Linker)會將中間檔 obj files 連結起來，找到symbol（函式，變數名）與程式庫（shared obj）中的副程式，產生可執行的obj檔(executable obj)

`$ gcc getMax.o -o getMax`


### 檔案類型

```
  getMax.c: C source, ASCII text
  getMax.i: C source, ASCII text
  getMax.s: assembler source, ASCII text
  getMax.o: ELF 64-bit LSB relocatable, x86-64, version 1 (SYSV), not stripped
  getMax: ELF 64-bit LSB executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, for GNU/Linux 2.6.32, BuildID[sha1]=60f3226f4ebab90f1d7985165048f48176ab3744, not stripped
```
