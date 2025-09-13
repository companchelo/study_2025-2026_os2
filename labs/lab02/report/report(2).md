---
## Front matter
title: "Лабораторная работа №2"
subtitle: "Управление пользователями
 и группами"
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

Получить представление о работе с учётными записями пользователей и группами
 пользователей в операционной системетипа Linux.


# Выполнение лабораторной работы

Определяем в какую учётную запись мы входим и создаём пользователя alice(рис. [-@fig:001]).

![Определяем](image/1.png){#fig:001 width=70%}

Убеждаемся, что есть нужная строка (рис. [-@fig:002]).

![Убеждение](image/2.png){#fig:002 width=70%}

Убеждаемся, что установлен в значение yes (C-y)(рис. [-@fig:003]).

![Установленное занчение](image/3.png){#fig:003 width=70%}

Создаем каталоги и пользователя(M-w).(рис. [-@fig:004]).

![Создание](image/4.png){#fig:004 width=70%}

Работа с группами(рис. [-@fig:005]).

![Работа](image/5.png){#fig:005 width=70%}




# Выводы

 Мы получили представление о работе с учётными записями пользователей и группами
 пользователей в операционной системетипа Linux.


