# Гайд по Verter
В данном руководстве я исследую вопросы:
- Почему Verter меня унижает?
- По каким кретериям Verter оценивает задания?
- Частые ошибки и их решения
- Как себя проверить перед окончанием задания?

## Схема проверки Verter
1. `Run tests` объявление о начале тестирования
2. `Quest_1` проверка квеста №1
   - `Style test` проверка кода на нормы стиля
   - `Build test` компиляция программы
   - `Test number` ~5 проверок, вводит свои значения, сравнивает ответ вашей программы с правильным ответом
3. `Quest_2` проверка квеста №2
   - `Style test` проверка кода...
   - `Build test` компиляция...
   - `Test number` ~5 проверок...
4. И так далее по следующим квестам

> [!NOTE]
> Ваша программа может пройти все тесты верно, во всех квестах, но не получит ни одного балла, если не проходит проверку стиля

## Нормы стиля или clang-format
Для соответствия нормам следует:
1. Перейти в папку репозитория `cd имя_репозитория` например `cd T06D09`
2. Перейти в папку материалов `cd materials`
3. Перейти в папку linters `cd linters`
4. Скопировать файл `.clang-format` в папку `src` для этого прописываем команду `cp .clang-format ../../src/`
5. Переходим в папку `src` для этого прописываем команду `cd ../../src`
6. Проверяем файл на соответствие нормам стиля `clang-format -n имя_файла.c`
7. Если в консоль вывелись ошибки, то запускаем автоисправление `clang-format -i имя_файла.c`
8. Если в консоли ничего не вывелось, то файл исправлен

> [!NOTE]
> Убедиться, что всё нормально, можно, запустив проверку файла заново, командой `clang-format -n имя_файла.c` в консоль ничего не должно выводиться

## Компиляция
Для компиляции программы используем ЭТУ команду с такими КЛЮЧАМИ и их ПОСЛЕДОВАТЕЛЬНОСТЬЮ

```bash
gcc -Wall -std=c11 -Werror -Wextra имя_файла.c
```

Появиться файл `a.out` - это и есть наша программа. Для её запуска выполняем команду `./a.out`

> [!NOTE]
> Если вместо компиляции выводятся ошибки в консоль, следует проверить программу на `clang-format` или синтаксические ошибки. Если не помогло, посмотри пункт <a href="#">Частые ошибки и их решения</a>

## Проверка на утечку памяти
Пока в процессе написания...

## Финальная самопроверка
Убедись, что твой проект соответствует данным критериям
1. Проект храниться в пределах каталога `src`
2. Все файлы расширением `c` прошли проверку на стиль без ошибок
```
clang-format -n *.c
```
3. Каждый файл с расширением `c` компилируются без ошибок командой
```
gcc -Wall -std=c11 -Werror -Wextra имя_файла.c
```
4. Каждая программа работает в соответствии с требованиями задания, например
   - правильно реагирует на пустой ввод
   - на ввод букв вместо цифр
   - на ввод большего числа аргументов
   - на ввод чисел с плавующей точкой и верно их округляет
   - и таких условий у задачи может быть больше...
5. Удаление лишних файлов из каталога `src`. Не забудь удалить:
   - файл `.clang-format`
   - файлы скомпилированных программ с расширением  `.out`
   - временные файлы
   - файлы, которые не просят оставить по условию задачи
6. Запушить проект в ветку `develop`

## Материалы
<details>
  <summary>Полный вывод Verter Задание T06D09</summary>

```bash
Run tests:

-------------------------------------------------------------------------------

Quest_1

Style test
Style test output:
b'/builds/pipelines/test/to/src/key9part1.c:1:39: warning: code should be clang-formatted [-Wclang-format-violations]\n/*------------------------------------\n                                      |\n/builds/pipelines/test/to/src/key9part1.c:2:39: warning: code should be clang-formatted [-Wclang-format-violations]\n        \xd0\x97\xd0\xb4\xd1\x80\xd0\xb0\xd0\xb2\xd1\x81\xd1\x82\xd0\xb2\xd1\x83\xd0\xb9, \xd1\x87\xd0\xb5\xd0\xbb\xd0\xbe\xd0\xb2\xd0\xb5\xd0\xba!\n/builds/pipelines/test/to/src/key9part1.c:3:38: warning: code should be clang-formatted [-Wclang-format-violations]\n        \xd0\xa7\xd1\x82\xd0\xbe\xd0\xb1\xd1\x8b \xd0\xbf\xd0\xbe\xd0\xbb\xd1\x83\xd1\x87\xd0\xb8\xd1\x82\xd1\x8c \xd0\xba\xd0\xbb\xd1\x8e\xd1\x87 \n/builds/pipelines/test/to/src/key9part1.c:9:11: warning: code should be clang-formatted [-Wclang-format-violations]\nvoid input (int *buffer, int *length);\n          |\n/builds/pipelines/test/to/src/key9part1.c:10:12: warning: code should be clang-formatted [-Wclang-format-violations]\nvoid output (int *buffer, int length);\n           |\n/builds/pipelines/test/to/src/key9part1.c:12:21: warning: code should be clang-formatted [-Wclang-format-violations]\nint find_numbers(int* buffer, int length, int number, int* numbers)\n                    |\n/builds/pipelines/test/to/src/key9part1.c:12:22: warning: code should be clang-formatted [-Wclang-format-violations]\nint find_numbers(int* buffer, int length, int number, int* numbers)\n                     |\n/builds/pipelines/test/to/src/key9part1.c:12:58: warning: code should be clang-formatted [-Wclang-format-violations]\nint find_numbers(int* buffer, int length, int number, int* numbers)\n                                                         |\n/builds/pipelines/test/to/src/key9part1.c:12:59: warning: code should be clang-formatted [-Wclang-format-violations]\nint find_numbers(int* buffer, int length, int number, int* numbers)\n                                                          |\n/builds/pipelines/test/to/src/key9part1.c:12:68: warning: code should be clang-formatted [-Wclang-format-violations]\nint find_numbers(int* buffer, int length, int number, int* numbers)\n                                                                   |\n/builds/pipelines/test/to/src/key9part1.c:14:39: warning: code should be clang-formatted [-Wclang-format-violations]\n/*------------------------------------\n                                      |\n/builds/pipelines/test/to/src/key9part1.c:15:59: warning: code should be clang-formatted [-Wclang-format-violations]\n        \xd0\xa4\xd1\x83\xd0\xbd\xd0\xba\xd1\x86\xd0\xb8\xd1\x8f \xd0\xbf\xd0\xbe\xd0\xbb\xd1\x83\xd1\x87\xd0\xb0\xd0\xb5\xd1\x82 \xd0\xbc\xd0\xb0\xd1\x81\xd1\x81\xd0\xb8\xd0\xb2 \xd0\xb4\xd0\xb0\xd0\xbd\xd0\xbd\xd1\x8b\xd1\x85 \n/builds/pipelines/test/to/src/key9part1.c:16:19: warning: code should be clang-formatted [-Wclang-format-violations]\n        \xd1\x87\xd0\xb5\xd1\x80\xd0\xb5\xd0\xb7 stdin.\n/builds/pipelines/test/to/src/key9part1.c:17:48: warning: code should be clang-formatted [-Wclang-format-violations]\n        \xd0\x92\xd1\x8b\xd0\xb4\xd0\xb0\xd0\xb5\xd1\x82 \xd0\xb2 stdout \xd0\xbe\xd1\x81\xd0\xbe\xd0\xb1\xd1\x83\xd1\x8e \xd1\x81\xd1\x83\xd0\xbc\xd0\xbc\xd1\x83\n/builds/pipelines/test/to/src/key9part1.c:18:46: warning: code should be clang-formatted [-Wclang-format-violations]\n        \xd0\xb8 \xd1\x81\xd1\x84\xd0\xbe\xd1\x80\xd0\xbc\xd0\xb8\xd1\x80\xd0\xbe\xd0\xb2\xd0\xb0\xd0\xbd\xd0\xbd\xd1\x8b\xd0\xb9 \xd0\xbc\xd0\xb0\xd1\x81\xd1\x81\xd0\xb8\xd0\xb2 \n/builds/pipelines/test/to/src/key9part1.c:19:43: warning: code should be clang-formatted [-Wclang-format-violations]\n        \xd1\x81\xd0\xbf\xd0\xb5\xd1\x86\xd0\xb8\xd0\xb0\xd0\xbb\xd1\x8c\xd0\xbd\xd1\x8b\xd1\x85 \xd1\x8d\xd0\xbb\xd0\xb5\xd0\xbc\xd0\xb5\xd0\xbd\xd1\x82\xd0\xbe\xd0\xb2\n/builds/pipelines/test/to/src/key9part1.c:20:71: warning: code should be clang-formatted [-Wclang-format-violations]\n        (\xd0\xb2\xd1\x8b\xd0\xb1\xd1\x80\xd0\xb0\xd0\xbd\xd0\xbd\xd1\x8b\xd1\x85 \xd1\x81 \xd0\xbf\xd0\xbe\xd0\xbc\xd0\xbe\xd1\x89\xd1\x8c\xd1\x8e \xd0\xbd\xd0\xb0\xd0\xb9\xd0\xb4\xd0\xb5\xd0\xbd\xd0\xbd\xd0\xbe\xd0\xb9 \xd1\x81\xd1\x83\xd0\xbc\xd0\xbc\xd1\x8b):\n/builds/pipelines/test/to/src/key9part1.c:21:46: warning: code should be clang-formatted [-Wclang-format-violations]\n        \xd1\x8d\xd1\x82\xd0\xbe \xd0\xb8 \xd0\xb1\xd1\x83\xd0\xb4\xd0\xb5\xd1\x82 \xd1\x87\xd0\xb0\xd1\x81\xd1\x82\xd1\x8c\xd1\x8e \xd0\xba\xd0\xbb\xd1\x8e\xd1\x87\xd0\xb0\n/builds/pipelines/test/to/src/key9part1.c:22:40: warning: code should be clang-formatted [-Wclang-format-violations]\n-------------------------------------*/\n                                       |\n/builds/pipelines/test/to/src/key9part1.c:23:11: warning: code should be clang-formatted [-Wclang-format-violations]\nint main()\n          |\n/builds/pipelines/test/to/src/key9part1.c:24:2: warning: code should be clang-formatted [-Wclang-format-violations]\n{\n |\n/builds/pipelines/test/to/src/key9part1.c:28:39: warning: code should be clang-formatted [-Wclang-format-violations]\n/*------------------------------------\n                                      |\n/builds/pipelines/test/to/src/key9part1.c:29:46: warning: code should be clang-formatted [-Wclang-format-violations]\n        \xd0\xa4\xd1\x83\xd0\xbd\xd0\xba\xd1\x86\xd0\xb8\xd1\x8f \xd0\xb4\xd0\xbe\xd0\xbb\xd0\xb6\xd0\xbd\xd0\xb0 \xd0\xbd\xd0\xb0\xd1\x85\xd0\xbe\xd0\xb4\xd0\xb8\xd1\x82\xd1\x8c\n/builds/pipelines/test/to/src/key9part1.c:30:44: warning: code should be clang-formatted [-Wclang-format-violations]\n        \xd1\x81\xd1\x83\xd0\xbc\xd0\xbc\xd1\x83 \xd1\x87\xd0\xb5\xd1\x82\xd0\xbd\xd1\x8b\xd1\x85 \xd1\x8d\xd0\xbb\xd0\xb5\xd0\xbc\xd0\xb5\xd0\xbd\xd1\x82\xd0\xbe\xd0\xb2 \n/builds/pipelines/test/to/src/key9part1.c:33:41: warning: code should be clang-formatted [-Wclang-format-violations]\nint sum_numbers(int *buffer, int length)\n                                        |\n/builds/pipelines/test/to/src/key9part1.c:34:2: warning: code should be clang-formatted [-Wclang-format-violations]\n{\n |\n/builds/pipelines/test/to/src/key9part1.c:35:14: warning: code should be clang-formatted [-Wclang-format-violations]\n        int sum = 0;\n                    |\n/builds/pipelines/test/to/src/key9part1.c:37:34: warning: code should be clang-formatted [-Wclang-format-violations]\n        for (int i = 1; i < length; i++)\n                                        |\n/builds/pipelines/test/to/src/key9part1.c:38:3: warning: code should be clang-formatted [-Wclang-format-violations]\n        {\n         |\n/builds/pipelines/test/to/src/key9part1.c:39:18: warning: code should be clang-formatted [-Wclang-format-violations]\n                if (i % 2 != 0)\n                               |\n/builds/pipelines/test/to/src/key9part1.c:40:4: warning: code should be clang-formatted [-Wclang-format-violations]\n                {\n                 |\n/builds/pipelines/test/to/src/key9part1.c:41:26: warning: code should be clang-formatted [-Wclang-format-violations]\n                        sum = sum + buffer[i];\n                                              |\n/builds/pipelines/test/to/src/key9part1.c:42:4: warning: code should be clang-formatted [-Wclang-format-violations]\n                }\n                 |\n/builds/pipelines/test/to/src/key9part1.c:43:3: warning: code should be clang-formatted [-Wclang-format-violations]\n        }\n         |\n/builds/pipelines/test/to/src/key9part1.c:48:39: warning: code should be clang-formatted [-Wclang-format-violations]\n/*------------------------------------\n                                      |\n/builds/pipelines/test/to/src/key9part1.c:49:46: warning: code should be clang-formatted [-Wclang-format-violations]\n        \xd0\xa4\xd1\x83\xd0\xbd\xd0\xba\xd1\x86\xd0\xb8\xd1\x8f \xd0\xb4\xd0\xbe\xd0\xbb\xd0\xb6\xd0\xbd\xd0\xb0 \xd0\xbd\xd0\xb0\xd1\x85\xd0\xbe\xd0\xb4\xd0\xb8\xd1\x82\xd1\x8c\n/builds/pipelines/test/to/src/key9part1.c:50:59: warning: code should be clang-formatted [-Wclang-format-violations]\n        \xd0\xb2\xd1\x81\xd0\xb5 \xd1\x8d\xd0\xbb\xd0\xb5\xd0\xbc\xd0\xb5\xd0\xbd\xd1\x82\xd1\x8b, \xd0\xbd\xd0\xb0 \xd0\xba\xd0\xbe\xd1\x82\xd0\xbe\xd1\x80\xd1\x8b\xd0\xb5 \xd0\xbd\xd0\xb0\xd1\x86\xd0\xb5\xd0\xbb\xd0\xbe\n/builds/pipelines/test/to/src/key9part1.c:51:51: warning: code should be clang-formatted [-Wclang-format-violations]\n        \xd0\xb4\xd0\xb5\xd0\xbb\xd0\xb8\xd1\x82\xd1\x81\xd1\x8f \xd0\xbf\xd0\xb5\xd1\x80\xd0\xb5\xd0\xb4\xd0\xb0\xd0\xbd\xd0\xbd\xd0\xbe\xd0\xb5 \xd1\x87\xd0\xb8\xd1\x81\xd0\xbb\xd0\xbe \xd0\xb8\n/builds/pipelines/test/to/src/key9part1.c:54:21: warning: code should be clang-formatted [-Wclang-format-violations]\nint find_numbers(int* buffer, int length, int number, int* numbers)\n                    |\n/builds/pipelines/test/to/src/key9part1.c:54:22: warning: code should be clang-formatted [-Wclang-format-violations]\nint find_numbers(int* buffer, int length, int number, int* numbers)\n                     |\n/builds/pipelines/test/to/src/key9part1.c:54:58: warning: code should be clang-formatted [-Wclang-format-violations]\nint find_numbers(int* buffer, int length, int number, int* numbers)\n                                                         |\n/builds/pipelines/test/to/src/key9part1.c:54:59: warning: code should be clang-formatted [-Wclang-format-violations]\nint find_numbers(int* buffer, int length, int number, int* numbers)\n                                                          |\n/builds/pipelines/test/to/src/key9part1.c:54:68: warning: code should be clang-formatted [-Wclang-format-violations]\nint find_numbers(int* buffer, int length, int number, int* numbers)\n                                                                   |\n/builds/pipelines/test/to/src/key9part1.c:55:2: warning: code should be clang-formatted [-Wclang-format-violations]\n{\n |\n'
Style test: FAIL 0

Style test result: 0

-------------------------------------------------------------------------------

Build output:

Project build: OK 1

Build result: 1

-------------------------------------------------------------------------------

Test number: 0, name: Quest_1

Test output: Result for test with number 0: OK 1

Test result: 0

-------------------------------------------------------------------------------

Test number: 1, name: Quest_1

Test output: Result for test with number 1: OK 1

Test result: 0

-------------------------------------------------------------------------------

Test number: 2, name: Quest_1

Test output: Result for test with number 2: OK 1

Test result: 0

-------------------------------------------------------------------------------

Test number: 3, name: Quest_1

Test output: Result for test with number 3: OK 1

Test result: 0

-------------------------------------------------------------------------------

Test number: 4, name: Quest_1

Test output: Result for test with number 4: OK 1

Test result: 0

-------------------------------------------------------------------------------

Test number: 5, name: Quest_1

Test output: Result for test with number 5: OK 1

Test result: 0

-------------------------------------------------------------------------------

Test number: 6, name: Quest_1

Test output: Result for test with number 6: OK 1

Test result: 0

-------------------------------------------------------------------------------

Test number: 7, name: Quest_1

Test output: Result for test with number 7: OK 1

Test result: 0

-------------------------------------------------------------------------------

Quest_2

Style test
Style test output:
b'/builds/pipelines/test/to/src/key9part1.c:1:39: warning: code should be clang-formatted [-Wclang-format-violations]\n/*------------------------------------\n                                      |\n/builds/pipelines/test/to/src/key9part1.c:2:39: warning: code should be clang-formatted [-Wclang-format-violations]\n        \xd0\x97\xd0\xb4\xd1\x80\xd0\xb0\xd0\xb2\xd1\x81\xd1\x82\xd0\xb2\xd1\x83\xd0\xb9, \xd1\x87\xd0\xb5\xd0\xbb\xd0\xbe\xd0\xb2\xd0\xb5\xd0\xba!\n/builds/pipelines/test/to/src/key9part1.c:3:38: warning: code should be clang-formatted [-Wclang-format-violations]\n        \xd0\xa7\xd1\x82\xd0\xbe\xd0\xb1\xd1\x8b \xd0\xbf\xd0\xbe\xd0\xbb\xd1\x83\xd1\x87\xd0\xb8\xd1\x82\xd1\x8c \xd0\xba\xd0\xbb\xd1\x8e\xd1\x87 \n/builds/pipelines/test/to/src/key9part1.c:9:11: warning: code should be clang-formatted [-Wclang-format-violations]\nvoid input (int *buffer, int *length);\n          |\n/builds/pipelines/test/to/src/key9part1.c:10:12: warning: code should be clang-formatted [-Wclang-format-violations]\nvoid output (int *buffer, int length);\n           |\n/builds/pipelines/test/to/src/key9part1.c:12:21: warning: code should be clang-formatted [-Wclang-format-violations]\nint find_numbers(int* buffer, int length, int number, int* numbers)\n                    |\n/builds/pipelines/test/to/src/key9part1.c:12:22: warning: code should be clang-formatted [-Wclang-format-violations]\nint find_numbers(int* buffer, int length, int number, int* numbers)\n                     |\n/builds/pipelines/test/to/src/key9part1.c:12:58: warning: code should be clang-formatted [-Wclang-format-violations]\nint find_numbers(int* buffer, int length, int number, int* numbers)\n                                                         |\n/builds/pipelines/test/to/src/key9part1.c:12:59: warning: code should be clang-formatted [-Wclang-format-violations]\nint find_numbers(int* buffer, int length, int number, int* numbers)\n                                                          |\n/builds/pipelines/test/to/src/key9part1.c:12:68: warning: code should be clang-formatted [-Wclang-format-violations]\nint find_numbers(int* buffer, int length, int number, int* numbers)\n                                                                   |\n/builds/pipelines/test/to/src/key9part1.c:14:39: warning: code should be clang-formatted [-Wclang-format-violations]\n/*------------------------------------\n                                      |\n/builds/pipelines/test/to/src/key9part1.c:15:59: warning: code should be clang-formatted [-Wclang-format-violations]\n        \xd0\xa4\xd1\x83\xd0\xbd\xd0\xba\xd1\x86\xd0\xb8\xd1\x8f \xd0\xbf\xd0\xbe\xd0\xbb\xd1\x83\xd1\x87\xd0\xb0\xd0\xb5\xd1\x82 \xd0\xbc\xd0\xb0\xd1\x81\xd1\x81\xd0\xb8\xd0\xb2 \xd0\xb4\xd0\xb0\xd0\xbd\xd0\xbd\xd1\x8b\xd1\x85 \n/builds/pipelines/test/to/src/key9part1.c:16:19: warning: code should be clang-formatted [-Wclang-format-violations]\n        \xd1\x87\xd0\xb5\xd1\x80\xd0\xb5\xd0\xb7 stdin.\n/builds/pipelines/test/to/src/key9part1.c:17:48: warning: code should be clang-formatted [-Wclang-format-violations]\n        \xd0\x92\xd1\x8b\xd0\xb4\xd0\xb0\xd0\xb5\xd1\x82 \xd0\xb2 stdout \xd0\xbe\xd1\x81\xd0\xbe\xd0\xb1\xd1\x83\xd1\x8e \xd1\x81\xd1\x83\xd0\xbc\xd0\xbc\xd1\x83\n/builds/pipelines/test/to/src/key9part1.c:18:46: warning: code should be clang-formatted [-Wclang-format-violations]\n        \xd0\xb8 \xd1\x81\xd1\x84\xd0\xbe\xd1\x80\xd0\xbc\xd0\xb8\xd1\x80\xd0\xbe\xd0\xb2\xd0\xb0\xd0\xbd\xd0\xbd\xd1\x8b\xd0\xb9 \xd0\xbc\xd0\xb0\xd1\x81\xd1\x81\xd0\xb8\xd0\xb2 \n/builds/pipelines/test/to/src/key9part1.c:19:43: warning: code should be clang-formatted [-Wclang-format-violations]\n        \xd1\x81\xd0\xbf\xd0\xb5\xd1\x86\xd0\xb8\xd0\xb0\xd0\xbb\xd1\x8c\xd0\xbd\xd1\x8b\xd1\x85 \xd1\x8d\xd0\xbb\xd0\xb5\xd0\xbc\xd0\xb5\xd0\xbd\xd1\x82\xd0\xbe\xd0\xb2\n/builds/pipelines/test/to/src/key9part1.c:20:71: warning: code should be clang-formatted [-Wclang-format-violations]\n        (\xd0\xb2\xd1\x8b\xd0\xb1\xd1\x80\xd0\xb0\xd0\xbd\xd0\xbd\xd1\x8b\xd1\x85 \xd1\x81 \xd0\xbf\xd0\xbe\xd0\xbc\xd0\xbe\xd1\x89\xd1\x8c\xd1\x8e \xd0\xbd\xd0\xb0\xd0\xb9\xd0\xb4\xd0\xb5\xd0\xbd\xd0\xbd\xd0\xbe\xd0\xb9 \xd1\x81\xd1\x83\xd0\xbc\xd0\xbc\xd1\x8b):\n/builds/pipelines/test/to/src/key9part1.c:21:46: warning: code should be clang-formatted [-Wclang-format-violations]\n        \xd1\x8d\xd1\x82\xd0\xbe \xd0\xb8 \xd0\xb1\xd1\x83\xd0\xb4\xd0\xb5\xd1\x82 \xd1\x87\xd0\xb0\xd1\x81\xd1\x82\xd1\x8c\xd1\x8e \xd0\xba\xd0\xbb\xd1\x8e\xd1\x87\xd0\xb0\n/builds/pipelines/test/to/src/key9part1.c:22:40: warning: code should be clang-formatted [-Wclang-format-violations]\n-------------------------------------*/\n                                       |\n/builds/pipelines/test/to/src/key9part1.c:23:11: warning: code should be clang-formatted [-Wclang-format-violations]\nint main()\n          |\n/builds/pipelines/test/to/src/key9part1.c:24:2: warning: code should be clang-formatted [-Wclang-format-violations]\n{\n |\n/builds/pipelines/test/to/src/key9part1.c:28:39: warning: code should be clang-formatted [-Wclang-format-violations]\n/*------------------------------------\n                                      |\n/builds/pipelines/test/to/src/key9part1.c:29:46: warning: code should be clang-formatted [-Wclang-format-violations]\n        \xd0\xa4\xd1\x83\xd0\xbd\xd0\xba\xd1\x86\xd0\xb8\xd1\x8f \xd0\xb4\xd0\xbe\xd0\xbb\xd0\xb6\xd0\xbd\xd0\xb0 \xd0\xbd\xd0\xb0\xd1\x85\xd0\xbe\xd0\xb4\xd0\xb8\xd1\x82\xd1\x8c\n/builds/pipelines/test/to/src/key9part1.c:30:44: warning: code should be clang-formatted [-Wclang-format-violations]\n        \xd1\x81\xd1\x83\xd0\xbc\xd0\xbc\xd1\x83 \xd1\x87\xd0\xb5\xd1\x82\xd0\xbd\xd1\x8b\xd1\x85 \xd1\x8d\xd0\xbb\xd0\xb5\xd0\xbc\xd0\xb5\xd0\xbd\xd1\x82\xd0\xbe\xd0\xb2 \n/builds/pipelines/test/to/src/key9part1.c:33:41: warning: code should be clang-formatted [-Wclang-format-violations]\nint sum_numbers(int *buffer, int length)\n                                        |\n/builds/pipelines/test/to/src/key9part1.c:34:2: warning: code should be clang-formatted [-Wclang-format-violations]\n{\n |\n/builds/pipelines/test/to/src/key9part1.c:35:14: warning: code should be clang-formatted [-Wclang-format-violations]\n        int sum = 0;\n                    |\n/builds/pipelines/test/to/src/key9part1.c:37:34: warning: code should be clang-formatted [-Wclang-format-violations]\n        for (int i = 1; i < length; i++)\n                                        |\n/builds/pipelines/test/to/src/key9part1.c:38:3: warning: code should be clang-formatted [-Wclang-format-violations]\n        {\n         |\n/builds/pipelines/test/to/src/key9part1.c:39:18: warning: code should be clang-formatted [-Wclang-format-violations]\n                if (i % 2 != 0)\n                               |\n/builds/pipelines/test/to/src/key9part1.c:40:4: warning: code should be clang-formatted [-Wclang-format-violations]\n                {\n                 |\n/builds/pipelines/test/to/src/key9part1.c:41:26: warning: code should be clang-formatted [-Wclang-format-violations]\n                        sum = sum + buffer[i];\n                                              |\n/builds/pipelines/test/to/src/key9part1.c:42:4: warning: code should be clang-formatted [-Wclang-format-violations]\n                }\n                 |\n/builds/pipelines/test/to/src/key9part1.c:43:3: warning: code should be clang-formatted [-Wclang-format-violations]\n        }\n         |\n/builds/pipelines/test/to/src/key9part1.c:48:39: warning: code should be clang-formatted [-Wclang-format-violations]\n/*------------------------------------\n                                      |\n/builds/pipelines/test/to/src/key9part1.c:49:46: warning: code should be clang-formatted [-Wclang-format-violations]\n        \xd0\xa4\xd1\x83\xd0\xbd\xd0\xba\xd1\x86\xd0\xb8\xd1\x8f \xd0\xb4\xd0\xbe\xd0\xbb\xd0\xb6\xd0\xbd\xd0\xb0 \xd0\xbd\xd0\xb0\xd1\x85\xd0\xbe\xd0\xb4\xd0\xb8\xd1\x82\xd1\x8c\n/builds/pipelines/test/to/src/key9part1.c:50:59: warning: code should be clang-formatted [-Wclang-format-violations]\n        \xd0\xb2\xd1\x81\xd0\xb5 \xd1\x8d\xd0\xbb\xd0\xb5\xd0\xbc\xd0\xb5\xd0\xbd\xd1\x82\xd1\x8b, \xd0\xbd\xd0\xb0 \xd0\xba\xd0\xbe\xd1\x82\xd0\xbe\xd1\x80\xd1\x8b\xd0\xb5 \xd0\xbd\xd0\xb0\xd1\x86\xd0\xb5\xd0\xbb\xd0\xbe\n/builds/pipelines/test/to/src/key9part1.c:51:51: warning: code should be clang-formatted [-Wclang-format-violations]\n        \xd0\xb4\xd0\xb5\xd0\xbb\xd0\xb8\xd1\x82\xd1\x81\xd1\x8f \xd0\xbf\xd0\xb5\xd1\x80\xd0\xb5\xd0\xb4\xd0\xb0\xd0\xbd\xd0\xbd\xd0\xbe\xd0\xb5 \xd1\x87\xd0\xb8\xd1\x81\xd0\xbb\xd0\xbe \xd0\xb8\n/builds/pipelines/test/to/src/key9part1.c:54:21: warning: code should be clang-formatted [-Wclang-format-violations]\nint find_numbers(int* buffer, int length, int number, int* numbers)\n                    |\n/builds/pipelines/test/to/src/key9part1.c:54:22: warning: code should be clang-formatted [-Wclang-format-violations]\nint find_numbers(int* buffer, int length, int number, int* numbers)\n                     |\n/builds/pipelines/test/to/src/key9part1.c:54:58: warning: code should be clang-formatted [-Wclang-format-violations]\nint find_numbers(int* buffer, int length, int number, int* numbers)\n                                                         |\n/builds/pipelines/test/to/src/key9part1.c:54:59: warning: code should be clang-formatted [-Wclang-format-violations]\nint find_numbers(int* buffer, int length, int number, int* numbers)\n                                                          |\n/builds/pipelines/test/to/src/key9part1.c:54:68: warning: code should be clang-formatted [-Wclang-format-violations]\nint find_numbers(int* buffer, int length, int number, int* numbers)\n                                                                   |\n/builds/pipelines/test/to/src/key9part1.c:55:2: warning: code should be clang-formatted [-Wclang-format-violations]\n{\n |\n'
Style test: FAIL 0

Style test result: 0

-------------------------------------------------------------------------------

Build output:
cc1: fatal error: /builds/pipelines/test/to/src/fast_sort.c: No such file or directory
compilation terminated.

Build failed with exit code 1. 0

Build result: 0

-------------------------------------------------------------------------------

Test output: Build fail

Test result: 0

-------------------------------------------------------------------------------

Quest_3

Style test
Style test output:
b'/builds/pipelines/test/to/src/key9part1.c:1:39: warning: code should be clang-formatted [-Wclang-format-violations]\n/*------------------------------------\n                                      |\n/builds/pipelines/test/to/src/key9part1.c:2:39: warning: code should be clang-formatted [-Wclang-format-violations]\n        \xd0\x97\xd0\xb4\xd1\x80\xd0\xb0\xd0\xb2\xd1\x81\xd1\x82\xd0\xb2\xd1\x83\xd0\xb9, \xd1\x87\xd0\xb5\xd0\xbb\xd0\xbe\xd0\xb2\xd0\xb5\xd0\xba!\n/builds/pipelines/test/to/src/key9part1.c:3:38: warning: code should be clang-formatted [-Wclang-format-violations]\n        \xd0\xa7\xd1\x82\xd0\xbe\xd0\xb1\xd1\x8b \xd0\xbf\xd0\xbe\xd0\xbb\xd1\x83\xd1\x87\xd0\xb8\xd1\x82\xd1\x8c \xd0\xba\xd0\xbb\xd1\x8e\xd1\x87 \n/builds/pipelines/test/to/src/key9part1.c:9:11: warning: code should be clang-formatted [-Wclang-format-violations]\nvoid input (int *buffer, int *length);\n          |\n/builds/pipelines/test/to/src/key9part1.c:10:12: warning: code should be clang-formatted [-Wclang-format-violations]\nvoid output (int *buffer, int length);\n           |\n/builds/pipelines/test/to/src/key9part1.c:12:21: warning: code should be clang-formatted [-Wclang-format-violations]\nint find_numbers(int* buffer, int length, int number, int* numbers)\n                    |\n/builds/pipelines/test/to/src/key9part1.c:12:22: warning: code should be clang-formatted [-Wclang-format-violations]\nint find_numbers(int* buffer, int length, int number, int* numbers)\n                     |\n/builds/pipelines/test/to/src/key9part1.c:12:58: warning: code should be clang-formatted [-Wclang-format-violations]\nint find_numbers(int* buffer, int length, int number, int* numbers)\n                                                         |\n/builds/pipelines/test/to/src/key9part1.c:12:59: warning: code should be clang-formatted [-Wclang-format-violations]\nint find_numbers(int* buffer, int length, int number, int* numbers)\n                                                          |\n/builds/pipelines/test/to/src/key9part1.c:12:68: warning: code should be clang-formatted [-Wclang-format-violations]\nint find_numbers(int* buffer, int length, int number, int* numbers)\n                                                                   |\n/builds/pipelines/test/to/src/key9part1.c:14:39: warning: code should be clang-formatted [-Wclang-format-violations]\n/*------------------------------------\n                                      |\n/builds/pipelines/test/to/src/key9part1.c:15:59: warning: code should be clang-formatted [-Wclang-format-violations]\n        \xd0\xa4\xd1\x83\xd0\xbd\xd0\xba\xd1\x86\xd0\xb8\xd1\x8f \xd0\xbf\xd0\xbe\xd0\xbb\xd1\x83\xd1\x87\xd0\xb0\xd0\xb5\xd1\x82 \xd0\xbc\xd0\xb0\xd1\x81\xd1\x81\xd0\xb8\xd0\xb2 \xd0\xb4\xd0\xb0\xd0\xbd\xd0\xbd\xd1\x8b\xd1\x85 \n/builds/pipelines/test/to/src/key9part1.c:16:19: warning: code should be clang-formatted [-Wclang-format-violations]\n        \xd1\x87\xd0\xb5\xd1\x80\xd0\xb5\xd0\xb7 stdin.\n/builds/pipelines/test/to/src/key9part1.c:17:48: warning: code should be clang-formatted [-Wclang-format-violations]\n        \xd0\x92\xd1\x8b\xd0\xb4\xd0\xb0\xd0\xb5\xd1\x82 \xd0\xb2 stdout \xd0\xbe\xd1\x81\xd0\xbe\xd0\xb1\xd1\x83\xd1\x8e \xd1\x81\xd1\x83\xd0\xbc\xd0\xbc\xd1\x83\n/builds/pipelines/test/to/src/key9part1.c:18:46: warning: code should be clang-formatted [-Wclang-format-violations]\n        \xd0\xb8 \xd1\x81\xd1\x84\xd0\xbe\xd1\x80\xd0\xbc\xd0\xb8\xd1\x80\xd0\xbe\xd0\xb2\xd0\xb0\xd0\xbd\xd0\xbd\xd1\x8b\xd0\xb9 \xd0\xbc\xd0\xb0\xd1\x81\xd1\x81\xd0\xb8\xd0\xb2 \n/builds/pipelines/test/to/src/key9part1.c:19:43: warning: code should be clang-formatted [-Wclang-format-violations]\n        \xd1\x81\xd0\xbf\xd0\xb5\xd1\x86\xd0\xb8\xd0\xb0\xd0\xbb\xd1\x8c\xd0\xbd\xd1\x8b\xd1\x85 \xd1\x8d\xd0\xbb\xd0\xb5\xd0\xbc\xd0\xb5\xd0\xbd\xd1\x82\xd0\xbe\xd0\xb2\n/builds/pipelines/test/to/src/key9part1.c:20:71: warning: code should be clang-formatted [-Wclang-format-violations]\n        (\xd0\xb2\xd1\x8b\xd0\xb1\xd1\x80\xd0\xb0\xd0\xbd\xd0\xbd\xd1\x8b\xd1\x85 \xd1\x81 \xd0\xbf\xd0\xbe\xd0\xbc\xd0\xbe\xd1\x89\xd1\x8c\xd1\x8e \xd0\xbd\xd0\xb0\xd0\xb9\xd0\xb4\xd0\xb5\xd0\xbd\xd0\xbd\xd0\xbe\xd0\xb9 \xd1\x81\xd1\x83\xd0\xbc\xd0\xbc\xd1\x8b):\n/builds/pipelines/test/to/src/key9part1.c:21:46: warning: code should be clang-formatted [-Wclang-format-violations]\n        \xd1\x8d\xd1\x82\xd0\xbe \xd0\xb8 \xd0\xb1\xd1\x83\xd0\xb4\xd0\xb5\xd1\x82 \xd1\x87\xd0\xb0\xd1\x81\xd1\x82\xd1\x8c\xd1\x8e \xd0\xba\xd0\xbb\xd1\x8e\xd1\x87\xd0\xb0\n/builds/pipelines/test/to/src/key9part1.c:22:40: warning: code should be clang-formatted [-Wclang-format-violations]\n-------------------------------------*/\n                                       |\n/builds/pipelines/test/to/src/key9part1.c:23:11: warning: code should be clang-formatted [-Wclang-format-violations]\nint main()\n          |\n/builds/pipelines/test/to/src/key9part1.c:24:2: warning: code should be clang-formatted [-Wclang-format-violations]\n{\n |\n/builds/pipelines/test/to/src/key9part1.c:28:39: warning: code should be clang-formatted [-Wclang-format-violations]\n/*------------------------------------\n                                      |\n/builds/pipelines/test/to/src/key9part1.c:29:46: warning: code should be clang-formatted [-Wclang-format-violations]\n        \xd0\xa4\xd1\x83\xd0\xbd\xd0\xba\xd1\x86\xd0\xb8\xd1\x8f \xd0\xb4\xd0\xbe\xd0\xbb\xd0\xb6\xd0\xbd\xd0\xb0 \xd0\xbd\xd0\xb0\xd1\x85\xd0\xbe\xd0\xb4\xd0\xb8\xd1\x82\xd1\x8c\n/builds/pipelines/test/to/src/key9part1.c:30:44: warning: code should be clang-formatted [-Wclang-format-violations]\n        \xd1\x81\xd1\x83\xd0\xbc\xd0\xbc\xd1\x83 \xd1\x87\xd0\xb5\xd1\x82\xd0\xbd\xd1\x8b\xd1\x85 \xd1\x8d\xd0\xbb\xd0\xb5\xd0\xbc\xd0\xb5\xd0\xbd\xd1\x82\xd0\xbe\xd0\xb2 \n/builds/pipelines/test/to/src/key9part1.c:33:41: warning: code should be clang-formatted [-Wclang-format-violations]\nint sum_numbers(int *buffer, int length)\n                                        |\n/builds/pipelines/test/to/src/key9part1.c:34:2: warning: code should be clang-formatted [-Wclang-format-violations]\n{\n |\n/builds/pipelines/test/to/src/key9part1.c:35:14: warning: code should be clang-formatted [-Wclang-format-violations]\n        int sum = 0;\n                    |\n/builds/pipelines/test/to/src/key9part1.c:37:34: warning: code should be clang-formatted [-Wclang-format-violations]\n        for (int i = 1; i < length; i++)\n                                        |\n/builds/pipelines/test/to/src/key9part1.c:38:3: warning: code should be clang-formatted [-Wclang-format-violations]\n        {\n         |\n/builds/pipelines/test/to/src/key9part1.c:39:18: warning: code should be clang-formatted [-Wclang-format-violations]\n                if (i % 2 != 0)\n                               |\n/builds/pipelines/test/to/src/key9part1.c:40:4: warning: code should be clang-formatted [-Wclang-format-violations]\n                {\n                 |\n/builds/pipelines/test/to/src/key9part1.c:41:26: warning: code should be clang-formatted [-Wclang-format-violations]\n                        sum = sum + buffer[i];\n                                              |\n/builds/pipelines/test/to/src/key9part1.c:42:4: warning: code should be clang-formatted [-Wclang-format-violations]\n                }\n                 |\n/builds/pipelines/test/to/src/key9part1.c:43:3: warning: code should be clang-formatted [-Wclang-format-violations]\n        }\n         |\n/builds/pipelines/test/to/src/key9part1.c:48:39: warning: code should be clang-formatted [-Wclang-format-violations]\n/*------------------------------------\n                                      |\n/builds/pipelines/test/to/src/key9part1.c:49:46: warning: code should be clang-formatted [-Wclang-format-violations]\n        \xd0\xa4\xd1\x83\xd0\xbd\xd0\xba\xd1\x86\xd0\xb8\xd1\x8f \xd0\xb4\xd0\xbe\xd0\xbb\xd0\xb6\xd0\xbd\xd0\xb0 \xd0\xbd\xd0\xb0\xd1\x85\xd0\xbe\xd0\xb4\xd0\xb8\xd1\x82\xd1\x8c\n/builds/pipelines/test/to/src/key9part1.c:50:59: warning: code should be clang-formatted [-Wclang-format-violations]\n        \xd0\xb2\xd1\x81\xd0\xb5 \xd1\x8d\xd0\xbb\xd0\xb5\xd0\xbc\xd0\xb5\xd0\xbd\xd1\x82\xd1\x8b, \xd0\xbd\xd0\xb0 \xd0\xba\xd0\xbe\xd1\x82\xd0\xbe\xd1\x80\xd1\x8b\xd0\xb5 \xd0\xbd\xd0\xb0\xd1\x86\xd0\xb5\xd0\xbb\xd0\xbe\n/builds/pipelines/test/to/src/key9part1.c:51:51: warning: code should be clang-formatted [-Wclang-format-violations]\n        \xd0\xb4\xd0\xb5\xd0\xbb\xd0\xb8\xd1\x82\xd1\x81\xd1\x8f \xd0\xbf\xd0\xb5\xd1\x80\xd0\xb5\xd0\xb4\xd0\xb0\xd0\xbd\xd0\xbd\xd0\xbe\xd0\xb5 \xd1\x87\xd0\xb8\xd1\x81\xd0\xbb\xd0\xbe \xd0\xb8\n/builds/pipelines/test/to/src/key9part1.c:54:21: warning: code should be clang-formatted [-Wclang-format-violations]\nint find_numbers(int* buffer, int length, int number, int* numbers)\n                    |\n/builds/pipelines/test/to/src/key9part1.c:54:22: warning: code should be clang-formatted [-Wclang-format-violations]\nint find_numbers(int* buffer, int length, int number, int* numbers)\n                     |\n/builds/pipelines/test/to/src/key9part1.c:54:58: warning: code should be clang-formatted [-Wclang-format-violations]\nint find_numbers(int* buffer, int length, int number, int* numbers)\n                                                         |\n/builds/pipelines/test/to/src/key9part1.c:54:59: warning: code should be clang-formatted [-Wclang-format-violations]\nint find_numbers(int* buffer, int length, int number, int* numbers)\n                                                          |\n/builds/pipelines/test/to/src/key9part1.c:54:68: warning: code should be clang-formatted [-Wclang-format-violations]\nint find_numbers(int* buffer, int length, int number, int* numbers)\n                                                                   |\n/builds/pipelines/test/to/src/key9part1.c:55:2: warning: code should be clang-formatted [-Wclang-format-violations]\n{\n |\n'
Style test: FAIL 0

Style test result: 0

-------------------------------------------------------------------------------

Build output:
/builds/pipelines/test/to/src/key9part1.c: In function 'find_numbers':
/builds/pipelines/test/to/src/key9part1.c:24:1: error: expected '=', ',', ';', 'asm' or '__attribute__' before '{' token
   24 | {
      | ^
/builds/pipelines/test/to/src/key9part1.c:34:1: error: expected '=', ',', ';', 'asm' or '__attribute__' before '{' token
   34 | {
      | ^
/builds/pipelines/test/to/src/key9part1.c:55:1: error: expected '=', ',', ';', 'asm' or '__attribute__' before '{' token
   55 | {
      | ^
/builds/pipelines/test/to/src/key9part1.c:58: error: expected '{' at end of input

Build failed with exit code 1. 0

Build result: 0

-------------------------------------------------------------------------------

Test output: Build fail

Test result: 0

-------------------------------------------------------------------------------

Quest_4

Style test
Style test output:
b'/builds/pipelines/test/to/src/key9part1.c:1:39: warning: code should be clang-formatted [-Wclang-format-violations]\n/*------------------------------------\n                                      |\n/builds/pipelines/test/to/src/key9part1.c:2:39: warning: code should be clang-formatted [-Wclang-format-violations]\n        \xd0\x97\xd0\xb4\xd1\x80\xd0\xb0\xd0\xb2\xd1\x81\xd1\x82\xd0\xb2\xd1\x83\xd0\xb9, \xd1\x87\xd0\xb5\xd0\xbb\xd0\xbe\xd0\xb2\xd0\xb5\xd0\xba!\n/builds/pipelines/test/to/src/key9part1.c:3:38: warning: code should be clang-formatted [-Wclang-format-violations]\n        \xd0\xa7\xd1\x82\xd0\xbe\xd0\xb1\xd1\x8b \xd0\xbf\xd0\xbe\xd0\xbb\xd1\x83\xd1\x87\xd0\xb8\xd1\x82\xd1\x8c \xd0\xba\xd0\xbb\xd1\x8e\xd1\x87 \n/builds/pipelines/test/to/src/key9part1.c:9:11: warning: code should be clang-formatted [-Wclang-format-violations]\nvoid input (int *buffer, int *length);\n          |\n/builds/pipelines/test/to/src/key9part1.c:10:12: warning: code should be clang-formatted [-Wclang-format-violations]\nvoid output (int *buffer, int length);\n           |\n/builds/pipelines/test/to/src/key9part1.c:12:21: warning: code should be clang-formatted [-Wclang-format-violations]\nint find_numbers(int* buffer, int length, int number, int* numbers)\n                    |\n/builds/pipelines/test/to/src/key9part1.c:12:22: warning: code should be clang-formatted [-Wclang-format-violations]\nint find_numbers(int* buffer, int length, int number, int* numbers)\n                     |\n/builds/pipelines/test/to/src/key9part1.c:12:58: warning: code should be clang-formatted [-Wclang-format-violations]\nint find_numbers(int* buffer, int length, int number, int* numbers)\n                                                         |\n/builds/pipelines/test/to/src/key9part1.c:12:59: warning: code should be clang-formatted [-Wclang-format-violations]\nint find_numbers(int* buffer, int length, int number, int* numbers)\n                                                          |\n/builds/pipelines/test/to/src/key9part1.c:12:68: warning: code should be clang-formatted [-Wclang-format-violations]\nint find_numbers(int* buffer, int length, int number, int* numbers)\n                                                                   |\n/builds/pipelines/test/to/src/key9part1.c:14:39: warning: code should be clang-formatted [-Wclang-format-violations]\n/*------------------------------------\n                                      |\n/builds/pipelines/test/to/src/key9part1.c:15:59: warning: code should be clang-formatted [-Wclang-format-violations]\n        \xd0\xa4\xd1\x83\xd0\xbd\xd0\xba\xd1\x86\xd0\xb8\xd1\x8f \xd0\xbf\xd0\xbe\xd0\xbb\xd1\x83\xd1\x87\xd0\xb0\xd0\xb5\xd1\x82 \xd0\xbc\xd0\xb0\xd1\x81\xd1\x81\xd0\xb8\xd0\xb2 \xd0\xb4\xd0\xb0\xd0\xbd\xd0\xbd\xd1\x8b\xd1\x85 \n/builds/pipelines/test/to/src/key9part1.c:16:19: warning: code should be clang-formatted [-Wclang-format-violations]\n        \xd1\x87\xd0\xb5\xd1\x80\xd0\xb5\xd0\xb7 stdin.\n/builds/pipelines/test/to/src/key9part1.c:17:48: warning: code should be clang-formatted [-Wclang-format-violations]\n        \xd0\x92\xd1\x8b\xd0\xb4\xd0\xb0\xd0\xb5\xd1\x82 \xd0\xb2 stdout \xd0\xbe\xd1\x81\xd0\xbe\xd0\xb1\xd1\x83\xd1\x8e \xd1\x81\xd1\x83\xd0\xbc\xd0\xbc\xd1\x83\n/builds/pipelines/test/to/src/key9part1.c:18:46: warning: code should be clang-formatted [-Wclang-format-violations]\n        \xd0\xb8 \xd1\x81\xd1\x84\xd0\xbe\xd1\x80\xd0\xbc\xd0\xb8\xd1\x80\xd0\xbe\xd0\xb2\xd0\xb0\xd0\xbd\xd0\xbd\xd1\x8b\xd0\xb9 \xd0\xbc\xd0\xb0\xd1\x81\xd1\x81\xd0\xb8\xd0\xb2 \n/builds/pipelines/test/to/src/key9part1.c:19:43: warning: code should be clang-formatted [-Wclang-format-violations]\n        \xd1\x81\xd0\xbf\xd0\xb5\xd1\x86\xd0\xb8\xd0\xb0\xd0\xbb\xd1\x8c\xd0\xbd\xd1\x8b\xd1\x85 \xd1\x8d\xd0\xbb\xd0\xb5\xd0\xbc\xd0\xb5\xd0\xbd\xd1\x82\xd0\xbe\xd0\xb2\n/builds/pipelines/test/to/src/key9part1.c:20:71: warning: code should be clang-formatted [-Wclang-format-violations]\n        (\xd0\xb2\xd1\x8b\xd0\xb1\xd1\x80\xd0\xb0\xd0\xbd\xd0\xbd\xd1\x8b\xd1\x85 \xd1\x81 \xd0\xbf\xd0\xbe\xd0\xbc\xd0\xbe\xd1\x89\xd1\x8c\xd1\x8e \xd0\xbd\xd0\xb0\xd0\xb9\xd0\xb4\xd0\xb5\xd0\xbd\xd0\xbd\xd0\xbe\xd0\xb9 \xd1\x81\xd1\x83\xd0\xbc\xd0\xbc\xd1\x8b):\n/builds/pipelines/test/to/src/key9part1.c:21:46: warning: code should be clang-formatted [-Wclang-format-violations]\n        \xd1\x8d\xd1\x82\xd0\xbe \xd0\xb8 \xd0\xb1\xd1\x83\xd0\xb4\xd0\xb5\xd1\x82 \xd1\x87\xd0\xb0\xd1\x81\xd1\x82\xd1\x8c\xd1\x8e \xd0\xba\xd0\xbb\xd1\x8e\xd1\x87\xd0\xb0\n/builds/pipelines/test/to/src/key9part1.c:22:40: warning: code should be clang-formatted [-Wclang-format-violations]\n-------------------------------------*/\n                                       |\n/builds/pipelines/test/to/src/key9part1.c:23:11: warning: code should be clang-formatted [-Wclang-format-violations]\nint main()\n          |\n/builds/pipelines/test/to/src/key9part1.c:24:2: warning: code should be clang-formatted [-Wclang-format-violations]\n{\n |\n/builds/pipelines/test/to/src/key9part1.c:28:39: warning: code should be clang-formatted [-Wclang-format-violations]\n/*------------------------------------\n                                      |\n/builds/pipelines/test/to/src/key9part1.c:29:46: warning: code should be clang-formatted [-Wclang-format-violations]\n        \xd0\xa4\xd1\x83\xd0\xbd\xd0\xba\xd1\x86\xd0\xb8\xd1\x8f \xd0\xb4\xd0\xbe\xd0\xbb\xd0\xb6\xd0\xbd\xd0\xb0 \xd0\xbd\xd0\xb0\xd1\x85\xd0\xbe\xd0\xb4\xd0\xb8\xd1\x82\xd1\x8c\n/builds/pipelines/test/to/src/key9part1.c:30:44: warning: code should be clang-formatted [-Wclang-format-violations]\n        \xd1\x81\xd1\x83\xd0\xbc\xd0\xbc\xd1\x83 \xd1\x87\xd0\xb5\xd1\x82\xd0\xbd\xd1\x8b\xd1\x85 \xd1\x8d\xd0\xbb\xd0\xb5\xd0\xbc\xd0\xb5\xd0\xbd\xd1\x82\xd0\xbe\xd0\xb2 \n/builds/pipelines/test/to/src/key9part1.c:33:41: warning: code should be clang-formatted [-Wclang-format-violations]\nint sum_numbers(int *buffer, int length)\n                                        |\n/builds/pipelines/test/to/src/key9part1.c:34:2: warning: code should be clang-formatted [-Wclang-format-violations]\n{\n |\n/builds/pipelines/test/to/src/key9part1.c:35:14: warning: code should be clang-formatted [-Wclang-format-violations]\n        int sum = 0;\n                    |\n/builds/pipelines/test/to/src/key9part1.c:37:34: warning: code should be clang-formatted [-Wclang-format-violations]\n        for (int i = 1; i < length; i++)\n                                        |\n/builds/pipelines/test/to/src/key9part1.c:38:3: warning: code should be clang-formatted [-Wclang-format-violations]\n        {\n         |\n/builds/pipelines/test/to/src/key9part1.c:39:18: warning: code should be clang-formatted [-Wclang-format-violations]\n                if (i % 2 != 0)\n                               |\n/builds/pipelines/test/to/src/key9part1.c:40:4: warning: code should be clang-formatted [-Wclang-format-violations]\n                {\n                 |\n/builds/pipelines/test/to/src/key9part1.c:41:26: warning: code should be clang-formatted [-Wclang-format-violations]\n                        sum = sum + buffer[i];\n                                              |\n/builds/pipelines/test/to/src/key9part1.c:42:4: warning: code should be clang-formatted [-Wclang-format-violations]\n                }\n                 |\n/builds/pipelines/test/to/src/key9part1.c:43:3: warning: code should be clang-formatted [-Wclang-format-violations]\n        }\n         |\n/builds/pipelines/test/to/src/key9part1.c:48:39: warning: code should be clang-formatted [-Wclang-format-violations]\n/*------------------------------------\n                                      |\n/builds/pipelines/test/to/src/key9part1.c:49:46: warning: code should be clang-formatted [-Wclang-format-violations]\n        \xd0\xa4\xd1\x83\xd0\xbd\xd0\xba\xd1\x86\xd0\xb8\xd1\x8f \xd0\xb4\xd0\xbe\xd0\xbb\xd0\xb6\xd0\xbd\xd0\xb0 \xd0\xbd\xd0\xb0\xd1\x85\xd0\xbe\xd0\xb4\xd0\xb8\xd1\x82\xd1\x8c\n/builds/pipelines/test/to/src/key9part1.c:50:59: warning: code should be clang-formatted [-Wclang-format-violations]\n        \xd0\xb2\xd1\x81\xd0\xb5 \xd1\x8d\xd0\xbb\xd0\xb5\xd0\xbc\xd0\xb5\xd0\xbd\xd1\x82\xd1\x8b, \xd0\xbd\xd0\xb0 \xd0\xba\xd0\xbe\xd1\x82\xd0\xbe\xd1\x80\xd1\x8b\xd0\xb5 \xd0\xbd\xd0\xb0\xd1\x86\xd0\xb5\xd0\xbb\xd0\xbe\n/builds/pipelines/test/to/src/key9part1.c:51:51: warning: code should be clang-formatted [-Wclang-format-violations]\n        \xd0\xb4\xd0\xb5\xd0\xbb\xd0\xb8\xd1\x82\xd1\x81\xd1\x8f \xd0\xbf\xd0\xb5\xd1\x80\xd0\xb5\xd0\xb4\xd0\xb0\xd0\xbd\xd0\xbd\xd0\xbe\xd0\xb5 \xd1\x87\xd0\xb8\xd1\x81\xd0\xbb\xd0\xbe \xd0\xb8\n/builds/pipelines/test/to/src/key9part1.c:54:21: warning: code should be clang-formatted [-Wclang-format-violations]\nint find_numbers(int* buffer, int length, int number, int* numbers)\n                    |\n/builds/pipelines/test/to/src/key9part1.c:54:22: warning: code should be clang-formatted [-Wclang-format-violations]\nint find_numbers(int* buffer, int length, int number, int* numbers)\n                     |\n/builds/pipelines/test/to/src/key9part1.c:54:58: warning: code should be clang-formatted [-Wclang-format-violations]\nint find_numbers(int* buffer, int length, int number, int* numbers)\n                                                         |\n/builds/pipelines/test/to/src/key9part1.c:54:59: warning: code should be clang-formatted [-Wclang-format-violations]\nint find_numbers(int* buffer, int length, int number, int* numbers)\n                                                          |\n/builds/pipelines/test/to/src/key9part1.c:54:68: warning: code should be clang-formatted [-Wclang-format-violations]\nint find_numbers(int* buffer, int length, int number, int* numbers)\n                                                                   |\n/builds/pipelines/test/to/src/key9part1.c:55:2: warning: code should be clang-formatted [-Wclang-format-violations]\n{\n |\n'
Style test: FAIL 0

Style test result: 0

-------------------------------------------------------------------------------

Build output:
cc1: fatal error: /builds/pipelines/test/to/src/cycle_shift.c: No such file or directory
compilation terminated.

Build failed with exit code 1. 0

Build result: 0

-------------------------------------------------------------------------------

Test output: Build fail

Test result: 0

-------------------------------------------------------------------------------

Quest_5

Style test
Style test output:
b'/builds/pipelines/test/to/src/key9part1.c:1:39: warning: code should be clang-formatted [-Wclang-format-violations]\n/*------------------------------------\n                                      |\n/builds/pipelines/test/to/src/key9part1.c:2:39: warning: code should be clang-formatted [-Wclang-format-violations]\n        \xd0\x97\xd0\xb4\xd1\x80\xd0\xb0\xd0\xb2\xd1\x81\xd1\x82\xd0\xb2\xd1\x83\xd0\xb9, \xd1\x87\xd0\xb5\xd0\xbb\xd0\xbe\xd0\xb2\xd0\xb5\xd0\xba!\n/builds/pipelines/test/to/src/key9part1.c:3:38: warning: code should be clang-formatted [-Wclang-format-violations]\n        \xd0\xa7\xd1\x82\xd0\xbe\xd0\xb1\xd1\x8b \xd0\xbf\xd0\xbe\xd0\xbb\xd1\x83\xd1\x87\xd0\xb8\xd1\x82\xd1\x8c \xd0\xba\xd0\xbb\xd1\x8e\xd1\x87 \n/builds/pipelines/test/to/src/key9part1.c:9:11: warning: code should be clang-formatted [-Wclang-format-violations]\nvoid input (int *buffer, int *length);\n          |\n/builds/pipelines/test/to/src/key9part1.c:10:12: warning: code should be clang-formatted [-Wclang-format-violations]\nvoid output (int *buffer, int length);\n           |\n/builds/pipelines/test/to/src/key9part1.c:12:21: warning: code should be clang-formatted [-Wclang-format-violations]\nint find_numbers(int* buffer, int length, int number, int* numbers)\n                    |\n/builds/pipelines/test/to/src/key9part1.c:12:22: warning: code should be clang-formatted [-Wclang-format-violations]\nint find_numbers(int* buffer, int length, int number, int* numbers)\n                     |\n/builds/pipelines/test/to/src/key9part1.c:12:58: warning: code should be clang-formatted [-Wclang-format-violations]\nint find_numbers(int* buffer, int length, int number, int* numbers)\n                                                         |\n/builds/pipelines/test/to/src/key9part1.c:12:59: warning: code should be clang-formatted [-Wclang-format-violations]\nint find_numbers(int* buffer, int length, int number, int* numbers)\n                                                          |\n/builds/pipelines/test/to/src/key9part1.c:12:68: warning: code should be clang-formatted [-Wclang-format-violations]\nint find_numbers(int* buffer, int length, int number, int* numbers)\n                                                                   |\n/builds/pipelines/test/to/src/key9part1.c:14:39: warning: code should be clang-formatted [-Wclang-format-violations]\n/*------------------------------------\n                                      |\n/builds/pipelines/test/to/src/key9part1.c:15:59: warning: code should be clang-formatted [-Wclang-format-violations]\n        \xd0\xa4\xd1\x83\xd0\xbd\xd0\xba\xd1\x86\xd0\xb8\xd1\x8f \xd0\xbf\xd0\xbe\xd0\xbb\xd1\x83\xd1\x87\xd0\xb0\xd0\xb5\xd1\x82 \xd0\xbc\xd0\xb0\xd1\x81\xd1\x81\xd0\xb8\xd0\xb2 \xd0\xb4\xd0\xb0\xd0\xbd\xd0\xbd\xd1\x8b\xd1\x85 \n/builds/pipelines/test/to/src/key9part1.c:16:19: warning: code should be clang-formatted [-Wclang-format-violations]\n        \xd1\x87\xd0\xb5\xd1\x80\xd0\xb5\xd0\xb7 stdin.\n/builds/pipelines/test/to/src/key9part1.c:17:48: warning: code should be clang-formatted [-Wclang-format-violations]\n        \xd0\x92\xd1\x8b\xd0\xb4\xd0\xb0\xd0\xb5\xd1\x82 \xd0\xb2 stdout \xd0\xbe\xd1\x81\xd0\xbe\xd0\xb1\xd1\x83\xd1\x8e \xd1\x81\xd1\x83\xd0\xbc\xd0\xbc\xd1\x83\n/builds/pipelines/test/to/src/key9part1.c:18:46: warning: code should be clang-formatted [-Wclang-format-violations]\n        \xd0\xb8 \xd1\x81\xd1\x84\xd0\xbe\xd1\x80\xd0\xbc\xd0\xb8\xd1\x80\xd0\xbe\xd0\xb2\xd0\xb0\xd0\xbd\xd0\xbd\xd1\x8b\xd0\xb9 \xd0\xbc\xd0\xb0\xd1\x81\xd1\x81\xd0\xb8\xd0\xb2 \n/builds/pipelines/test/to/src/key9part1.c:19:43: warning: code should be clang-formatted [-Wclang-format-violations]\n        \xd1\x81\xd0\xbf\xd0\xb5\xd1\x86\xd0\xb8\xd0\xb0\xd0\xbb\xd1\x8c\xd0\xbd\xd1\x8b\xd1\x85 \xd1\x8d\xd0\xbb\xd0\xb5\xd0\xbc\xd0\xb5\xd0\xbd\xd1\x82\xd0\xbe\xd0\xb2\n/builds/pipelines/test/to/src/key9part1.c:20:71: warning: code should be clang-formatted [-Wclang-format-violations]\n        (\xd0\xb2\xd1\x8b\xd0\xb1\xd1\x80\xd0\xb0\xd0\xbd\xd0\xbd\xd1\x8b\xd1\x85 \xd1\x81 \xd0\xbf\xd0\xbe\xd0\xbc\xd0\xbe\xd1\x89\xd1\x8c\xd1\x8e \xd0\xbd\xd0\xb0\xd0\xb9\xd0\xb4\xd0\xb5\xd0\xbd\xd0\xbd\xd0\xbe\xd0\xb9 \xd1\x81\xd1\x83\xd0\xbc\xd0\xbc\xd1\x8b):\n/builds/pipelines/test/to/src/key9part1.c:21:46: warning: code should be clang-formatted [-Wclang-format-violations]\n        \xd1\x8d\xd1\x82\xd0\xbe \xd0\xb8 \xd0\xb1\xd1\x83\xd0\xb4\xd0\xb5\xd1\x82 \xd1\x87\xd0\xb0\xd1\x81\xd1\x82\xd1\x8c\xd1\x8e \xd0\xba\xd0\xbb\xd1\x8e\xd1\x87\xd0\xb0\n/builds/pipelines/test/to/src/key9part1.c:22:40: warning: code should be clang-formatted [-Wclang-format-violations]\n-------------------------------------*/\n                                       |\n/builds/pipelines/test/to/src/key9part1.c:23:11: warning: code should be clang-formatted [-Wclang-format-violations]\nint main()\n          |\n/builds/pipelines/test/to/src/key9part1.c:24:2: warning: code should be clang-formatted [-Wclang-format-violations]\n{\n |\n/builds/pipelines/test/to/src/key9part1.c:28:39: warning: code should be clang-formatted [-Wclang-format-violations]\n/*------------------------------------\n                                      |\n/builds/pipelines/test/to/src/key9part1.c:29:46: warning: code should be clang-formatted [-Wclang-format-violations]\n        \xd0\xa4\xd1\x83\xd0\xbd\xd0\xba\xd1\x86\xd0\xb8\xd1\x8f \xd0\xb4\xd0\xbe\xd0\xbb\xd0\xb6\xd0\xbd\xd0\xb0 \xd0\xbd\xd0\xb0\xd1\x85\xd0\xbe\xd0\xb4\xd0\xb8\xd1\x82\xd1\x8c\n/builds/pipelines/test/to/src/key9part1.c:30:44: warning: code should be clang-formatted [-Wclang-format-violations]\n        \xd1\x81\xd1\x83\xd0\xbc\xd0\xbc\xd1\x83 \xd1\x87\xd0\xb5\xd1\x82\xd0\xbd\xd1\x8b\xd1\x85 \xd1\x8d\xd0\xbb\xd0\xb5\xd0\xbc\xd0\xb5\xd0\xbd\xd1\x82\xd0\xbe\xd0\xb2 \n/builds/pipelines/test/to/src/key9part1.c:33:41: warning: code should be clang-formatted [-Wclang-format-violations]\nint sum_numbers(int *buffer, int length)\n                                        |\n/builds/pipelines/test/to/src/key9part1.c:34:2: warning: code should be clang-formatted [-Wclang-format-violations]\n{\n |\n/builds/pipelines/test/to/src/key9part1.c:35:14: warning: code should be clang-formatted [-Wclang-format-violations]\n        int sum = 0;\n                    |\n/builds/pipelines/test/to/src/key9part1.c:37:34: warning: code should be clang-formatted [-Wclang-format-violations]\n        for (int i = 1; i < length; i++)\n                                        |\n/builds/pipelines/test/to/src/key9part1.c:38:3: warning: code should be clang-formatted [-Wclang-format-violations]\n        {\n         |\n/builds/pipelines/test/to/src/key9part1.c:39:18: warning: code should be clang-formatted [-Wclang-format-violations]\n                if (i % 2 != 0)\n                               |\n/builds/pipelines/test/to/src/key9part1.c:40:4: warning: code should be clang-formatted [-Wclang-format-violations]\n                {\n                 |\n/builds/pipelines/test/to/src/key9part1.c:41:26: warning: code should be clang-formatted [-Wclang-format-violations]\n                        sum = sum + buffer[i];\n                                              |\n/builds/pipelines/test/to/src/key9part1.c:42:4: warning: code should be clang-formatted [-Wclang-format-violations]\n                }\n                 |\n/builds/pipelines/test/to/src/key9part1.c:43:3: warning: code should be clang-formatted [-Wclang-format-violations]\n        }\n         |\n/builds/pipelines/test/to/src/key9part1.c:48:39: warning: code should be clang-formatted [-Wclang-format-violations]\n/*------------------------------------\n                                      |\n/builds/pipelines/test/to/src/key9part1.c:49:46: warning: code should be clang-formatted [-Wclang-format-violations]\n        \xd0\xa4\xd1\x83\xd0\xbd\xd0\xba\xd1\x86\xd0\xb8\xd1\x8f \xd0\xb4\xd0\xbe\xd0\xbb\xd0\xb6\xd0\xbd\xd0\xb0 \xd0\xbd\xd0\xb0\xd1\x85\xd0\xbe\xd0\xb4\xd0\xb8\xd1\x82\xd1\x8c\n/builds/pipelines/test/to/src/key9part1.c:50:59: warning: code should be clang-formatted [-Wclang-format-violations]\n        \xd0\xb2\xd1\x81\xd0\xb5 \xd1\x8d\xd0\xbb\xd0\xb5\xd0\xbc\xd0\xb5\xd0\xbd\xd1\x82\xd1\x8b, \xd0\xbd\xd0\xb0 \xd0\xba\xd0\xbe\xd1\x82\xd0\xbe\xd1\x80\xd1\x8b\xd0\xb5 \xd0\xbd\xd0\xb0\xd1\x86\xd0\xb5\xd0\xbb\xd0\xbe\n/builds/pipelines/test/to/src/key9part1.c:51:51: warning: code should be clang-formatted [-Wclang-format-violations]\n        \xd0\xb4\xd0\xb5\xd0\xbb\xd0\xb8\xd1\x82\xd1\x81\xd1\x8f \xd0\xbf\xd0\xb5\xd1\x80\xd0\xb5\xd0\xb4\xd0\xb0\xd0\xbd\xd0\xbd\xd0\xbe\xd0\xb5 \xd1\x87\xd0\xb8\xd1\x81\xd0\xbb\xd0\xbe \xd0\xb8\n/builds/pipelines/test/to/src/key9part1.c:54:21: warning: code should be clang-formatted [-Wclang-format-violations]\nint find_numbers(int* buffer, int length, int number, int* numbers)\n                    |\n/builds/pipelines/test/to/src/key9part1.c:54:22: warning: code should be clang-formatted [-Wclang-format-violations]\nint find_numbers(int* buffer, int length, int number, int* numbers)\n                     |\n/builds/pipelines/test/to/src/key9part1.c:54:58: warning: code should be clang-formatted [-Wclang-format-violations]\nint find_numbers(int* buffer, int length, int number, int* numbers)\n                                                         |\n/builds/pipelines/test/to/src/key9part1.c:54:59: warning: code should be clang-formatted [-Wclang-format-violations]\nint find_numbers(int* buffer, int length, int number, int* numbers)\n                                                          |\n/builds/pipelines/test/to/src/key9part1.c:54:68: warning: code should be clang-formatted [-Wclang-format-violations]\nint find_numbers(int* buffer, int length, int number, int* numbers)\n                                                                   |\n/builds/pipelines/test/to/src/key9part1.c:55:2: warning: code should be clang-formatted [-Wclang-format-violations]\n{\n |\n'
Style test: FAIL 0

Style test result: 0

-------------------------------------------------------------------------------

Build output:

Project build: OK 1

Build result: 1

-------------------------------------------------------------------------------

Test number: 29, name: Quest_5

Test output: Result for test with number 29: FAIL 0

Test result: 0

-------------------------------------------------------------------------------

Test number: 30, name: Quest_5

Test output: Result for test with number 30: FAIL 0

Test result: 0

-------------------------------------------------------------------------------

Test number: 31, name: Quest_5

Test output: Result for test with number 31: FAIL 0

Test result: 0

-------------------------------------------------------------------------------

Test number: 32, name: Quest_5

Test output: Result for test with number 32: FAIL 0

Test result: 0

-------------------------------------------------------------------------------

Test number: 33, name: Quest_5

Test output: Result for test with number 33: FAIL 0

Test result: 0

-------------------------------------------------------------------------------

Test number: 34, name: Quest_5

Test output: Result for test with number 34: FAIL 0

Test result: 0

-------------------------------------------------------------------------------

Test number: 35, name: Quest_5

Test output: Result for test with number 35: FAIL 0

Test result: 0

-------------------------------------------------------------------------------

Test number: 36, name: Quest_5

Test output: Result for test with number 36: FAIL 0

Test result: 0

-------------------------------------------------------------------------------

Test number: 37, name: Quest_5

Test output: Result for test with number 37: FAIL 0

Test result: 0

-------------------------------------------------------------------------------




Failed (0 XP, 0%)
Project failed

```

</details>

<details>
  <summary>Сокращённый вывод Verter Задание T06D09</summary>

```bash
Run tests:
-------------------------------------------------------------------------------
Quest_1

Style test: FAIL 0
-------------------------------------------------------------------------------
Project build: OK 1
-------------------------------------------------------------------------------

Test 0 - OK 1
Test 1 - OK 1
Test 2 - OK 1
Test 3 - OK 1
Test 4 - OK 1
Test 5 - OK 1
Test 6 - OK 1
Test 7 - OK 1

-------------------------------------------------------------------------------

Quest_2

Style test
Style test output:
b'key9part1.c:1:39: warning: code should be clang-formatted [-Wclang-format-violations]'
Style test: FAIL 0

Style test result: 0

-------------------------------------------------------------------------------

Build output:
cc1: fatal error: /builds/pipelines/test/to/src/fast_sort.c: No such file or directory
compilation terminated.

Build failed with exit code 1. 0
Build result: 0
-------------------------------------------------------------------------------
Test output: Build fail
Test result: 0
-------------------------------------------------------------------------------
Quest_3
Style test
Style test output:
b'key9part1.c:1:39: warning: code should be clang-formatted [-Wclang-format-violations]'
Style test: FAIL 0
Style test result: 0
-------------------------------------------------------------------------------
Build output:
/builds/pipelines/test/to/src/key9part1.c: In function 'find_numbers':
/builds/pipelines/test/to/src/key9part1.c:24:1: error: expected '=', ',', ';', 'asm' or '__attribute__' before '{' token
   24 | {
      | ^
/builds/pipelines/test/to/src/key9part1.c:34:1: error: expected '=', ',', ';', 'asm' or '__attribute__' before '{' token
   34 | {
      | ^
/builds/pipelines/test/to/src/key9part1.c:55:1: error: expected '=', ',', ';', 'asm' or '__attribute__' before '{' token
   55 | {
      | ^
/builds/pipelines/test/to/src/key9part1.c:58: error: expected '{' at end of input

Build failed with exit code 1. 0
Build result: 0
-------------------------------------------------------------------------------
Test output: Build fail
Test result: 0
-------------------------------------------------------------------------------
Quest_4
Style test
Style test output:
b'key9part1.c:1:39: warning: code should be clang-formatted [-Wclang-format-violations]'
Style test: FAIL 0
Style test result: 0
-------------------------------------------------------------------------------
Build output:
cc1: fatal error: /builds/pipelines/test/to/src/cycle_shift.c: No such file or directory
compilation terminated.
Build failed with exit code 1. 0
Build result: 0
-------------------------------------------------------------------------------
Test output: Build fail
Test result: 0
-------------------------------------------------------------------------------
Quest_5
Style test
Style test output:
b'key9part1.c:1:39: warning: code should be clang-formatted [-Wclang-format-violations]'
Style test: FAIL 0
Style test result: 0
-------------------------------------------------------------------------------
Build output:
Project build: OK 1
Build result: 1
-------------------------------------------------------------------------------
Test number: 29, name: Quest_5
Test output: Result for test with number 29: FAIL 0
Test result: 0
-------------------------------------------------------------------------------
Test number: 30, name: Quest_5
Test output: Result for test with number 30: FAIL 0
Test result: 0
-------------------------------------------------------------------------------
Test number: 31, name: Quest_5
Test output: Result for test with number 31: FAIL 0
Test result: 0
-------------------------------------------------------------------------------
Test number: 32, name: Quest_5
Test output: Result for test with number 32: FAIL 0
Test result: 0
-------------------------------------------------------------------------------
Test number: 33, name: Quest_5
Test output: Result for test with number 33: FAIL 0
Test result: 0
-------------------------------------------------------------------------------
Test number: 34, name: Quest_5
Test output: Result for test with number 34: FAIL 0
Test result: 0
-------------------------------------------------------------------------------
Test number: 35, name: Quest_5
Test output: Result for test with number 35: FAIL 0
Test result: 0
-------------------------------------------------------------------------------
Test number: 36, name: Quest_5
Test output: Result for test with number 36: FAIL 0
Test result: 0
-------------------------------------------------------------------------------
Test number: 37, name: Quest_5
Test output: Result for test with number 37: FAIL 0
Test result: 0
-------------------------------------------------------------------------------
Failed (0 XP, 0%)
Project failed

```

</details>
