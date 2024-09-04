# Консоль
## Поддерживаемые символы <a href="https://www.cs.cmu.edu/~pattis/15-1XX/common/handouts/ascii.html">ASCII</a>
```
Dec  Char                           Dec  Char     Dec  Char     Dec  Char
---------                           ---------     ---------     ----------
  0  NUL (null)                      32  SPACE     64  @         96  `
  1  SOH (start of heading)          33  !         65  A         97  a
  2  STX (start of text)             34  "         66  B         98  b
  3  ETX (end of text)               35  #         67  C         99  c
  4  EOT (end of transmission)       36  $         68  D        100  d
  5  ENQ (enquiry)                   37  %         69  E        101  e
  6  ACK (acknowledge)               38  &         70  F        102  f
  7  BEL (bell)                      39  '         71  G        103  g
  8  BS  (backspace)                 40  (         72  H        104  h
  9  TAB (horizontal tab)            41  )         73  I        105  i
 10  LF  (NL line feed, new line)    42  *         74  J        106  j
 11  VT  (vertical tab)              43  +         75  K        107  k
 12  FF  (NP form feed, new page)    44  ,         76  L        108  l
 13  CR  (carriage return)           45  -         77  M        109  m
 14  SO  (shift out)                 46  .         78  N        110  n
 15  SI  (shift in)                  47  /         79  O        111  o
 16  DLE (data link escape)          48  0         80  P        112  p
 17  DC1 (device control 1)          49  1         81  Q        113  q
 18  DC2 (device control 2)          50  2         82  R        114  r
 19  DC3 (device control 3)          51  3         83  S        115  s
 20  DC4 (device control 4)          52  4         84  T        116  t
 21  NAK (negative acknowledge)      53  5         85  U        117  u
 22  SYN (synchronous idle)          54  6         86  V        118  v
 23  ETB (end of trans. block)       55  7         87  W        119  w
 24  CAN (cancel)                    56  8         88  X        120  x
 25  EM  (end of medium)             57  9         89  Y        121  y
 26  SUB (substitute)                58  :         90  Z        122  z
 27  ESC (escape)                    59  ;         91  [        123  {
 28  FS  (file separator)            60  <         92  \        124  |
 29  GS  (group separator)           61  =         93  ]        125  }
 30  RS  (record separator)          62  >         94  ^        126  ~
 31  US  (unit separator)            63  ?         95  _        127  DEL
```
## Окраска текста и фона
Синтаксис. Вставте нужные коды из таблиц
```bash
\033[форматирование_текста;цвет_текста;цвет_фонаm
```
```bash
printf "\033[3;36;44m Текст \033[0m\n"
```
<b>Форматирование текста</b>
<table>
    <tr>
      <th>Код</th>
      <th>Описание</th>
    </tr>
    <tr>
      <td>1</td> 
      <td>Жирный</td>
    </tr>
    <tr>
      <td>2</td>
      <td>Блёклый</td>
    </tr>
    <tr>
      <td>3</td>
      <td>Курсив</td>
    </tr>
    <tr>
      <td>4</td>
      <td>Подчёркнутый</td>
    </tr>
    <tr>
      <td>5</td>
      <td>Мигание</td>
    </tr>
    <tr>
      <td>9</td>
      <td>Зачёркнутый</td>
    </tr>
</table>

<b>Цвет текста</b>
<table>
    <tr>
      <th>Код</th>
      <th>Описание</th>
    </tr>
    <tr>
      <td>30</td> 
      <td>Чёрный</td>
    </tr>
    <tr>
      <td>31</td> 
      <td>Красный</td>
    </tr>
    <tr>
      <td>32</td>
      <td>Зелёный</td>
    </tr>
    <tr>
      <td>33</td>
      <td>Жёлтый</td>
    </tr>
    <tr>
      <td>34</td>
      <td>Синий</td>
    </tr>
    <tr>
      <td>35</td>
      <td>Фиолетовый</td>
    </tr>
    <tr>
      <td>36</td>
      <td>Бирюзовый</td>
    </tr>
    <tr>
      <td>37</td>
      <td>Белый</td>
    </tr>
</table>

<b>Фон</b>
<table>
    <tr>
      <th>Код</th>
      <th>Описание</th>
    </tr>
    <tr>
      <td>40</td> 
      <td>Чёрный</td>
    </tr>
    <tr>
      <td>41</td> 
      <td>Красный</td>
    </tr>
    <tr>
      <td>42</td>
      <td>Зелёный</td>
    </tr>
    <tr>
      <td>43</td>
      <td>Жёлтый</td>
    </tr>
    <tr>
      <td>44</td>
      <td>Синий</td>
    </tr>
    <tr>
      <td>45</td>
      <td>Фиолетовый</td>
    </tr>
    <tr>
      <td>46</td>
      <td>Бирюзовый</td>
    </tr>
    <tr>
      <td>47</td>
      <td>Белый</td>
    </tr>
</table>

[^1]

> [!NOTE]
> Useful information that users should know, even when skimming content.


[^1]: <a href="https://habr.com/ru/companies/macloud/articles/558316/">Источник</a>

# C
## Verter
Перемещаем файл `.clang-format` из папки `materials/linters` в папку со скриптом, который нужно поправить, в `src`<br>
`.clang-format` скрытый файл, для отображения скрытых файлов в <b>Finder</b> нажмите сочетание клавишь<br>
<b>&#8984; Command</b> + <b>&#8679; Shift</b> + <b>.<sup>ю</sup></b><br>
В папке со скриптом `src`, в консоли исполняем команду
```bash
clang-format -i
```

&#10060; До
```c
void input(int *a){for(int i=0;i<10;++i){scanf("%d",&a[i]);}}
```

&#9989; После
```c
void input(int *a) {
    for (int i = 0; i < 10; ++i) {
        scanf("%d", &a[i]);
    }
}
```

## Проверяем переполнение памяти

## Компиляция программы через <b>GCC</b> <b>C11</b>
```c
gcc -Wall -std=c11 -Werror -Wextra -o имя_скомпилированного_файла имя_файла.c
```
Или краткая версия
```c
gcc -Wall -std=c11 -Werror -Wextra имя_файла.c
```
При краткой версии имя скомпилированного файла будет ```a.out``` 

## Как убрать знак ```%``` в выводе консоли
Знакома ситуация, когда выполняется ваш скрипт и в конце вывода есть лишний символ, надоедливый ```%```
```bash
 Hello%
```
Убрать его можно, если добавить в последнем выводе перенос коретки

```c
printf("\n");
```


```c
if [ "$#" -ne 1 ]; then
    echo "Данный скрипт принимает 1 аргумент"
    exit 1
fi

filePath=$1
```
## FOR
```c
for(int i=0;i<10;++i){printf("%d",i)}
```

```bash
0123456789
```
