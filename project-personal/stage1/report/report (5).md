---
## Front matter
title: "Отчет по первому этапу индивидуального проекта"
subtitle: 
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

Приобретение практических навыков установки операционной системы на виртуальную машину, настройки минимально необходимых для дальнейшей работы сервисов.

# Ход работы 

1 Этап - перешли по ссылке, оставленной в разделе "Этапы реализации проекта" и установили Kali Linux

![Установка Kali Linux](image/1.png){#fig:001 width=70%}

Создаем новую виртуальную машину и производим основные настройки ( основной памяти, имени, жесткого диска)

![Основные настройки ](image/2.png){#fig:002 width=70%}

Первое, что необходимо выбрать при установке - язык.

![Выбор языка системы](image/3.png){#fig:003 width=70%}

После установщик просит выбрать местонахождение.

![Выбор локации](image/4.png){#fig:004 width=70%}

Система, предлагается выбрать раскладку клавиатуры, которая будет для системы основной. 

![Выбор раскладки клавиатуры](image/5.png){#fig:005 width=70%}

Следующий этап - конфигурация сети. Здесь необходимо выбрать имя хоста, доменное имя и создать пользователя.

![Выбор домена второго уровня](image/6.png){#fig:006 width=70%}

![Выбор домена первого уровня](image/7.png){#fig:007 width=70%}

Создаем пользователя. Вводим полное имя, затем - логин и пароль, который необходимо подтвердить дважды.

![Выбор логина](image/8.png){#fig:008 width=70%}

![Выбор пароля](image/9.png){#fig:009 width=70%}

Выбор часовой зоны

![Выбор времени системы](image/10.png){#fig:010 width=70%}

Далее идет этап установки - настройка диска и его разделов. Система предлагает использовать диск целиком 
![Этап настройки диска](image/11.png){#fig:011 width=70%}

После описанных выше настроек машина готова к работе. Она автоматически перезагружается и выводит на вход.

![Вход в систему](image/12.png){#fig:012 width=70%}

![Рабочий стол](image/13.png){#fig:013 width=70%}

# Выводы

Были приобретены практические навыки установки операционной системы на виртуальную машину и настройки минимально необходимых для дальнейшей работы сервисов.
