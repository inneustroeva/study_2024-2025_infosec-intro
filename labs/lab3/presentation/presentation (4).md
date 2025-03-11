---
## Front matter
lang: ru-RU
title: Презентация по лабораторной работе № 3
subtitle: Дискреционное разграничение прав в Linux. Два пользователя
author:
author:
  - Неустроева И.Н.
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 11  марта 2025

## i18n babel
babel-lang: russian
babel-otherlangs: english

## Formatting pdf
toc: false
toc-title: Содержание
slide_level: 2
aspectratio: 169
section-titles: true
theme: metropolis
header-includes:
 - \metroset{progressbar=frametitle,sectionpage=progressbar,numbering=fraction}
 - '\makeatletter'
 - '\beamer@ignorenonframefalse'
 - '\makeatother'
 
 ## Fonts
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase,Scale=0.9
 
---

# Информация

## Докладчик

:::::::::::::: {.columns align=center}
::: {.column width="70%"}

  * Неустроева Ирина Николаевна
  * студентка группы НБИ 02-23
  * Российский университет дружбы народов
  * <https://inneustroeva.github.io/ru/>

:::
::::::::::::::

# Вводная часть

## Актуальность

Навыки работы с атрибутами, создание нескольких учетных записей пользователя, а также навык установки и ограничения прав доступа в ОС - неотьемлемая часть навыков специалиста в области ИТ

## Цели и задачи

Получение практических навыков работы в консоли с атрибутами файлов для групп пользователей


## Материалы и методы

- Процессор `pandoc` для входного формата Markdown
- Результирующие форматы
	- `pdf`
	- `html`
- Автоматизация процесса создания: `Makefile`

# Ход работы

## Создание нового пользователя 

Переключившись на учетную запись администратора, Создали второго пользователя guest2

![](image/1.png){#fig:001 width=40%}

## Добавлене нового пользователя в группу 

Добавили пользователя guest2 в группу guest командой: gpasswd -a guest2 guest

![](image/2.png){#fig:002 width=40%}

## Вход в систему от двух пользователей 

Осуществили вход в систему от двух пользователей на двух разных консолях: guest на первой консоли и guest2 на второй консоли.

![](image/3.png){#fig:003 width=40%}

## Уточнение, в какие группы входит пользователь 

Уточнили имя нашего пользователя, его группу, кто входит в неё и к каким группам принадлежит он сам. 

![](image/5.png){#fig:004 width=40%}

## Создание новой группы 

От имени пользователя guest2 выполнили регистрацию пользователя guest2 в группе guest командой: newgrp guest 

![](image/9.png){#fig:005 width=40%}

## Разрешения всех действий в директории для пользователей группы

От имени пользователя guest изменили права директории /home/guest, разрешив все действия для пользователей группы:

![](image/10.png){#fig:006 width=40%}

## Снятие всех атрибутов дириктории 

От имени пользователя guest сняли с директории /home/guest/dir1 все атрибуты

![](image/11.png){#fig:007 width=40%}

# Выводы

Получили практические навыки работы в консоли с атрибутами файлов для групп пользователей.
:::

