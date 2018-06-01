# 程式編譯組譯與逆向

## C語言程式編譯與逆向

#### code:
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

---
### 預處理階段:

`
gcc -E getMax.c -o getMax.i
`

[getMax.i](/Reverse/getMax.i)

---
### 編譯階段

`
gcc –S getMax.i –o getMax.s
`

[getMax.s](/Reverse/getMax.s)

---
### 組譯階段

`
gcc -c getMax.s -o getMax.o
`

---
### 連結階段

`
gcc getMax.o -o getMax
`
