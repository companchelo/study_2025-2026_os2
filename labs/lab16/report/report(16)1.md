
---
## Front matter
title: "Лабораторная работа №16"
subtitle: "Программный RAID"
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

Освоить работу с RAID-массивами при помощи утилиты mdadm.

# Выполнение лабораторной работы

Получаем полномочия администратора, проверка наличие дисков, создание разделов на каждом диске(рис. [-@fig:001]).

![Создание](image/1.jpg){#fig:001 width=70%}

Разделы имеют тип 83 (стандартный Linux).(рис. [-@fig:002]).

![Разделы](image/2.jpg){#fig:002 width=70%}

Диски /dev/sdd, /dev/sde, /dev/sdf по 512 МБ, на каждом создан раздел типа fd (Linux RAID),занимают всё пространство диска (511 МБ)(рис. [-@fig:003]).

![Диски](image/3.jpg){#fig:003 width=70%}

Создаём массив, проверяем состояние массива(рис. [-@fig:004]).

![Состояние](image/4.jpg){#fig:004 width=70%}

Добавление записи(рис. [-@fig:005]).

![Добавление](image/5.jpg){#fig:005 width=70%}

Подмонтируем, добавляем запись, имитируем сбой. удаление сбойного диска, заменяем диск в массиве, удаляем массив и очищаем метаданные(рис. [-@fig:006]).

![Сбой](image/6.jpg){#fig:006 width=70%}

Создайте массив RAID 1 из двух дисков, добавляем третий диск,(рис. [-@fig:007]).

![Массив](image/7.jpg){#fig:007 width=70%}

RAID 1 /dev/md0:
Работает на 2 из 3 дисков,/dev/sde1 — сбойный,Состояние: Clean (данные доступны),Размер: 510 МБ(рис. [-@fig:008]).

![Описание](image/8.jpg){#fig:008 width=70%}

Сымитируем сбой одного из дисков, проверяем состояние, удаляем массив(рис. [-@fig:009]).

![Состояние](image/9.jpg){#fig:009 width=70%}

Создаём массив RAID 1 из двух дисков, добавляем третий диск, подмонтирование(рис. [-@fig:010]).

![Создание](image/10.jpg){#fig:010 width=70%}

RAID 1 работает нормально, есть запасной диск на случай сбоя.(рис. [-@fig:011]).

![Работа](image/11.jpg){#fig:011 width=70%}


Изменяем тип массива RAID, 
Состояние массива /dev/md0:Тип изменён: с RAID 1 → RAID 5,Диски: 2 активных, 1 запасной (всего 3),Состояние: Clean (работоспособен),Размер: 510 МБ (остался прежним),RAID 5 с 2 активными дисками: Эффективность как у RAID 0 (нет избыточности),Для полноценного RAID 5 нужно минимум 3 активных диска(рис. [-@fig:012]).

![Описание](image/12.jpg){#fig:012 width=70%}

Состояние массива /dev/md0:Тип: RAID 5,Активные диски: 2 (/dev/sdd1, /dev/sde1),Запасной диск: 1 (/dev/sdf1),Состояние: Clean (работоспособен),Размер: 510 МБ(рис. [-@fig:013]).

![Оптсание](image/13.jpg){#fig:013 width=70%}

Удаляем массив и очищаем метаданные(рис. [-@fig:014]).

![Удаление](image/14.jpg){#fig:014 width=70%}

Закомментирование записи в /etc/fstab(рис. [-@fig:015]).

![Запись](image/15.jpg){#fig:015 width=70%}




# Ответы на вопросы 
1. RAID — объединение дисков в массив для повышения скорости/надёжности.

2. Основные типы: RAID 0, 1, 5, 6, 10, 50, 60.

3. RAID 0 — скорость, нет надёжности.

RAID 1 — зеркало, надёжность, 50% потерь ёмкости.

RAID 5 — чередование с чётностью, 1 диск на отказ.

RAID 6 — два диска на отказ, для критичных данных.





# Выводы
Мы освоили работу с RAID-массивами при помощи утилиты mdadm.
