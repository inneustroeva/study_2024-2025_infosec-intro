---
## Front matter
title: "отчёта по лабораторной работе 7"
subtitle: " Элементы криптографии. Однократное гаммирование"
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

 Освоить напрактике применение режима однократного гаммирования.

# Выполнение лабораторной работы

В подтверждение выполнения задания прилагаю скриншот кода программы, написанной на языке Python.

![Программный код](image/1.jpg){#fig:001 width=70%}

Ключевым элементом этой программы является функция xortextf, которая принимает две строки для сложения. Эти строки должны иметь одинаковую длину, и программа проверяет это условие. Если длины строк различаются, выводится сообщение об ошибке. В случае успешной проверки мы поочередно применяем операцию сложения по модулю к символам строк, в результате чего получаем сумму двух строк.

# Выводы

В процессе выполнения лабораторной работы я овладела навыками шифрования и дешифрования сообщений с использованием однократного гаммирования и познакомилась с этим методом в криптографии.

