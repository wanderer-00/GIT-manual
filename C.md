# C
## Делаем красивый код )
1. Перемещаем файл ```.clang-format``` из папки ```materials/linters``` в папку со скриптом, который нужно поправить, в ```src```
2. 


## Компиляция программы через <b>GCC</b> <b>C11</b>
```c
gcc -Wall -std=c11 -Werror -Wextra -o имя_скомпилированного_файла имя_файла.c
```
Или краткая версия
```c
gcc -Wall -std=c11 -Werror -Wextra имя_файла.c
```
При краткой версии имя скомпилированного файла будет ```a.out``` 

```c
#include <stdio.h>

int main(){

    printf("Hello, AI!\n");
    
    return 0;
}

```
