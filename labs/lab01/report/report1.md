
---
## Front matter
title: "Лабораторная работа №1"
subtitle: "Установка и конфигурация
операционной системы на виртуальную машину"
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

Целью данной работы является приобретение практических навыков
установки операционной системы на виртуальную машину,настройки ми
нимально необходимыхдлядальнейшей работы сервисов.

# Выполнение лабораторной работы

Cоздание Rocky(рис. [-@fig:001]).

![Создание](image/1.jpg){#fig:001 width=70%}

Настройки(рис. [-@fig:002]).

![настройки](image/2.jpg){#fig:002 width=70%}

Выполнение домашнего задания(рис. [-@fig:003]).

![Выполнение](image/3.jpg){#fig:003 width=70%}

Выполнение домашнего задания(рис. [-@fig:004]).

![Выполнение](image/4.jpg){#fig:004 width=70%}




# Ответы на вопросы 
1. Учётка: Логин, пароль, домашняя папка.

2. Команды: man (справка), cd (переход), ls (список), du -sh (размер), mkdir/rm (созд/удал), chmod (права), history (история).

3. ФС: Способ записи данных (ext4, NTFS).

4. Монтирование: mount.

5.Убить процесс: kill -9 PID





# Выводы
Мы приобрели практические навыки
установки операционной системы на виртуальную машину,настройки ми
нимально необходимыхдлядальнейшей работы сервисов.
