---
## Front matter
title: "Отчет по лабораторной работе № 3"
subtitle: "Дискреционное разграничение прав в Linux. Два пользователя"
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

Получение практических навыков работы в консоли с атрибутами файлов для групп пользователей

# Выполнение лабораторной работы

Создали второго пользователя guest2

![Создание пользователя](image/1.png){#fig:001 width=70%}

Добавили пользователя guest2 в группу guest командой:
gpasswd -a guest2 guest

![Добавлене пользователя в группу](image/2.png){#fig:002 width=70%} 

Осуществили вход в систему от двух пользователей на двух разных консолях: guest на первой консоли и guest2 на второй консоли.

![Вход в систему](image/3.png){#fig:003 width=70%}

Для обоих пользователей командой pwd определили директорию, в которой мы находимся. В данный момент мы находимся в домашней директории созданного ранее пользователя 

![команда pwd](image/4.png){#fig:004 width=70%}

Уточнили имя нашего пользователя, его группу, кто входит в неё и к каким группам принадлежит он сам. 

![Уточнение групп, имен, участников группы пользователей](image/5.png){#fig:005 width=70%}

Определили командами groups guest и groups guest2, в какие группы входят пользователи guest и guest2. Сравнили выводы команды groups с выводом команд id -Gn и id -G
![Вывод команды guest и guest2, id -Gn и id -G ](image/6.png){#fig:006 width=70%}
![Вывод команды groups guest и groups guest2](image/7.png){#fig:007 width=70%}

Посмотрели содержания файла /etc/group.
![Просмотр файла](image/8.png){#fig:008 width=70%}

От имени пользователя guest2 выполнили регистрацию пользователя guest2 в группе guest командой: newgrp guest 

![Регистрация пользователя](image/9.png){#fig:009 width=70%}

От имени пользователя guest изменили права директории /home/guest, разрешив все действия для пользователей группы:
![Изменения прав дириктории для пользователей группы](image/10.png){#fig:010 width=70%}

От имени пользователя guest сняли с директории /home/guest/dir1 все атрибуты

![Снятие всех отрибутов](image/11.png){#fig:011 width=70%}

Далее, меняя атрибуты директории и файла в ней заполним таблицу. Сравнивая ее с таблицей из предыдущей лабораторной работы мы можем наблюдать сходство. 

: Права на каталог и файл в нем {#tbl:std-dir}

| Права директории | Права файла | Создание файла | Удаление файла | Запись в файл | Чтение файла | Смена директории | Просмотр файлов в директории | Переименование файла | Смена атрибутов файла |
|----------|----------|----------|----------|----------|----------|----------|----------|----------|
| 000    | 000  | -   | -    | -   | -   | -    | -   | -   | -   |
| 010    | 000  | -   | -    | -   | -   | +    | -   | -   | -   |
| 020    | 000  | +   | +    | -   | -   | -    | -   | +   | -   |
| 030    | 000  | +   | +    | -   | -   | +    | -   | +   | -   |
| 040    | 000  | -   | -    | -   | -   | +    | -   | -   | -   |
| 050    | 000  | +   | +    | -   | -   | +    | -   | +   | -   |
| 060    | 000  | +   | +    | -   | -   | -    | +   | +   | -   |
| 070    | 000  | +   | +    | -   | -   | +    | +   | -   | -   |
| 010    | 020  | -   | -    | +   | -   | +    | -   | -   | -   |
| 020    | 020  | +   | +    | +   | -   | -    | -   | +   | -   |
| 030    | 020  | +   | +    | +   | -   | +    | -   | +   | -   |
| 040    | 020  | -   | -    | +   | -   | +    | +   | -   | +   |
| 050    | 020  | +   | +    | +   | -   | -    | +   | -   | +   |
| 060    | 020  | +   | +    | +   | -   | -    | +   | +   | +   |
| 070    | 020  | +   | +    | +   | -   | +    | +   | +   | +   |
| 010    | 040  | -   | -    | -   | -   | +    | -   | -   | -   |
| 020    | 040  | +   | +    | -   | -   | -    | -   | +   | -   |
| 030    | 040  | +   | +    | -   | -   | +    | -   | +   | -   |
| 040    | 040  | -   | -    | -   | +   | +    | -   | -   | -   |
| 050    | 040  | +   | +    | -   | +   | +    | -   | +   | -   |
| 060    | 040  | +   | +    | -   | +   | -    | +   | +   | -   |
| 070    | 040  | +   | +    | -   | +   | +    | +   | -   | -   |
| 010    | 070  | -   | -    | -   | -   | +    | -   | -   | -   |
| 020    | 070  | +   | +    | +   | +   | -    | -   | +   | -   |
| 030    | 070  | +   | +    | +   | +   | +    | -   | +   | -   |
| 040    | 070  | -   | -    | +   | +   | +    | -   | -   | -   |
| 050    | 070  | -   | -    | +   | +   | +    | +   | -   | +   |
| 060    | 070  | +   | +    | +   | -   | +    | +   | +   | +   |
| 070    | 070  | +   | +    | +   | +   | +    | +   | +   | +   |

# Выводы

Получены практические навыки работы в консоли с атрибутами файлов для групп пользователей.
