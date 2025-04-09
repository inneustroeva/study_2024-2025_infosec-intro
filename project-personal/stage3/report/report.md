---
## Front matter
title: "Отчет по 3 этапу индивидуального проекта"
subtitle: "Использование Hydra"
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

# Теоретическое введение 

-Hydra используется для подбора или взлома имени пользователя и пароля.

-Поддерживает подбор для большого набора приложений.

 Пример работы:

Исходные данные:
    
        -IP сервера 178.72.90.181;
        
        -Сервис http на стандартном 80 порту;
        
        -Для авторизации используется html форма, которая отправляет по адресу http://178.72.90.181/cgi-bin/luci методом POST запрос вида username=root&password=test_password;
        
        -В случае не удачной аутентификации пользователь наблюдает сообщение Invalid username and/or password! Please try again.


Запрос к Hydra будет выглядеть примерно так:
    
    hydra -l root -P ~/pass_lists/dedik_passes.txt -o ./hydra_result.log -f -V -s 80 178.72.90.181 http-post-form "/cgi-bin/luci:username=^USER^&password=^PASS^:Invalid username"
    
Используется http-post-form потому, что авторизация происходит по http методом post.
    
После указания этого модуля идёт строка /cgi-bin/luci:username=^USER^&password=^PASS^:Invalid username, у которой через двоеточие (:) указывается: 


        -путь до скрипта, который обрабатывает процесс аутентификации (/cgi-bin/luci);
        
        -строка, которая передаётся методом POST, в которой логин и пароль заменены на ^USER^ и ^PASS^ соответственно (username=^USER^&password=^PASS^);
        
        -строка, которая присутствует на странице при неудачной аутентификации; при её отсутствии Hydra поймёт, что мы успешно вошли (Invalid username).
  
# Цель работы

Приобретение практических навыков по использованию инструмаента Hydra взлома и подбора пороля 

# Выполнение 

Чтобы взломать пароль, нужно сначала скачать большой список часто используемых паролей, его нужно найти в открытых источниках, установила стандартный список паролей "rockyou.txt" для Kali linux и распокавала скаченный файл 

![Распаковка архива со списком паролей](image/1.png){#fig:001 width=70%}

Захажу на сайт DVWA, полученный в ходе 2 этапа индивидуального проекта. Для запроса hydra, мне понадобяться параметры Cookie c сайта 

![Сайта DVWA для Cookie ](image/2.png){#fig:002 width=70%} 

Чтобы получить информацию о о параметрах Cookies я установила расширение для браузера, теперь мы можем увидеть и скопировать параметры Cookie

![Информация о параметрах Cookie ](image/4.png){#fig:003 width=70%}

Ввожу в Hydra запрос с нужной нам информацией. Пароль подбираем для пользователя admin, используя GET-запрос с двумя параметрами Cookie: безопасность и PHPSESSID, найденными в прошлом пункте. Спустя некоторое время, появиться результат с подхлдящим паролем. 

![Результат на запрос в Hydra](image/5.png){#fig:004 width=70%}

Вводим полученные данные на сайт для проверки пароля и получаем положительный результат. Все сделано верно 

![проверка пароля](image/6.png){#fig:005 width=70%}

# Выводы

В ходе нашей работы, приобрела практические навыки по использованию инструманта Hydra для подбора паролей. 
