# C語言程式編譯與逆向

## code
```c
#include <stdio.h>

int max(int num1, int num2);
 
int main ()
{
   int a = 100;
   int b = 200;
   int ret;

   ret = max(a, b);
 
   printf( "Max value is : %d\n", ret );
 
   return 0;
}

int max(int num1, int num2) 
{
   int result;
 
   if (num1 > num2)
      result = num1;
   else
      result = num2;
 
   return result; 
}
```

`file getMax.c`

```
getMax.c: C source, ASCII text
```

---
## 預處理階段(Preprocess)

`$ gcc -E getMax.c -o getMax.i`

產生[getMaxi.i](/Reverse/getMax.i)

> 預處理器(Preprocess)會在進行編譯前先處理原始碼內像#ifdef、#define相對簡單的詞句替換、和一些巨集代換的功能



`$ file getMax.i`

```
getMax.i: C source, ASCII text
```


---
## 編譯階段(Compile)

`$ gcc –S getMax.i –o getMax.s`

產生組語[getMax.s](/Reverse/getMax.s)


`$ file getMax.i`

```
getMax.s: assembler source, ASCII text
```


---
## 組譯階段(Assemble)

`$ gcc -c getMax.s -o getMax.o`

`$ file getMax.o`

```
getMax.o: ELF 64-bit LSB relocatable, x86-64, version 1 (SYSV), not stripped
```

---
## 連結階段(Link)

`$ gcc getMax.o -o getMax`

`$ file getMax`

```
getMax: ELF 64-bit LSB executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, for GNU/Linux 2.6.32, BuildID[sha1]=60f3226f4ebab90f1d7985165048f48176ab3744, not stripped
```
