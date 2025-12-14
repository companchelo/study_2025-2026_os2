
---
## Front matter
title: "Лабораторная работа №15"
subtitle: "Управление логическими томами"
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

Получить навыки управления логическими томами

# Выполнение лабораторной работы

Хоть 14 лабораторная работа выполнена успешно, но после Rocky отказывался работать, из-за этого пришлось переустанавливать систему, следуя из этого я пропустила первые три пункта и начала с 4(рис. [-@fig:001]).

![Создание](image/1.jpg){#fig:001 width=70%}

Просмотр текущей разметки, создание новой таблицы, убеждение в удаление, сохранениие(рис. [-@fig:002]).

![Просмотр](image/2.jpg){#fig:002 width=70%}

Запись изменений, просмотр информации о разделах(рис. [-@fig:003]).

![Просмотр](image/3.jpg){#fig:003 width=70%}

Создание нового раздела, делаем его основным разделом, изменяем тип раздела, записываем изменения, обновляем таблицу разделов, указываем физический том, убеждаемся, что создан успешно(рис. [-@fig:004]).

![Раздел](image/4.jpg){#fig:004 width=70%}

Проверяем доступность физических томов, создаём группу томов, проверяем, что группа была создана успешно, создаём логический том LVM с именем lvdata, проверка успешного добавления(рис. [-@fig:005]).

![Проверка](image/5.jpg){#fig:005 width=70%}

Создаём файловую систему поверх логического тома, создаём папку, добавляем строку, проверяем(рис. [-@fig:006]).

![Создание](image/6.jpg){#fig:006 width=70%}

Строка, которую мы добавили(рис. [-@fig:007]).

![Строка](image/7.jpg){#fig:007 width=70%}

Добавляем раздел(рис. [-@fig:008]).

![Добавление](image/8.jpg){#fig:008 width=70%}

Создаём физический том, расширяем vgdata, проверяем ,что размер доступной группы томов увеличен, проверяем текущий размер, проверяем текущий размер файловой системы, увеличиваем lvdata на 50% оставшегося доступного дискового пространства, убеждаемся, уменьшаем размер, убеждаемся в успешном изменение дискового пространства(рис. [-@fig:009]).

![Создание](image/9.jpg){#fig:009 width=70%}

1 задание, создаём логический том, проверка создания, в файловую систему, создаём точку монтирования, промонтирование, проверка, перезагрузка(рис. [-@fig:010]).

![Создание](image/10.jpg){#fig:010 width=70%}

Задание 2. Проверка текущего размера, расширяем логический том, расширяем файловую систему, проверка(рис. [-@fig:011]).

![Расширение](image/11.jpg){#fig:011 width=70%}


Задание 3, проверяем размер, проверяем размер файловой системы, проверка целостности файловой системы(рис. [-@fig:012]).

![Проверка](image/12.jpg){#fig:012 width=70%}




# Ответы на вопросы 

1. 8e00 (Linux LVM)

2. vgcreate -s 4M vggroup /dev/sdb3

3. pvs

4. vgextend vggroup /dev/sdd

5. lvcreate -n lvvol1 -L 6M vggroup

6. lvextend -L +100M /dev/vggroup/lvvol1

7. Добавить новый физический том в группу томов: vgextend vggroup /dev/новый_диск

8. -r (пример: lvextend -r -L +200M /dev/vggroup/lvvol1)

9. lvs или lvdisplay

10. Для ext4: fsck /dev/vgdata/lvdata
Для XFS: xfs_check /dev/vgdata/lvdata





# Выводы
Мы получили навыки управления логическими томами
