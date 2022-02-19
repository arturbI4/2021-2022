---
# Front matter
lang: ru-RU
title: "Лабораторная работа №4"
subtitle: "Дискреционное разграничение прав в Linux. Расширенные атрибуты"
author: "Карымшаков Артур Алишерович"

# Formatting
toc-title: "Содержание"
toc: true # Table of contents
toc_depth: 2
lof: true # List of figures
lot: true # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a4paper
documentclass: scrreprt
polyglossia-lang: russian
polyglossia-otherlangs: english
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase
indent: true
pdf-engine: lualatex
header-includes:
  - \linepenalty=10 # the penalty added to the badness of each line within a paragraph (no associated penalty node) Increasing the value makes tex try to have fewer lines in the paragraph.
  - \interlinepenalty=0 # value of the penalty (node) added after each line of a paragraph.
  - \hyphenpenalty=50 # the penalty for line breaking at an automatically inserted hyphen
  - \exhyphenpenalty=50 # the penalty for line breaking at an explicit hyphen
  - \binoppenalty=700 # the penalty for breaking a line at a binary operator
  - \relpenalty=500 # the penalty for breaking a line at a relation
  - \clubpenalty=150 # extra penalty for breaking after first line of a paragraph
  - \widowpenalty=150 # extra penalty for breaking before last line of a paragraph
  - \displaywidowpenalty=50 # extra penalty for breaking before last line before a display math
  - \brokenpenalty=100 # extra penalty for page breaking after a hyphenated line
  - \predisplaypenalty=10000 # penalty for breaking before a display
  - \postdisplaypenalty=0 # penalty for breaking after a display
  - \floatingpenalty = 20000 # penalty for splitting an insertion (can only be split footnote in standard LaTeX)
  - \raggedbottom # or \flushbottom
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цель работы

Получение практических навыков работы в консоли с расширенными атрибутами файлов [1]

# Задание

1. Создать от имени пользователя файл с расширенным атрибутом \texttt{a} и выполнить ряд операций.
2. Снять расширенный атрибут \texttt{a} с файла и выполнить ряд команд
3. Заменить расширенный атрибут \texttt{a} на расширенный атрибут \texttt{i} и повторить операции.
4. Заполнить таблицу, поясняющую какие операции возможны при различных установленных атрибутах.

# Выполнение лабораторной работы

1.  От имени пользователя \texttt{guest} определил расширенные атрибуты файла \texttt{/home/guest/dir1/file1} (рис - @fig:001).

![Проверка расширенных атриюутов файла \texttt{file1}](image/1.png){ #fig:001 width=70% }

Установил командой \texttt{chmod 600 file1} на файл \texttt{file1} права, разрешающие чтение и запись для владельца файла (рис -@fig:002).

![Установка прав на чтение и запись](image/2.png){ #fig:002 width=70% }

Попробовал установить на файл \texttt{/home/guest/dir1/file1} расширенный атрибут \texttt{a} от имени пользователя \texttt{guest} с помощью команды \texttt{chattr +a /home/guest/dir1/file1} (рис -@fig:003).

![Установка расширенного атрибута \texttt{a} от имени пользователя \texttt{guest}](image/3.png){ #fig:003 width=70% }

Получил отказ от выполнения операции.  

Зашел в отдельную консоль с правами администратора. Установил расширенныйатрибут \texttt{a} на файл \texttt{/home/guest/dir1/file1} от имени суперпользователя с помощью команды \texttt{chattr +a /home/guest/dir1/file1}. (рис -@fig:004)

![Установка расширенного атрибута \texttt{a} от имени суперпользователя](image/4.png){ #fig:004 width=70% }

От имени пользователя \texttt{guest} проверил правильность установления атрибута с помощью команды \texttt{lsattr /home/guest/dir1/file1} (рис. -@fig:005)

![Проверка правильности установления атрибута \texttt{a}](image/5.png){ #fig:005 width=70% }

Выполнил дозапись в файл \texttt{file1} слова "test" командой \texttt{echo >> "test" /home/guest/dir1/file1}. Дозапись удалась. После этого выполнил чтение файла \texttt{file1} командой \texttt{cat /home/guest/dir1/file1}. (рис -@fig:006).

![Дозапись в файл и его прочтение](image/6.png){ #fig:006 width=70% }

Попробовал перезаписать имеющуюся в файле информацию командой \texttt{echo "abcd" > /home/guest/dir1/file1}. Перезаписывание информации не удалось. (рис. -@fig:008)

![Перезаписывание информации в файл](image/7_2.png){ #fig:008 width=70% }

Попробовал с помощью команды \texttt{chmod 000 file1} установить на файл \texttt{file1} права, запрещающие чтение и запись для владельца файла. Установка прав не удалась. (рис -@fig:010)

![Установка прав](image/8.png){ #fig:010 width=70% }

2. Снял расширенный атрибут \texttt{a} с файла \texttt{/home/guest/dir1/file1} от имени суперпользователя командой \texttt{chattr -a /home/guest/dir1/file1} (рис -@fig:011)

![Снятие расширенного атрибута \texttt{a} с файла](image/9_1.png){ #fig:011 width=70% }

Повторил операции, которые ранее не удавалось выполнить (рис -@fig:012, рис -@fig:013, рис -@fig:014, рис -@fig:015).

![Дозапись информации в файл](image/9_2.png){ #fig:012 width=70% }

![Перезапись информации в файле](image/9_3.png){ #fig:013 width=70% }

Все вышеприведенные на скриншотах операции удалось выполнить.

3. Повторил действия по шагам, заменив атрибут \texttt{a} на атрибут \texttt{i}
(рис -@fig:016, рис -@fig:017, рис -@fig:018, рис -@fig:019, рис -@fig:020, рис -@fig:021).

![Установление расширенного атрибута \texttt{i}. Проверка его установления](image/10_1.png){ #fig:016 width=70% }

![Дозапись информации в файл. Чтение файла](image/10_2.png){ #fig:017 width=70% }

4. Заполнил таблицу "Результат проведения операция с расширенными атрибутами" (таб. 3.1)

|Операции            |Без расширенных атрибутов|С расширенным атрибутом а|С расширенным атрибутом с|
|--------------------|-------------------------|-------------------------|-------------------------|
|Дозапись в файл     |+                        |+                        |-                        |
|Чтение файла        |+                        |+                        |+                        |
|Перезапись в файле  |+                        |-                        |-                        |
|Удаление файла      |+                        |-                        |-                        |
|Переименование файла|+                        |-                        |-                        |
|Установка прав      |+                        |-                        |-                        |


: Результат проведения операция с расширенными атрибутами

# Выводы

Получил практические навыки работы в консоли с расширенными атрибутами файлов.

# Список литературы

1. Кулябов Д. С., Королькова А. В., Геворкян М. Н. Информационная безопасность компьютерных сетей. Лабораторная работа № 4. Дискреционное разграничение прав в Linux. Расширенные атрибуты
