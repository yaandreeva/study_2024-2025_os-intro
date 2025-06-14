---
## Front matter
title: "Лабораторная работа № 4"
subtitle: "Основы интерфейса взаимодействия пользователя с системой Unix на уровне командной строки"
author: "Андреева Яна"
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
  name: English
## I18n babel
babel-lang: russian
babel-otherlangs: English
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

Приобретение практических навыков взаимодействия пользователя с системой посредством командной строки.

# Задание

1. Определите полное имя вашего домашнего каталога. Далее относительно этого каталога будут выполняться последующие упражнения.
2. Выполните следующие действия:
    2.1. Перейдите в каталог /tmp.

    2.2. Выведите на экран содержимое каталога /tmp. Для этого используйте команду ls с различными опциями. Поясните разницу в выводимой на экран информации.

    2.3. Определите, есть ли в каталоге /var/spool подкаталог с именем cron?

    2.4. Перейдите в Ваш домашний каталог и выведите на экран его содержимое. Определите, кто является владельцем файлов и подкаталогов? 3. Выполните следующие действия:

    3.1. В домашнем каталоге создайте новый каталог с именем newdir. 
    
    3.2. В каталоге ~/newdir создайте новый каталог с именем morefun.

    3.3. В домашнем каталоге создайте одной командой три новых каталога с именами letters, memos, misk. Затем удалите эти каталоги одной командой.

    3.4. Попробуйте удалить ранее созданный каталог ~/newdir командой rm. Проверьте,был ли каталог удалён.

    3.5. Удалите каталог ~/newdir/morefun из домашнего каталога. Проверьте, был ли каталог удалён.

4. С помощью команды man определите, какую опцию команды ls нужно использовать для просмотра содержимое не только указанного каталога, но и подкаталогов, входящих в него.
5. С помощью команды man определите набор опций команды ls, позволяющий отсортировать по времени последнего изменения выводимый список содержимого каталога с развёрнутым описанием файлов.
6. Используйте команду man для просмотра описания следующих команд: cd, pwd, mkdir,rmdir, rm. Поясните основные опции этих команд.
7. Используя информацию, полученную при помощи команды history, выполните модификацию и исполнение нескольких команд из буфера команд.

# Теоретическое введение

В операционной системе типа Linux взаимодействие пользователя с системой обычно осуществляется с помощью командной строки посредством построчного ввода команд. При этом обычно используется командные интерпретаторы языка shell: /bin/sh; /bin/csh; /bin/ksh. Формат команды. Командой в операционной системе называется записанный по специальным правилам текст (возможно с аргументами), представляющий собой ука- зание на выполнение какой-либо функций (или действий) в операционной системе. Обычно первым словом идёт имя команды, остальной текст — аргументы или опции, конкретизирующие действие. Общий формат команд можно представить следующим образом: <имя_команды><разделитель><аргументы> Команда man. Команда man используется для просмотра (оперативная помощь) в диалоговом режиме руководства (manual) по основным командам операционной системы типа Linux. Формат команды: man <команда>.

# Выполнение лабораторной работы

Определим полное имя домашнего каталога с помощью команды pwd.
![](image/fig1.png)

Перейдем в каталог /tmp, выведем на экран его сожержимое с помощью команды ls с различными опциями.
![](image/fig2.png)
![](image/fig3.png)
ls -a отображает имена скрытых файлов.
![](image/fig4.png)
ls -F выводит информацию о типах файлов.
![](image/fig5.png)
ls -l выводит подробную информацию о файлах и каталогах.
![](image/fig6.png)

Определим, есть ли в каталоге /var/spool подкаталог с именем cron.
![](image/fig7.png)
Используем команду ls и убеждаемся, что есть такой подкаталог.

Перейдем в домашний каталог и выведем на экран его сожержимое, увидим кто является владельцем.
![](image/fig8.png)

В домашнем каталоге создим новый каталог с именем newdir. В каталоге ~/newdir создадим новый каталог с именем morefun. В домашнем каталоге создадим одной командой три новых каталога с именами letters, memos, misk. Затем удалим эти каталоги одной командой. Попробуем удалить ранее созданный каталог ~/newdir командой rm. Проверим,был ли каталог удалён. Удалим каталог ~/newdir/morefun из домашнего каталога. Проверим, был ли каталог удалён.
![](image/fig9.png)

С помощью команды man определим, какую опцию команды ls нужно использовать для просмотра содержимое не только указанного каталога, но и подкаталогов, входящих в него.
С помощью команды man определим набор опций команды ls, позволяющий отсортировать по времени последнего изменения выводимый список содержимого каталога с развёрнутым описанием файлов.
![](image/fig10.png)

Используем команду man для просмотра описания следующих команд: cd, pwd, mkdir,rmdir, rm. 
![](image/fig11.png)
![](image/fig12.png)
![](image/fig13.png)
![](image/fig14.png)
![](image/fig15.png)

Используя информацию, полученную при помощи команды history, выполним модификацию и исполнение нескольких команд из буфера команд.
![](image/fig16.png)

# Контрольные вопросы

1. Что такое командная строка?
Командная строка - это текстовый интерфейс взаимодействия человека и компьютера, в котором компьютеру даются некоторые инструкции, путём их ввода с клавиатуры. Интерфейс командной строки противопоставляется управлению командами на основе меню и при помощи графического интерфейса.

2. При помощи какой команды можно определить абсолютный путь текущего каталога? Приведите пример.
Абсолютный путь текущего каталога можно определить при помощи команды pwd. Например, Чтобы определить абсолютный путь каталога в котором мы находимся нужно написать в командной строке:

-> pwd

3. При помощи какой команды и каких опций можно определить только тип файлов и их имена в текущем каталоге? Приведите примеры.
При помощи команды ls -F.

4. Каким образом отобразить информацию о скрытых файлах? Приведите примеры.
При помощи команды ls -a.

5. При помощи каких команд можно удалить файл и каталог? Можно ли это сделать одной и той же командой? Приведите примеры.
Удалить файл или каталог можно при помощи команды rm, rmdir - только пустой каталог, rm -r - любой файл или непустой каталог.

6. Каким образом можно вывести информацию о последних выполненных пользователем командах? работы?
При помощи команды history.

7. Как воспользоваться историей команд для их модифицированного выполнения? Приведите примеры.
Нужно написать следующую конструкцию:

!<Номер команды>:s/<ЧТО меняем>/<НА что меняем>

8. Приведите примеры запуска нескольких команд в одной строке.
Когда требуется выполнить несколько команд в одной строке, пишем символ ; (точка с запятой)

cd work; ls

9. Дайте определение и приведите примера символов экранирования.
Если в заданном контексте встречаются символы (".", "/", "*" и т.д.), то перед ними нудно поставить кавычки как символ экранирования. Также они ставятся, когда текст - просто текст, а не команда.

10. Охарактеризуйте вывод информации на экран после выполнения команды ls с опцией l.
Чтобы вывести на экран подробную информацию о файлах и каталогах, нужно использовать команду ls с опцией l. При этом о каждом файле и каталоге будет выведена следующая информация: тип файла, право доступа, число ссылок, владелец, размер, дата последней ревизии, имя файла или каталога.

11. Что такое относительный путь к файлу? Приведите примеры использования относительного и абсолютного пути при выполнении какой-либо команды.
Относительный путь - это ссылка, указывающая, на другие каталоги, относительно каталога, в котором мы находимся. Допустим, я сейчас нахожусь в каталоге report, который содержит каталог images. Тогда, чтобы перейти в каталог images мне достаточно написать команду cd images.

12. Как получить информацию об интересующей вас команде?
Чтобы получить информацию об интересующей меня команде есть два пути: команда help или команда man.

13. Какая клавиша или комбинация клавиш служит для автоматического дополнения вводимых команд?
Клавиша Tab.

# Выводы

Приобрели практические навыки взаимодействия пользователя с системой посредством командной строки.

# Список литературы
