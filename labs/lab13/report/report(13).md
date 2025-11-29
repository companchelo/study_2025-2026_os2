
---
## Front matter
title: "Лабораторная работа №13"
subtitle: "Фильтр пакетов"
author: "Хохлачёва Полина Дмитриевна"

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
mainfont: IBM Plex Serif
romanfont: IBM Plex Serif
sansfont: IBM Plex Sans
monofont: IBM Plex Mono
mathfont: STIX Two Math
mainfontoptions: Ligatures=Common,Ligatures=TeX,Scale=0.94
romanfontoptions: Ligatures=Common,Ligatures=TeX,Scale=0.94
sansfontoptions: Ligatures=Common,Ligatures=TeX,Scale=MatchLowercase,Scale=0.94
monofontoptions: Scale=MatchLowercase,Scale=0.94,FakeStretch=0.9
mathfontoptions:
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

 Получить навыки настройки пакетного фильтра в Linux

# Выполнение лабораторной работы

Получаем полномочия администратора, определяем текущую зону по умолчанию, определяем доступные зоны(рис. [-@fig:001]).

![Зоны](image/1.jpg){#fig:001 width=70%}

Доступные службы на моём компьютере(рис. [-@fig:002]).

![Службы](image/2.jpg){#fig:002 width=70%}

Доступные службы в текущей зоне(рис. [-@fig:003]).

![Службы](image/3.jpg){#fig:003 width=70%}

Информация, выводимая обеими командами, абсолютно идентична - нет никаких различий в отображаемых настройках firewall.(рис. [-@fig:004]).

![Информация](image/4.jpg){#fig:004 width=70%}

Добавляем сервер VNC в конфигурацию, проверяем добавился ли сервер в конфигурацию, перезапускаем службу(рис. [-@fig:005]).

![Добавление](image/5.jpg){#fig:005 width=70%}

vnc-server больше не указан, потому что  правило добавили без параметра --permanent(рис. [-@fig:006]).

![Пармет](image/6.jpg){#fig:006 width=70%}

Добавляем службу ещё раз и делаем её постоянной, проверяем наличия vnc-server в конфигурации, перезагружаем конфигурацию и смотрим конфигурацию времени выполнения(рис. [-@fig:007]).

![Добавление](image/7.jpg){#fig:007 width=70%}

Добавляем в конфигурацию порт 2022 протокола, перезагружаем конфигурацию, проверяем, что порт добавлен(рис. [-@fig:008]).

![Добавление](image/8.jpg){#fig:008 width=70%}

Открываем терминал под своей учётной записью(рис. [-@fig:009]).

![Терминал](image/9.jpg){#fig:009 width=70%}

В конфигурации выбираем "постоянная", далее в public выбираем http, https и ftp(рис. [-@fig:0010]).

![Конфигурация](image/10.jpg){#fig:010 width=70%}

Добавляем порт 2022 и протокол, чтобы добавить их в список(рис. [-@fig:0011]).

![Добавление](image/11.jpg){#fig:011 width=70%}


Перезагружаем конфигурацию и список доступных сервисов, чтобы увидеть изменения(рис. [-@fig:0012]).

![Список](image/12.jpg){#fig:012 width=70%}

#Выполнения самостоятельной работы 

Создаём конфигурацию командной строкой(рис. [-@fig:0013]).

![Создание](image/13.jpg){#fig:013 width=70%}

В графическом интерфейсе выбираем imap, pop3, smtp(рис. [-@fig:0014]).

![Выбор](image/14.jpg){#fig:014 width=70%}

Убеждаемся, что конфигурация активна и постоянна после перезагрузки(рис. [-@fig:0015]).

![Проверка](image/15.jpg){#fig:015 width=70%}


# Ответы на вопросы 

1. firewalld

2. firewall-cmd --add-port=2355/udp

3. firewall-cmd --list-all-zones

4. firewall-cmd --remove-service=vnc-server

5. firewall-cmd --reload

6. --list-all

7. firewall-cmd --zone=public --add-interface=eno1

8. В зону public (зона по умолчанию)





# Выводы
Мы получили навыки настройки пакетного фильтра в Linux
