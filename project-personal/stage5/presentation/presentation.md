---
## Front matter
lang: ru-RU
title: Перезнтация по индивидуальному проект, 5 этап
subtitle: 
author:
  - Неустроева И.Н.
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 30 апреля 2025

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

# Цели 

Приобретение практических навыков по использованию инструмаента Nikto для сканирования веб-сайтов и поиска уязвимости в нем 

# Основная часть

## Знакомство с Nikto

Перед сканированием веб-серверов использовали параметр -Help, чтобы увидеть, что можно делать с этим инструментом 

![](image/1.png)

## Базовое сканирование сайта

Затем используем базовый синтексис nikto -h <IP or hostname> для классического сканирования сайта. Таким образом мы просканировали сайт rudn.ru 

![](image/2.png)

## Сканирование сайта pbc.org

Далее сканирую сайт pbs.org c SSL "nikto -h <IP or hostname> -ssl"

![](image/3.png)

## Сканирование IP-адреса с помощью ifconfig

Теперь, когда мы провели быстрое сканирование веб-сайта, можно попробовать использовать Nikto в локальной сети, чтобы найти embedded-сервера, такие как страница логина роутера или http-сервис на другой машине, который представляет из себя просто сервис без веб-сайта, Чтобы узнать IP-адрес, я буду использовать ifconfig

![](image/4.png)

## Использование IpCalc для IP-адреса

 IP-адрес, который нам нужен относиться к inet.На нем мы можем использовать ipcal Диапазон будет стоять после Network, в нашем случае это 10.0.2.255

![](image/5.png)

# Заключительная чаcть.

## Результаты

В ходе нашей работы, приобрела практические навыки по использованию инструмаента Nikto для сканирования веб-сайтов и поиска уязвимости в нем.


