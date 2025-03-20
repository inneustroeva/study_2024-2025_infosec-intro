---
## Front matter
title: "Отчет по второму этапу индивидуального проекта"
subtitle: "Установка DVWA"
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

Установить DVWA в гостевую систему Kali Linux 

# Выполнение 

Запустили терминал и перешли в каталог /var/www/html, это место где храняться файлы локального хостинга. Далее мы клонируем репозиторий DVWA с GitHub в каталог /html.

![Клонирование репозитория](image/1.png){#fig:001 width=70%}

Папке DVWA назначаем разрешение на чтенеи, запись и выполнение. Далее переходим в каталог config и просмотрели ее содержание, там оказался файл, который содержит конфигурацию DVWA по умолчанию. 

![Назначение разрешения папке на чтение запись и выполнение. Просмотр Директории](image/2.png){#fig:002 width=70%} 

Создаем копию файла с именем config.inc.php, командой ls проверяем создание копии.

![Cоздание копии](image/3.png){#fig:003 width=70%}

Далее открываем этот файл в редакторе nano, командой sudo nano config.inc.php, чтобы произвести необходимые настройки. Меняем значения db_user to userDVWA and db_password to dvwa. 

![nano редактор](image/4.png){#fig:004 width=70%}

Запускаем службу mysql и проверяем ее запуск 

![Запуск службы mysql](image/5.png){#fig:005 width=70%}

Входим в базу данных от имени суперпользователя root, далее система просит ввести пароль.Сначало мы создадим нового пользователя, используя учетные данные, которые мы создавали в файле config.inc.php. Далее предоставляем этому пользователю все права доступа к базе данных DVWA. 

![Создание нового пользователя в базе даннх и предоставление ему всех прав доступа.](image/6.png){#fig:006 width=70%}

Веб-сервер Apache установлен по уполчанию, нам не нужно устанавиливать дополнительные пакет. Переходим в каталог /etc/php/8.2/apache2. 

![Переход в каталог ](image/7.png){#fig:007 width=70%}

Открываем файл php.ini в редакторе nano и меняем значение allow_url_fopen с off на on

![nano редактор](image/8.png){#fig:008 width=70%}

Переходим к запуску службы веб-сервера Apache, и проверяем запуск. 

![Запуск службы веб-сервера](image/9.png){#fig:009 width=70%}

Переходим к запуску приложения DVWA. Переходим в браузер и переходим по ссылке на страницу DVWA.  

![Переход на страницу DVWA, через браузер](image/10.png){#fig:010 width=70%}

Далее мы входим в систему DVWA, вводим пароль и имя 

![Вход в систему DVWA](image/11.png){#fig:011 width=70%}

После успешного входа мы попали на домашнюю страницу DVWA

![Вход в систему DVWA](image/12.png){#fig:012 width=70%}

# Выводы

В ходе нашей работы, установили DVWA в гостевую систему Kali Linux 

::: {#refs}
:::
