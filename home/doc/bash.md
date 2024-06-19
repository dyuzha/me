---
tags:
  - bash
---

# Standart
---
```
-a 			– Вывести все объекты.
-c 			– Произвести подсчёт.
-d 			– Указать директорию.
-e 			– Развернуть объект.
-f 			– Указать файл, из которого нужно прочитать данные.
-h 			– Вывести справку по команде.
-i 			– Игнорировать регистр символов.
-l 			– Выполнить полноформатный вывод данных.
-n 			– Использовать неинтерактивный (пакетный) режим.
-o 			– Позволяет указать файл, в который нужно перенаправить вывод.
-q 			– Выполнить скрипт в quiet-режиме.
-r 			– Обрабатывать папки и файлы рекурсивно.
-s 			– Выполнить скрипт в silent-режиме.
-v 			– Выполнить многословный вывод.
-x 			– Исключить объект.
-y 			– Ответить «yes» на все вопросы.
```
---
# Sintax

> -a или &&	– И
> -o или ||	– Или

> -eq 		    – равно
> -ne 		    – не равно
> -gt 		    – больше
> -lt 		    – меньше
> -ge 		    – больше или равно
> -le 		    – меньше или равно

>[!Example]
>```
[ "$a" -le "$b" ]

- < 			– меньше 
- <= 			– меньше
- > 			– больше 
- >= 			– больше или равно 

>[!Example]
>```
((a" < "$b"))

[[bash-2]]