---
## Front matter
title: "Лабораторная работа 8"
subtitle: "Планировщики событий"
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

Получение навыков работы с планировщиками событий cron и at.

# Выполнение лабораторной работы

Получаем полномочия администратора, просматриваем статус демона crond -l и просматриваем содержимое файла конфигурации(рис. [-@fig:001]).

![Просмотр](image/1.jpg){#fig:001 width=70%}

Просматриваем список заданий и файл расписания на редактирование, также открываем файл для редактирования(рис. [-@fig:002]).

![Просмотр](image/2.jpg){#fig:002 width=70%}

Добавляем следующую строку в файл(рис. [-@fig:003]).

![Редактирование](image/3.jpg){#fig:003 width=70%}

Не выключая систему просматриваем журнал(рис. [-@fig:004]).

![Просмотр журнала](image/4.jpg){#fig:004 width=70%}

Изменяем запись в расписании(рис. [-@fig:005]).

![Изменение](image/5.jpg){#fig:005 width=70%}

Переходим в каталог, создаём в нём файл сценария и прописываем в нём следующий скрипт(рис. [-@fig:006]).

![Прописание скрипта](image/6.jpg){#fig:006 width=70%}

Перейдя в каталог, создав в нём файл с расписанием, поместили в него нужное содержимое, не выключая систему через некоторое время (2-3 часа), просмотрели журнал системы событий(рис. [-@fig:007]).

![Система событий](image/7.jpg){#fig:007 width=70%}

Получаем полномочия администратора, проверяем, что служба atd загружена и включена(рис. [-@fig:008]).

![Проверка](image/8.jpg){#fig:008 width=70%}

Планируем действие, убеждаемся, что оно запланировано и с помощью команды убеждаемся, что появилось соответствующее сообщение в указанное время(рис. [-@fig:009]).

![Сообщение](image/9.jpg){#fig:009 width=70%}

# Ответы на вопросы 

1.  Раз в 2 недели: 0 0 */14 * * команда
2.  1-го и 15-го числа в 2 часа ночи: 0 2 1,15 * * команда
3.  Каждые 2 минуты каждый день: */2 * * * * команда
4.  19 сентября ежегодно: 0 0 19 9 * команда
5.  Каждый четверг сентября ежегодно: 0 0 * 9 4 команда
6.  Для пользователя alice: sudo crontab -u alice -e.  *Пример:* sudo crontab -u alice -e откроет crontab для alice в редакторе.
7.  Запретить bob: Добавьте bob в файл /etc/cron.deny. *Пример:* echo "bob" | sudo tee -a /etc/cron.deny
8.  Выполнение при недоступности: Использовать anacron. Он запускает пропущенные задания при включении сервера.
9.  Какая команда позволяет уз (Вопрос не закончен)  Если вы имели в виду - какая команда позволяет увидеть расписание cron другого пользователя?  Ответ sudo crontab -u <username> -l






# Выводы
Мы получили  навыки  работы с планировщиками событий cron и at.
