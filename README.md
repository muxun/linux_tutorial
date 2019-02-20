# linux
<p><a name="top"></p>
  
  
Справочник-компиляция linux
по материалам курсов <a href = https://stepik.org/course/762 target="blank"> Основы Linux от Stepik.org </a> , <a href = https://otus.ru/lessons/linux target="blank"> Администратор Linux от Otus.ru <a> , обучающих плейлистов по <a href = https://www.lpi.org/our-certifications/summary-of-certifications target="blank">LPIC</a> от <a href=https://www.youtube.com/user/itsemaev  target="blank">Кирилла Семаева</a> и <a target="blank" href = https://www.youtube.com/channel/UC-sAMvDe7gTmBbub-rWljZg/featured> Дениса Астахова </a> и прочих источников
  <h2>Оглавление</h2><br>
  <a href=#0>0. Выбор и установка дистрибутива</a><br>
  <a href=#1>1. Работа с файлами</a><br>
  <a href=#2>2. Работа с фильтрами</a><br>
  <a href=#3>3. Регулярные выражения</a><br>
  <a href=#4>4. vim</a><br>
  <a href=#5>5. Работа с пользователями и группами</a><br>
  <a href=#6>6. Работа с правами доступами</a><br>
  <a href=#7>7. </a><br>
  <a href=#8>8. Про SSH </a><br>
  <a href=#9>9. Настройка linux сервера после установки</a><br>
  <a href=#10>10 Cheat sheet</a><br>
  
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
 Наиболее простым сценарием использования фильтра grep является фильтрация строк текста, содержащих (или не содержащих) определенную  подстроку.<br>
 grep -i - поиск без учета регистров<br>
 grep -v - поиск БЕЗ учета подстроки<br>
 grep -An - n строк перед искомой фразой<br>
 grep -Bn - n строк после искомой фразы<br>
 grep -Cn - контекст в n строк вокруг искомой строки<br>
 
 <h5>cut</h5>
 Фильтр cut может использоваться для извлечения данных из столбцов расположенных в файлах таблиц с указанием разделителя столбцов или количества байт данных в столбцах
 
 ```
 cut -d: -f1,3 /etc/passwd
 ```
 показаны 1 и 3 столбец из строк с раздилителем :
 
 Для указания разделителя пробела ,юзаем атрибут ` -d" " `

```
cut -d" " /etc/passwd
```
 
 Для вывода с 2 по 7 символы содержимого файла
 ```
  cut -c2-7 /etc/passwd
 ```

<h4>шаблоны поиска в shell</h4>
<h5>*</h5>

```
ls file*
> file1 file2 file3 file123
```
 
<h5>?</h5>

```
ls file?
>file1 file2 file3
```
 
 <h5>[]</h5>
 
 ```
 ls file[1]*
 >file1 file123
 ```
 
 <h5>[a-z] - [A-Z] - [0-9]</h5>
 
 ```
 ls file[0-9][0-9][0-9]
 >file123
 
 ls fil[e][!2]*
 >file1 file3 file123
 ```
 
 <h4>wc</h4>
 отражает количество строк слов и символов в документе<br>
 
 `wc`    <br>
 
 `wc -l` <br>
 
 `wc -w` <br>
 
 `wc -c` <br>
 
 <h4>sort</h4>
 сортировка по алфавиту содержимого файла<br>
 
 `sort -k1` - сортировка по колонке<br>
 
 `sort -n -k1` - сортировка по числовому значению и колонке<br>
 
 <h4>uniq</h4>
 uniq - представление уникальных данных в документа<br>
 uniq -c - представление уникальных данных с подсчетом повторяющихся слов<br>
 
 <h4>comm</h4>
 comm - сравнение потоков данных<br>
 >1 столбец - уникальное содержимое 1 файла<br>
 >2 столбец - уникальное содержимое 2 файла<br>
 >3 столбец - встречающиеся значения в 1 и 2 файле<br>
 
 
<h3><a name = "3">3 Регулярные выражения</h3>
<h4>regex</h4>
Существуют три различных версии синтаксисов регулярных выражений:<br>
BRE: Basic Regular Expressions (Базовый синтаксис регулярных выражений)<br>
ERE: Extended Regular Expressions (Расширенный синтаксис регулярных выражений)<br>
PCRE: Perl Regular Expressions (Синтаксис регулярных выражений языка программирования Perl)<br>

В зависимости от используемого инструмента может использоваться один или несколько упомянутых синтаксисов.<br>
К примеру, инструмент grep поддерживает параметр -E, позволяющий принудительно <br>
использовать расширенный синтаксис регулярных выражений (ERE) при разборе регулярного <br>
выражения, в то в время, как параметр -G позволяет принудительно использовать базовый <br>
синтаксис регулярных выражений (BRE), а параметр -P - синтаксис регулярных выражений <br>
языка программирования Perl (PCRE).<br>

<h4>grep regesx</h4>

`grep -G'i\|a' file ` - поиск вхождения i или a в file. Логическое ИЛИ экранируется \ <br>

`grep -E 's*' file` - вхождение нулевого,одного или большего кол-ва символа s <br>

`grep -E 's+' file` - вхождение одного или большего коло-ва символа s <br>

`grep a$ file` - совпадениев конце строки символа a <br>

`grep ^a file` - совпадение в начале строки символа a <br>

`grep '\bWATTOFIND\b' file` - поиск только вхождения WHATTOFIND <br>

`grep -w WHATTOFIND file` - поиск только слова WHATTOFIND <br>





<h3><a name = "4">4 VIM</h3>
<h4>ввод</h4>

`esc` - Выход в визуальный режим <br>

`a` — Начало ввода текста после текущего символа<br>

`A` — Начало ввода текста в конце текущей строки<br>

`i` — Начало ввода текста перед текущим символом<br>

`I` — Начало ввода текста в начале текущей строки<br>

`o` — Начало ввода текста в новой строке, созданной после текущей строки<br>

`O` — Начало ввода текста в новой строке, созданной перед текущей строкой<br>

<h4>замена и удаление символов</h4>

`x` — Удаление символа, выделенного с помощью курсора<br>

`X` — Удаление символа перед курсором<br>

`r` — Замена символа, выделенного с помощью курсора<br>

`p` — Вставка символа после курсора (в данном случае будет осуществляться вставка последнего удаленного символа)<br>

`xp` — Замена местами двух символов<br>

<h4>отмена действий</h4>

`u` — Отменить последнее действие<br>

`.` — Повторить последнее действие<br>

<h4>перенос копирование и вставкк строк</h4>

`dd` —	Перенос текущей строки<br>

`yy` — Копирование текущей строки (yank yank)<br>

`p`— Вставка строки после текущей строки<br>

`P` — Вставка строки до текущей строки<br>

`3dd` — Перемещение трех строк<br>

`4yy` — Копирование четырех строк<br>

<h4>переход по строке</h4>

`0` — Переход к началу текущей строки<br>

`^` — Переход к началу текущей строки<br>

`$` — Переход к концу текущей строки<br>

`d0` - Удаление символов до начала текущей строки<br>

`d$` — Удаление символов до конца текущей строки <br>

<h4>слова</h4>

`w` — Переход к следующему слову<br>

`b` — Переход к предыдущему слову<br>

`3w` — Переход вперед на три слова<br>

`dw` — Удаление одного слова<br>

`yw` — Копирование (yank) одного слова<br>

`5yb` — Копирование пяти слов до курсора<br>

`7dw` — Удаление семи слов<br>

<h4>сохранение данных и выход</h4>

`:w` — Сохранение (запись) данных в файл<br>

`:w` имя файла — Сохранение данных в файл с заданным именем<br>

`:q` — Завершение работы с редактором<br>

`:wq` — Сохранение данных и завершение работы с редактором<br>

`ZZ` — Сохранение данных и завершение работы с редактором<br>

`:q!` — Завершение работы с редактором (с отклонением внесенных вами изменений)<br>

`:w!` — Сохранение данных (и запись данных в защищенный от записи файл)<br>


<h3><a name = "5">5-</h3>
<h3><a name = "6">6-</h3>
<h3><a name = "7">7-</h3>
<h3><a name = "8">8 Про SSH</h3>
<h4>ssh</h4>
ssh авторизация не по паролю, а по паре ключей. Ключи состоят из открытого и закрытого ключа. Открытый ключ отправляется на сервер, закрытый — в домашний каталог пользователя, который идёт на удалённый сервер.
<h4>генерация ключей</h4>
по дефолту генерация происходит по rsa

```
ssh-keygen -t rsa
```
создается пара ключей

`~/.ssh/id_rsa.pub` — открытый ключ. Его копируют на сервера, куда нужно получить доступ.

`~/.ssh/id_rsa` — закрытый ключ.

копирование на сервер 

`ssh-copy-id user@server` - копирование публичного ключа на сервер

установка прав на ключи и каталог <br>
`chmod 700 ~/.ssh` - каталог <br>
`chmod 600 ~/.ssh/id_rsa` - закрытый ключ <br>
`chmod 644 ~/.ssh/id_rsa.pub` - открытый ключ <br>

<h4>работа с ssh-agent</h4>
 cоздаём ключи
 ```
    $ ssh-keygen
    # Но на этот раз вводим passphrase (ключевую фразу) - 
    #т.е. вводим пароль на доступ к приватному ключу ~/.ssh/ida_rsa
    # Вы так же сможете просмотреть ключ:
    $ cat ~/.ssh/ida_rsa
```

 запускаем агента для bash
 ```
 $ eval `ssh-agent`
 ```
 
 cообщаем агенту информацию о запаролированном приватном ключе:
  ```
    $ ssh-add /home/box/.ssh/name_rsa
    Или так (если имя у ключа стандартное, т.е. id_rsa):
    $ ssh-add # и вот тут агент наc спросит пароль passphrase, 
    #вводим его и получаем строку:
    Identity added: ...  # т.е. ключ добавлен
```

 убедимся в этом. Просмотрим ключи которые хранятся в агенте:
 ```
 $ ssh-add -l
```

импортируем публичный ключ на сервер (+ вводим пароль к серверу):
```
   $ ssh-copy-id user@server
   # После этого у вас появится файл ~/.ssh/known_hosts
   # Для дальнейшего подключения ПК-Сервер наш 
   # локальный публичный ключ ~/.ssh/id_rsa.pub - не нужен, его можно удалить
```

теперь при попытке входа на сервер:
```
 $ ssh user@server
 # Будет выведено окно с предложением сначала разблокировать секретный ключ на доступ
 # к приватному ключу и после ввода пароля произойдёт заход на сервер.
 # Вводить такой пароль разблокировки нужно максимум при входе в систему.
```

<h3><a name = "9">9 Настройка linux на сервере</h3>
<h4>задать root пользователю пароль</h4>

```
sudo -i
passwd root
```

<h4>создать юзера с правами sudo</h4>

для ubuntu

```
useradd username -G sudo -m
```
для centos

```
useradd username -G wheel -m
```

задать юзеру пароль

```
passwd username
```

<h4>задаем имя серверу</h4>

```
vi /etc/hostname
>server.domain.org
```

<h4>обновление системы</h4>
ubuntu
 x
 ```
 apt-get update && apt-get upgrade 
 ```
 
 centos
 
 ```
 yum update
 ```
 
 <h4>настройка времени</h4>
 
 ```
 \cp /usr/share/zoneinfo/Europe/Moscow /etc/localtime
 ```
 
  <h4>настройка ssh</h4>
  
  ```
  vi /etc/ssh/sshd_config
  # Запрет подключение от root, при этом должна быть учетка с доступом по ssh
  > PermitRootLogin no
  # Явное указание групп и пользователей для плдключения
  >AllowGroups wheel sudo developer testers
  >AllowUsers username dev tester
  # Изменение порта и адреса прослушивания
  > Port 2222
  > ListenAdress 192.168.0.1
  ```
 
 
<h3><a name = "10">10 Cheat Sheet</h3>
<h4>system information</h4>

```
# Display Linux system information
uname -a
 
# Display kernel release information
uname -r
 
# Show which version of redhat installed
cat /etc/redhat-release
 
# Show how long the system has been running + load
uptime
 
# Show system host name
hostname
 
# Display the IP addresses of the host
hostname -I
 
# Show system reboot history
last reboot
 
# Show the current date and time
date
 
# Show this month's calendar
cal
 
# Display who is online
w
 
# Who you are logged in as
whoami

```

<h4>hardware information</h4>

```
# Display messages in kernel ring buffer
dmesg
 
# Display CPU information
cat /proc/cpuinfo
 
# Display memory information
cat /proc/meminfo
 
# Display free and used memory ( -h for human readable, -m for MB, -g for GB.)
free -h
 
# Display PCI devices
lspci -tv
 
# Display USB devices
lsusb -tv
 
# Display DMI/SMBIOS (hardware info) from the BIOS
dmidecode
 
# Show info about disk sda
hdparm -i /dev/sda
 
# Perform a read speed test on disk sda
hdparm -tT /dev/sda
 
# Test for unreadable blocks on disk sda
badblocks -s /dev/sda

```

<h4>monitoring</h4>

```
# Display and manage the top processes
top
 
# Interactive process viewer (top alternative)
htop
 
# Display processor related statistics
mpstat 1
 
# Display virtual memory statistics
vmstat 1
 
# Display I/O statistics
iostat 1
 
# Display the last 100 syslog messages  (Use /var/log/syslog for Debian based systems.)
tail 100 /var/log/messages
 
# Capture and display all packets on interface eth0
tcpdump -i eth0
 
# Monitor all traffic on port 80 ( HTTP )
tcpdump -i eth0 'port 80'
 
# List all open files on the system
lsof
 
# List files opened by user
lsof -u user
 
# Display free and used memory ( -h for human readable, -m for MB, -g for GB.)
free -h
 
# Execute "df -h", showing periodic updates
watch df -h
 
```

<h4>users</h4>

```
# Display the user and group ids of your current user.
id
 
# Display the last users who have logged onto the system.
last
 
# Show who is logged into the system.
who
 
# Show who is logged in and what they are doing.
w
 
# Create a group named "test".
groupadd test
 
# Create an account named john, with a comment of "John Smith" and create the user's home directory.
useradd -c "John Smith" -m john
 
# Delete the john account.
userdel john
 
# Add the john account to the sales group
usermod -aG sales john

```

<h4>files and diractory</h4>

```
# List all files in a long listing (detailed) format
ls -al
 
# Display the present working directory
pwd
 
# Create a directory
mkdir directory
 
# Remove (delete) file
rm file
 
# Remove the directory and its contents recursively
rm -r directory
 
# Force removal of file without prompting for confirmation
rm -f file
 
# Forcefully remove directory recursively
rm -rf directory
 
# Copy file1 to file2
cp file1 file2
 
# Copy source_directory recursively to destination. If destination exists, copy source_directory into destination, otherwise create destination with the contents of source_directory.
cp -r source_directory destination
 
# Rename or move file1 to file2. If file2 is an existing directory, move file1 into directory file2
mv file1 file2
 
# Create symbolic link to linkname
ln -s /path/to/file linkname
 
# Create an empty file or update the access and modification times of file.
touch file
 
# View the contents of file
cat file
 
# Browse through a text file
less file
 
# Display the first 10 lines of file
head file
 
# Display the last 10 lines of file
tail file
 
# Display the last 10 lines of file and "follow" the file as it grows.
tail -f file
```

<h4>processes</h4>

```
# Display your currently running processes
ps
 
# Display all the currently running processes on the system.
ps -ef
 
# Display process information for processname
ps -ef | grep processname
 
# Display and manage the top processes
top
 
# Interactive process viewer (top alternative)
htop
 
# Kill process with process ID of pid
kill pid
 
# Kill all processes named processname
killall processname
 
# Start program in the background
program &amp;
 
# Display stopped or background jobs
bg
 
# Brings the most recent background job to foreground
fg
 
# Brings job n to the foreground
fg n
```

<h4>permissions</h4>

```
PERMISSION      EXAMPLE
 
         U   G   W
        rwx rwx rwx     chmod 777 filename
        rwx rwx r-x     chmod 775 filename
        rwx r-x r-x     chmod 755 filename
        rw- rw- r--     chmod 664 filename
        rw- r-- r--     chmod 644 filename
 
# NOTE: Use 777 sparingly!
 
        LEGEND
        U = User
        G = Group
        W = World
 
        r = Read
        w = write
        x = execute
        - = no access

```

<h4>networking</h4>

```
# Display all network interfaces and ip address
ifconfig -a
 
# Display eth0 address and details
ifconfig eth0
 
# Query or control network driver and hardware settings
ethtool eth0
 
# Send ICMP echo request to host
ping host
 
# Display whois information for domain
whois domain
 
# Display DNS information for domain
dig domain
 
# Reverse lookup of IP_ADDRESS
dig -x IP_ADDRESS
 
# Display DNS ip address for domain
host domain
 
# Display the network address of the host name.
hostname -i
 
# Display all local ip addresses
hostname -I
 
# Download https:://domain.com/file
wget https:://domain.com/file
 
# Display listening tcp and udp ports and corresponding programs
netstat -nutlp
```

<h4>archives</h4>

```
# Create tar named archive.tar containing directory.
tar cf archive.tar directory
 
# Extract the contents from archive.tar.
tar xf archive.tar
 
# Create a gzip compressed tar file name archive.tar.gz.
tar czf archive.tar.gz directory
 
# Extract a gzip compressed tar file.
tar xzf archive.tar.gz
 
# Create a tar file with bzip2 compression
tar cjf archive.tar.bz2 directory
 
# Extract a bzip2 compressed tar file.
tar xjf archive.tar.bz2
```

<h4>packages</h4>

```
# Search for a package by keyword.
yum search keyword
 
# Install package.
yum install package
 
# Display description and summary information about package.
yum info package
 
# Install package from local file named package.rpm
rpm -i package.rpm
 
# Remove/uninstall package.
yum remove package
 
# Install software from source code.
tar zxvf sourcecode.tar.gz
cd sourcecode
./configure
make
make install
```

<h4>search</h4>

```
# Search for pattern in file
grep pattern file

# Search recursively for pattern in directory
grep -r pattern directory

# Find files and directories by name
locate name

# Find files in /home/john that start with "prefix".
find /home/john -name 'prefix*'

# Find files larger than 100MB in /home
find /home -size +100M
```
<h4>files transfers</h4>

```
# Secure copy file.txt to the /tmp folder on server
scp file.txt server:/tmp
 
# Copy *.html files from server to the local /tmp folder.
scp server:/var/www/*.html /tmp
 
# Copy all files and directories recursively from server to the current system's /tmp folder.
scp -r server:/var/www /tmp
 
# Synchronize /home to /backups/home
rsync -a /home /backups/
 
# Synchronize files/directories between the local and remote system with compression enabled
rsync -avz /home server:/backups/

```

<h4>disk usage</h4>

```
# Show free and used space on mounted filesystems
df -h
 
# Show free and used inodes on mounted filesystems
df -i
 
# Display disks partitions sizes and types
fdisk -l
 
# Display disk usage for all files and directories in human readable format
du -ah
 
# Display total disk usage off the current directory
du -sh
```

ufw - управление файерволлом  , предварительно нужно установить
 


# linux tips

# === VIM ===

## mode INSERT

i - insert

a - add 

o - new line after cursor

## EXITING

ESC

:wq 

:q!

ZZ

## EDITING TEXT

dd - delete string to buffer

yy - coping string to buffer

p - paste from buffer

## mode VISUAL

v  - into to visual mode to mark text

d - delete to buffer

y - copy to buffer

p -paste from buffer 

## MANAGING TEXT

u - undo otmena

ctrl + r

USEFULL COMMAND

:%s/old/new/g

# ==**ВИДЫ СЕТЕВЫХ АДАПТЕРОВ VIRTUALBOX==**

Существует несколько способов как настроить сеть в virtualbox, и каждый из них подходит для лучше для решения одной задачи и меньше для другой. Рассмотрим основные:

- **NAT** - этот способ используется по умолчанию. Для каждой машины создается отдельная внутренняя локальная сеть, в которой машина получает ip 10.10.0.1. Машина может связаться с интернетом, используя технологию NAT, и вы можете обратиться к машине, используя проброс портов VirtualBox, но если у вас будет две виртуальные машины, то вы уже не сможете между ними так взаимодействовать. И если из основной системы к гостевой можно обратиться, то к основной ни гостевой уже никак не получится;
- **Виртуальный адаптер хоста** - создается виртуальный сетевой адаптер, к которому можно подключить несколько виртуальных машин, тем самым объединив их в локальную сеть. Доступа к интернету нет, но зато машины находятся в одной сети и каждая имеет свой ip адрес, теперь они могут взаимодействовать между собой. Основная система тоже доступна по ip 192.168.56.1. Машины доступны не только между собой, но и из основной системы;
- **Сетевой мост** - при таком подключении виртуальная машина становится полноценным членом локальной сети, к которой подключена основная система. Машина использует сетевой интерфейс чтобы получить адрес у роутера и становится доступна для других устройств, как и основной компьютер по своему ip адресу.
- **Внутренняя сеть** - почти то же самое, что и виртуальный адаптер хоста, только без возможности доступа к виртуальной сети из основной системы, доступа к интернету нет.
- **Универсальный драйвер** - позволяет использовать драйвер из расширений VirtualBox для связи между машинами, расположенными на разных физических хостах.

# **Краткий список всех команд с описанием**

## **Примитивы**

[Untitled](https://www.notion.so/538c1c0b636d4a9e84c7c6f70b2aba6e)

> Важно понимать, что в современных дистрибутивах команды, свзанные с завершением работы являются символическими ссылками, напрмиер /sbin/reboot -> /bin/systemctl. и по сути команда посылается одному и тому же исполняемому файлу systemctl. Если выполнить команду без аргументов - по смыслу будет выполнена именно введенная команда. Некоторые из команд также принимают на вход ключи, которые позволяют управлять процессом останова, выключени или перезагрузки более тонко.

## **Вывод данных на экран**

[Untitled](https://www.notion.so/4c563f7f045041d6ab944e87ad86638a)

## **Работа с сетью**

[Untitled](https://www.notion.so/ca203d4ec4864c81ae20a1b257421aa7)

## **Фильтрование данных**

[Untitled](https://www.notion.so/3777464c7d4a4bad8aead1ca097752b3)

## **Информация о системе и системные утилиты**

[Untitled](https://www.notion.so/29da506efeb84cbf858f0cd2b0d480db)

## **Конфигурация системы**

[Untitled](https://www.notion.so/6002f7a5e05d4ac992337f8286cbfb04)

## **Работа с дисками**

[Untitled](https://www.notion.so/19fce5afa4b44d88ba6d9a7d2a9e5a62)

## **Архивы**

[Untitled](https://www.notion.so/227ce6c7fe064224867b2b09cf5eca61)

## **скриптинг**

[Untitled](https://www.notion.so/7a25d06ffdb24d3f906ad8ecb5ed5f8b)

## **Пакеты**

[Untitled](https://www.notion.so/2a065c45a8df48caaef30762f3b75a38)

## **Работа с файлами**

[Untitled](https://www.notion.so/23e607a1b8504d3aae81cd74339bfdd0)

## **Разное**

[Untitled](https://www.notion.so/d4c61bb5d96848608bd3252ff1d68166)

# RAID

**raid-0** - **stripping** - единое пространство из 2х винтов, запись файлов идет 50\50 на каждый диск. при порче одного информацию не восстановить
для увеличения дискового пространства\ совместной обработки информации. увеличивается скорость записи чтения.

**raid-1** - **mirroring** - зеркалирование данных на 2 винтах. Отказоустойчивость и скорость чтения,но  попадает

**raid-5 -** три винта, файлы пишутся как при рейде 0 , на третий день пишется хэш. Следующие файлы пишутся тоже на два других винта, хэш на третий.и так далее. Итого имея два живых диска мы можем получить либо части всего файла,либо высчитать из хэша,имея одну половину.

**raid-10 -** способ организации raid при котором используют 4 диска. два соседних зеркалируются,  и на них  пишется две одинаковых части файла, вторая пара с зеркальной второй частью.

**raid -01 -** аналогичен рэйду 10 , но два соседних винта пишутся по технологии рэйд 0, два других винта их зеркалят
