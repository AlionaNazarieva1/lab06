---
# Front matter
lang: ru-RU
title: "Oтчёт по лабораторной работе"
subtitle: "Задача об эпидемии"
author: "Назарьева Алена Игоревна НФИбд-03-18"

# Formatting
toc-title: "Содержание"
toc: true # Table of contents
toc_depth: 2
lof: true # List of figures
lot: true # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a4paper
documentclass: scrreprt
polyglossia-lang: russian
polyglossia-otherlangs: english
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase
indent: true
pdf-engine: lualatex
header-includes:
  - \linepenalty=10 # the penalty added to the badness of each line within a paragraph (no associated penalty node) Increasing the value makes tex try to have fewer lines in the paragraph.
  - \interlinepenalty=0 # value of the penalty (node) added after each line of a paragraph.
  - \hyphenpenalty=50 # the penalty for line breaking at an automatically inserted hyphen
  - \exhyphenpenalty=50 # the penalty for line breaking at an explicit hyphen
  - \binoppenalty=700 # the penalty for breaking a line at a binary operator
  - \relpenalty=500 # the penalty for breaking a line at a relation
  - \clubpenalty=150 # extra penalty for breaking after first line of a paragraph
  - \widowpenalty=150 # extra penalty for breaking before last line of a paragraph
  - \displaywidowpenalty=50 # extra penalty for breaking before last line before a display math
  - \brokenpenalty=100 # extra penalty for page breaking after a hyphenated line
  - \predisplaypenalty=10000 # penalty for breaking before a display
  - \postdisplaypenalty=0 # penalty for breaking after a display
  - \floatingpenalty = 20000 # penalty for splitting an insertion (can only be split footnote in standard LaTeX)
  - \raggedbottom # or \flushbottom
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цель работы

Изучить и реализовать Задачу об эпидемии

# Задание
На одном небольшом острове вспыхнула эпидемия свинки. Известно, что из
всех проживающих на острове (N=6730) в момент начала эпидемии (t=0) число
заболевших свинкой людей (являющихся распространителями инфекции) I(0)=46,
А число здоровых людей с иммунитетом к болезни R(0)=8. Таким образом, число
людей восприимчивых к болезни, но пока здоровых, в начальный момент времени
S(0)=N-I(0).
Постройте графики изменения числа особей в  каждой из трех групп. Рассмотрите, как будет протекать эпидемия в случае:
а) если I(0)<=I*
б) если I(0)>I*

# Теоретическая справка

Рассмотрим простейшую модель эпидемии. Предположим, что некая
популяция, состоящая из N особей, (считаем, что популяция изолирована)
подразделяется на три группы. Первая группа - это восприимчивые к болезни, но
пока здоровые особи, обозначим их через S(t). Вторая группа – это число
инфицированных особей, которые также при этом являются распространителями
инфекции, обозначим их I(t). А третья группа, обозначающаяся через R(t) – это
здоровые особи с иммунитетом к болезни.
До того, как число заболевших не превышает критического значения
I*, считаем, что все больные изолированы и не заражают здоровых.
Когда I(t)>I*, тогда инфицирование способны заражать восприимчивых к болезни особей.
Таким образом, скорость изменения числа S(t) меняется по следующему
закону:
dS/dt= -aS, если I(t)>I*
        0, если I(t)<=I* (1)
Поскольку каждая восприимчивая к болезни особь, которая, в конце концов,
заболевает, сама становится инфекционной, то скорость изменения числа
инфекционных особей представляет разность за единицу времени между
заразившимися и теми, кто уже болеет и лечится, т.е.:
dI/dt=aS-bI, если I(t)>I*
      -bI, если I(t)<=I* (2)
А скорость изменения выздоравливающих особей (при этом приобретающие
иммунитет к болезни)
dR/dt=bI (3)
Постоянные пропорциональности
a,b - это коэффициенты заболеваемости и выздоровления соответственно.
Для того, чтобы решения соответствующих уравнений определялось
однозначно, необходимо задать начальные условия .Считаем, что на начало
эпидемии в момент времени
t = 0 нет особей с иммунитетом к болезни R(0)=0, а
число инфицированных и восприимчивых к болезни особей
I(0) и S(0)соответственно. Для анализа картины протекания эпидемии необходимо
рассмотреть два случая:
I(0)<=I* и
I(0)>I*

# Выполнение лабораторной работы

1. Код в python для I(0)<=I* (рис. -@fig:001)

![код для первого случая](1.jpg){ #fig:001 width=70% }

2. Динамика изменения числа людей в каждой из трех групп в случае,
когда I(0)<=I* (рис. -@fig:002)

![график для первого случая](2.jpg){ #fig:002 width=70% }

3.  Код в python для I(0)>I* (рис. -@fig:003)

![код для второго случая](3.jpg){ #fig:003 width=70% }

4. Динамика изменения числа людей в каждой из трех групп в случае,
когда I(0)>I* (рис. -@fig:004)

![график для второго случая](4.jpg){ #fig:004 width=70% }

# Выводы

В результате проделанной работы я изучила и реализовала Задачу об эпидемии
