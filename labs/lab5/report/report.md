---
## Front matter
title: "отчёта по лабораторной работе 5"
subtitle: "Дискреционное разграничение прав в Linux. Исследование влияния дополнительных атрибутов"
author: "Неустроева Ирина Николаевна"

## Generic otions
lang: ru-RU
toc-title: "Содержание"

## Bibliography
bibliography: bib/cite.bib
csl: pandoc/csl/gost-r-7-0-5-2008-numeric.csl

## Pdf output format
toc: true # Table of contents
toc-depth: 2
lof: true # List of figures
lot: true # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a4
documentclass: scrreprt
## I18n polyglossia
polyglossia-lang:
  name: russian
  options:
	- spelling=modern
	- babelshorthands=true
polyglossia-otherlangs:
  name: english
## I18n babel
babel-lang: russian
babel-otherlangs: english
## Fonts
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase,Scale=0.9
## Biblatex
biblatex: true
biblio-style: "gost-numeric"
biblatexoptions:
  - parentracker=true
  - backend=biber
  - hyperref=auto
  - language=auto
  - autolang=other*
  - citestyle=gost-numeric
## Pandoc-crossref LaTeX customization
figureTitle: "Рис."
tableTitle: "Таблица"
listingTitle: "Листинг"
lofTitle: "Список иллюстраций"
lotTitle: "Список таблиц"
lolTitle: "Листинги"
## Misc options
indent: true
header-includes:
  - \usepackage{indentfirst}
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цель работы

Изучение механизмов изменения идентификаторов, применения SetUID- и Sticky-битов. Получение практических навыков работы в консоли с дополнительными атрибутами. Рассмотрение работы механизма смены идентификатора процессов пользователей, а также влияние бита Sticky на запись и удаление файлов

# Выполнение лабораторной работы

Вошли в систему от имени пользователя guest и создали программу simpleid.с

![Создание программы simpleid.c](image/1.png){#fig:001 width=70%}

Cкомплилировали программу и убедились, что файл программы создан

![Компиляция программы и проверка на создание файла](image/2.png){#fig:002 width=70%} 

Выполнили программу simpleid.с и программу id. Вывод программ одиннаковый 

![Выполнение прграмм simpleid и id](image/3.png){#fig:003 width=70%}

Создали новую программу simpleid2.с, добавили вывод действительных идентификаторов

![Создание программы simpleid2.c](image/4.png){#fig:004 width=70%}

Скомпилировали и запустили simpleid2.c

![Запуск программы simpleid2.c](image/5.png){#fig:005 width=70%}

От имени суперпользователя выполнили команды

![Выполнение команд](image/6.png){#fig:006 width=70%}

Выполнили проверку правильности установки новых атрибутов и смены владельца файла simpleid2. Запустили simpleid2 и id

![Проверка правильности установки атрибутов и смены владельца файла. Запуск simpleid2 и id ](image/7.png){#fig:007 width=70%}

Создали программу readfile.c

![Создание программы readfile.c](image/8.png){#fig:008 width=70%}

Откомпилировали программу 

![Откомпилирование программы](image/9.png){#fig:009 width=70%}

Сменили владельца у файла readfile.c и изменили права так, чтобы только суперпользователь (root) мог прочитать его, a guest не мог

![Смена владельца у файла readfile.c](image/10.png){#fig:010 width=70%}

Проверили, что пользователь guest не может прочитать файл readfile.c

![Отказ в доступе на чтение](image/11.png){#fig:011 width=70%}

Проверели, что программа readfile прочитать файл /etc/shadow не может

![Попытка прочесть файл](image/12.png){#fig:012 width=70%}

Выяснили, что атрибут Sticky на директории /tmp установлен

![Проверка на установку атрибута](image/13.png){#fig:013 width=70%}

От имени пользователя guest создали файл file01.txt в директории /tmp со словом test

![Создание файла с текстом внутри](image/14.png){#fig:014 width=70%}

Просмотрели атрибуты у только что созданного файла и разрешили доступ на чтение и запись для категории пользователей все остальные

![Разрешение в доступе на чтение и запись для каткгории все остальные](image/15.png){#fig:015 width=70%}

От пользователя guest2 (не являющегося владельцем) получилось прочитать файл /tmp/file01.txt. Дозаписать в файл
/tmp/file01.txt слово test2 не удалось. Не получилось записать в файл /tmp/file01.txt слово test3. Не удалось удалить файл /tmp/file01.txt.

![Попытки от пользователя guest2 прочитать, дозаписать и удалить файл](image/16.png){#fig:016 width=70%}

Повысили свои права до суперпользователя и сняли атрибут t (Sticky-бит) с директории /tmp. Покинули режим суперпользователя командой

![Отказ в доступе](image/17.png){#fig:017 width=70%}

От пользователя guest2 проверили, что атрибута t нет у директории /tmp

![Проверка атрибута](image/18.png){#fig:018 width=70%}

Повторили предыдущие шаги и выяснили, что можем только прочитать файл и удалить его. 

![Повторение предыдущих шагов](image/19.png){#fig:019 width=70%}

Повысили свои права до суперпользователя и вернули атрибут t на директорию /tmp:

![Повысили свои права до суперпользователя ](image/20.png){#fig:020 width=70%}

# Выводы

Изучили механизм изменения идентификаторов, применения SetUID- и Sticky-битов. Получили практические навыки работы в консоли с дополнительными атрибутами. Рассмотрели работы механизма смены идентификатора процессов пользователей, а также влияние бита Sticky на запись и удаление файлов.


