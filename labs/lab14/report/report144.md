
---
## Front matter
title: "Лабораторная работа №14"
subtitle: "Партиции,файловыесистемы,
 монтирование"
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

Получить навыки создания разделов на диске и файловых систем.Получить навыки монтирования файловых систем

# Выполнение лабораторной работы

Создание виртуальных носителей(рис. [-@fig:001]).

![Создание](image/1.jpg){#fig:001 width=70%}

Получаем полномочия администратора и просматриваем перечень разделов(рис. [-@fig:002]).

![Просмотр](image/2.jpg){#fig:002 width=70%}

Делаем разметку диска, получаем справку о командах(рис. [-@fig:003]).

![Справка](image/3.jpg){#fig:003 width=70%}

Для fdisk /dev/sdb и fdisk /dev/sdс  добавляем новый раздел, создаём новый раздел.(рис. [-@fig:004]).

![Раздел](image/4.jpg){#fig:004 width=70%}

Определяем тип раздела(рис. [-@fig:005]).

![Тип](image/5.jpg){#fig:005 width=70%}

Сравнение выводов команд 
fdisk читает данные напрямую с диска, а /proc/partitions отражает текущее состояние устройств в памяти ядра.(рис. [-@fig:006]).

![Сравнение](image/6.jpg){#fig:006 width=70%}

Создаём новый раздел, создаём расширенный раздел(рис. [-@fig:007]).

![Создание](image/7.jpg){#fig:007 width=70%}

Обновляем таблицу разделов, смотри информацию о добавленных разделах(рис. [-@fig:008]).

![Просмотр](image/8.jpg){#fig:008 width=70%}

Запускаем fdisk, добавляем новый раздел, вводим код раздела(рис. [-@fig:009]).

![Добавление](image/9.jpg){#fig:009 width=70%}

Обновляем таблицу разделов, смотрим таблицу добавленных разделов, отформатируем раздел подкачки, включение вновь выделенного пространства, просмотр размера пространства подкачки(рис. [-@fig:010]).

![Просмотр](image/10.jpg){#fig:010 width=70%}

Смотрим таблицы разделов и разделы на втором добавленном вами ранее диске,  создаём раздел с помощью gdisk(рис. [-@fig:011]).

![Создание](image/11.jpg){#fig:011 width=70%}


Добавляем новый раздел, устанавливаем тип раздела и сохраняем(рис. [-@fig:012]).

![Тип](image/12.jpg){#fig:012 width=70%}


Обновляем таблицу разделов, смотрим информацию о добавленных разделах(рис. [-@fig:013]).

![Информация](image/13.jpg){#fig:013 width=70%}

Создайте файловую систему XFS, установка метки файловой системы(рис. [-@fig:014]).

![Установка](image/14.jpg){#fig:014 width=70%}

Создаём файловую систему EXT4, установки метки файловой системы в ext4disk,установка параметров монтирования по умолчанию для файловой системы(рис. [-@fig:015]).

![Установка](image/15.jpg){#fig:015 width=70%}

Создание точки монтирования для раздела, с монтирование файловой системы, проверка корректности монтирования(рис. [-@fig:016]).

![Проверка](image/16.jpg){#fig:016 width=70%}

Отмонтирование раздела, проверка(рис. [-@fig:017]).

![Проверка](image/17.jpg){#fig:017 width=70%}

Создаём точку монтирования для раздела XFS, смотрим информацию об идентификаторах блочных устройств, открываем файл(рис. [-@fig:018]).

![Информация](image/18.jpg){#fig:018 width=70%}

Редактируем файл(рис. [-@fig:019]).

![Файл](image/19.jpg){#fig:019 width=70%}

Монтируем всё, что указано  в /etc/fstab, проверка(рис. [-@fig:020]).

![Проверка](image/20.jpg){#fig:020 width=70%}

Добавляем две партиции надиск с разбиением GPT. Создаём оба раздела размером 100 MiB(рис. [-@fig:021]).

![Раздел](image/21.jpg){#fig:021 width=70%}

Один раздел должен быть отформатирован файловой системой ext4(рис. [-@fig:022]).

![Система](image/22.jpg){#fig:022 width=70%}

Настройка сервера для автоматического монтирования этих разделов. Установка раздел ext4 на /mnt/data-ext и установка пространства подкачки(рис. [-@fig:023]).

![Установка](image/23.jpg){#fig:023 width=70%}

Настройка сервера для автоматического монтирования, проверка и перезагрузка(рис. [-@fig:024]).

![Проверка](image/24.jpg){#fig:024 width=70%}


# Ответы на вопросы 

1. gdisk

2. fdisk

3. /etc/fstab

4. Опция noauto в /etc/fstab

5. mkswap

6. mount -a

7. ext2 (по умолчанию для mkfs)

8. mkfs.ext4

9. blkid




# Выводы
Мы получить навыки создания разделов на диске и файловых систем и  навыки монтирования файловых систем
