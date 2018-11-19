# linux_tutorial
<p><a name="top"></p>
  
  
Справочник linux
по материалам курсов <a href = https://stepik.org/course/762 target="blank"> Основы Linux от Stepik.org </a> , <a href = https://otus.ru/lessons/linux target="blank"> Администратор Linux от Otus.ru <a> , обучающих плейлистов по <a href = https://www.lpi.org/our-certifications/summary-of-certifications target="blank">LPIC</a> от <a href=https://www.youtube.com/user/itsemaev  target="blank">Кирилла Семаева</a> и <a target="blank" href = https://www.youtube.com/channel/UC-sAMvDe7gTmBbub-rWljZg/featured> Дениса Астахова </a>
  <h2>Оглавление</h2><br>
  <a href=#0>0. Выбор и установка дистрибутива</a><br>
  <a href=#1>1. Работа с файлами</a><br>
  <a href=#2>2. Работа с фильтрами</a><br>
  <a href=#3>3.</a><br>
  <a href=#4>4.</a><br>
  <a href=#5>5.</a><br>
  <a href=#6>6.</a><br>
  <a href=#7>7.</a><br>
  <a href=#8>8.</a><br>
  <a href=#9>9.</a><br>
  
<h3><a name = "0">0 Выбор и установка дистрибутива</h3>
  Дистрибутив Linux является коллекцией программного обеспечения, работающего под управлением ядра Linux.
 <h4>RedHat</h4>
RedHat является тесно связанной с Linux коммерческой компанией с бюджетом, исчисляющимся миллиардами долларов, работники которой прикладывают огромные усилия к разработке Linux. В данной компании трудоустроены сотни специалистов в области Linux, поэтому компания оказывает превосходную техническую поддержку своим клиентам. Продукты компании (Red Hat Enterprise Linux и Fedora) распространяются бесплатно. В отличие от дистрибутива Red Hat Enterprise Linux, который тщательно тестируется перед выпуском и поддерживается в течение периода длительностью до семи лет, Fedora является дистрибутивом с более частыми обновлениями, но без платной технической поддержки.

<h4>Ubuntu</h4>
Компания Canonical начала работу с распространения по почте бесплатных компакт-дисков с дистрибутивом Ubuntu Linux в 2004 году, в течение короткого периода обеспечив популярность своего дистрибутива среди домашних пользователей (многие пользователи перешли к использованию дистрибутива, отказавшись от Microsoft Windows). Целью компании Canonical является разработка в рамках дистрибутива Ubuntu простого в использовании графического окружения рабочего стола, работающего под управлением ядра Linux, которое позволит обойтись без командной строки. Конечно же, целью компании также является извлечение прибыли путем продажи услуг технической поддержки дистрибутива Ubuntu.

<h4>Debian</h4>
За дистрибутивом Debian не стоит никаких компаний. Вместо персонала компании развитие дистрибутива осуществляется тысячами хорошо организованных разработчиков, которые избирают лидера проекта Debian через каждые два года. Debian зарекомендовал себя как один из самых стабильных дистрибутивов Linux. Также данный дистрибутив является основой каждого из релизов дистрибутива Ubuntu. Существуют три версии дистрибутива Debian: stable (стабильная ветвь), testing (тестовая ветвь) и unstable (нестабильная ветвь). Каждый из выпусков дистрибутива Debian носит имя персонажа фильма "История игрушек" ("Toy Story").

<h4>Другие дистрибутивы</h4>
Такие дистрибутивы, как CentOS, Oracle Enterprise Linux и Scientific Linux базируются на дистрибутиве Red Hat Enterprise Linux и используют множество аналогичных принципов, директорий и техник администрирования системы. Дистрибутивы Linux Mint, Edubuntu и многие другие дистрибутивы с именами *buntu базируются на дистрибутиве Ubuntu и, таким образом, очень похожи на дистрибутив Debian. Существуют также сотни других дистрибутивов Linux.

<h3><a name = "1">1 Работа с файлами</h3>
<h4>Информация о файлах</h4>
В linux все есть файл. Любая директория на самом деле является файлом (с регистрозависмым именем), хотя этот файл и имеет специальный тип. Каждый терминал (например, /dev/pts/4), любой жесткий диск или раздел на нем (например, /dev/sdb1) и любой процесс представлены где-либо в рамках файловой системы с помощью файла.<br> 
В unix системах выделяют 6 типов файлов:<br>
   - обычный файл(regular file)<br>
   d директория (directory)<br>
   p именованный канал (named pipe)<br>
   l символическая ссылка (soft link)<br>
   c\b специальный файл устройства (device file)<br>
   s сокет (socket)<br>

<h5>file</h5>
Утилита для определения типа файла. Утилита file использует файл со списком "магических последовательностей байт", содержащий шаблоны для распознавания типов данных. Файл со списком "магических последовательностей байт" расположен по пути /usr/share/file/magic <br>

<h5>touch</h5>
touch - cоздание файла<br>

<h5>rm</h5>
rm - удаление файла<br>
rm -i - удаление файлов с подтверждением<br>
rm -Rfv - рекурсивное(-R) принудительное (-f) удаление файлов и директорий с выводом информации о процессе (-v)<br>

<h5>cp</h5>
cp - копирования файла с аргументами, представленными путями к исходному и целевому файлам (cp file copyOfFile)<br>
cp -r -копирование директории с поддиректориями 

```
cp -r mydir/ mydircopy
```

cp -i - предотвращает перезапись существующихх файлов<br>

<h5>mv</h5>
mv - переименование или перемещение файлов <br>
mv -i - запрос на подтверждение операции <br>

<h5>rename<h5>
единовременное переименования множества файлов с использованием регулярных выражений 
<h4>(debian\ubuntu)</h4>

```
rename 's/\.txt/\.png/' *.txt 
```

шаблон rename 's/in/out' files <br>
пример выше переименует все файлы с расширением txt на png для всех находящихся в текущем каталоге txt файлов <br>

```
rename 's/file/document/' *.png
```

в этом примере переименуется все вхождения символов file на document для всех файлов с расширением *.png <br>

<h4>(CentOS/RHEL/Fedora)</h4>
шаблон rename in out files<br>

```
rename .conf .backup *.conf 
```

будут переименованный все вхождения символов .conf на .backup для расширения .conf<br>
rename one ONE *<br>
все вайлы с вхождением one будут переименованны в ONE<br> 

<h5>pwd</h5>
pwd (print working directory) - отражает текущую директорию

<h5>cd</h5>
cd (change directory) - меняет текущую директорию<br>
cd ~ - переход в домашнюю директорию текущего юзера<br>
cd .. - переход в родительскую директорию<br>
cd - - переход в предыдущую директорию<br>

<h5>ls</h5>
ls - список содержимого директории<br>
ls -a - список всего содержимого,включая скрытые файлы<br>
ls -l (alias ll) - вывод метаданных(inode) о содержимом директории<br>
ls -h - вывод информации о содержимом директории в человекочитаемом виде<br>
ls -lah - commmbo!<br>

<h5>mkdir</h5>
mkdir(make directory) - создание каталога с передачей парметра имени каталога (mkdir mydir)<br>
mkdir -p - создание группы подкаталогов (mkdir -p mydir/mydir2/mydir3)<br>

<h5>rmdir</h5>
rmdir - удаление пустого каталога<br>
rmdir -p - удаление каталога с поддиректориями<br>

<h5>head</h5>
head - вывод начала содержимого файла (первые 10 строк) <br>
head -n - вывод первых n строк содержимого файла <br>
head -cn - вывод первых n байт файла <br>

<h5>tail</h5>
tail - вывод последних 10 строк содержимого файла


<h3><a name = "2">2 Работа с фильтрами</h3>
<h5>tee</h5>
 Фильтр tee перемещает данные из стандартного потока ввода stdin в стандартный поток вывода stdout, а также записывает их в файл.<br>
 
 ```
 tac count.txt | tee temp.txt | tac
 ```
 <h5>grep</h5>
 Наиболее простым сценарием использования фильтра grep является фильтрация строк текста, содержащих (или не содержащих) определенную подстроку.<br>
 grep -i - поиск без учета регистров
 grep -v - поиск БЕЗ учета подстроки
 grep -An - n строк перед искомой фразой
 grep -Bn - n строк после искомой фразы
 grep -Cn - контекст в n строк вокруг искомой строки
 
 
 
<h3><a name = "3">3-</h3>
<h3><a name = "4">4-</h3>
<h3><a name = "5">5-</h3>
<h3><a name = "6">6-</h3>
<h3><a name = "7">7-</h3>
<h3><a name = "8">8-</h3>
<h3><a name = "9">9-</h3>
