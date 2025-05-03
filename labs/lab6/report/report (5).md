---
## Front matter
title: "отчёта по лабораторной работе 6"
subtitle: " Мандатное
 разграничение прав в Linux"
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

 Развить навыки администрирования ОС Linux. Получить первое прак
тическое знакомство с технологией SELinux1.
 Проверить работу SELinx на практике совместно с веб-сервером
 Apache.

# Выполнение лабораторной работы

От имени пользователя guest определили расширенные атрибуты файла
/home/guest/dir1/file1 

![Расширенные атрибуты](image/1.png){#fig:001 width=70%}

Установили на файл file1 права, разрешающие чтение и запись для владельца файла.

![Право на чтение и запись для владельца](image/2.png){#fig:002 width=70%} 

Попробовали установить на файл /home/guest/dir1/file1 расширенный атрибут a от имени пользователя guest, отказ в доступе

![Расширенный атрибут а от имени guest](image/3.png){#fig:003 width=70%}

Попробовали установить на файл /home/guest/dir1/file1 расширенный атрибут a от имени пользователя суперпользователя, получилось это сделать

![Расширенный атрибут от имени суперпользователя](image/4.png){#fig:004 width=70%}

От пользователя guest проверели правильность установления атрибута, все установилось правильно 

![Проверка атрибута](image/5.png){#fig:005 width=70%}

Выполнили дозапись в файл file1 слова «test»

![Дозапись в файл слова ](image/6.png){#fig:006 width=70%}

После этого выполнили чтение файла file1 командой cat /home/guest/dir1/file1

![Выполнили чтение файла](image/7.png){#fig:007 width=70%}

Попробовали файл в file1 стереть имеющуюся в нём информацию, получаем отказ

![Отказ в удалении информации в файле](image/8.png){#fig:008 width=70%}

Попробовали установить на файл file1 права, запрещающие чтение и запись для владельца файл, тоже получили отказ

![Отказ в установлении прав на файл](image/9.png){#fig:009 width=70%}

Сняли расширенный атрибут a с файла /home/guest/dirl/file1 от имени суперпользователя

![Снятие аtрибутов](image/10.png){#fig:010 width=70%}

Снова пробуем установить на файл file1 права, запрещающие чтение и запись для владельца файл, это нам удаеться, также нам доступно его перемещение.

![Доступно установление прав для файла](image/11.png){#fig:011 width=70%}

Заменили атрибут «a» атрибутом «i» 

![Замена атрибута](image/13.png){#fig:012 width=70%}

Видим, что при попытке удалить файл, нам отказанно в доступе. Также мы не можем его перемещать и изменение прав доступа тоже невозможно. Таким образом, файл можно лишь читать, в таком режиме он менее уязвим. 

![Отказ в доступе](image/15.png){#fig:013 width=70%}

# Выводы

Получили практические навыки работы в консоли с расширенными атрибутами файлов.

