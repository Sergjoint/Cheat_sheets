## Базовые команды в консоли
### Навигация

|Название|Перевод|Функционал|
|-|---|-------|
|pwd|print working directory|показать рабочую папку|
|ls|list directory contents|отобразить содержимое директории|
|ls -a| |отобразить скрытые файлы и папки, названия которых начинаются с символа .|
|cd directory|change directory|сменить директорию на directory|
|cd directory/html||перейти в папку html, которая находится в папке directory|
|cd ..||перейти на уровень выше, в родительскую папку|
|cd ~||перейти в домашнюю директорию (/Users/Username)|
|cd /||перейти в корневую директорию|

## Работа с файлами и папками
### Создание
•	touch index.html (англ. touch, коснуться — создай файл index.html в текущей папке;
•	touch index.html style.css script.js — если нужно создать сразу несколько файлов, можно напечатать их имена в одну строку через пробел;
•	mkdir second-project make directory, создать директорию — создай папку с именем second-project в текущей папке.
Копирование и перемещение
•	cp file.txt ~/my-dir copy, копировать — скопируй файл в другое место;
•	mv file.txt ~/my-dir move, переместить — перемести файл или папку в другое место.
Чтение
•	cat file.txt concatenate and print, объединить и распечатать — распечатай содержимое текстового файла file.txt.
Удаление
•	rm about.html remove, удалить — удали файл about.html;
•	rmdir images remove directory, удалить директорию — удали папку images;
•	rm -r second-project remove, удалить + recursive, рекурсивный — удали папку second-project и всё, что она содержит.
Полезные возможности
•	Команды необязательно печатать и выполнять по очереди. Можно указать их списком — разделить двумя амперсандами (&&.
•	У консоли есть собственная память — буфер с несколькими последними командами. По ним можно перемещаться с помощью клавиш со стрелками вверх (↑ и вниз (↓.
•	Чтобы не вводить название файла или папки полностью, можно набрать первые символы имени и дважды нажать Tab. Если файл или папка есть в текущей директории, командная строка допишет путь сама.
Например, вы находитесь в папке dev. Начните вводить cd first и дважды нажмите Tab. Если папка first-project есть внутри dev, командная строка автоматически подставит её имя. Останется только нажать Enter.
Допустим, вы создали или изменили какой-то файл и добавили его в список на коммит (staging area с помощью git add, но потом передумали включать его туда. Убрать файл из staging поможет команда git restore --staged <file> restore — восстановить.
Иногда нужно откатить то, что уже было закоммичено, то есть вернуть состояние репозитория к более раннему. Для этого используют команду git reset --hard <commit hash> reset — сброс, обнуление и hard — суровый.
Может быть так, что вы случайно изменили файл, который не планировали. Теперь он отображается в Changes not staged for commit (modified. Чтобы вернуть всё как было, можно выполнить команду git restore <file>.
•	Команда git restore --staged <file> переведёт файл из staged обратно в modified или untracked.
•	Команда git reset --hard <commit hash> откатит историю до коммита с хешем <hash>. Более поздние коммиты потеряются!
•	Команда git restore <file> откатит изменения в файле до последней сохранённой (в коммите или в staging версии.
•	Команда git diff сравнит последнюю закоммиченную версию файла с той, что находится в состоянии modified.
•	Команда git diff --staged покажет изменения в staged-файлах относительно последних закоммиченных версий.
•	Если нужно, чтобы Git игнорировал какие-то файлы, стоит составить файл .gitignore.
•	Посмотреть, что игнорируется, можно с помощью команды git status --ignored.
•	Сам файл .gitignore — это обычный файл в репозитории. Его тоже стоит закоммитить.
•	Шаблонов много, но их легко найти в интернете вместе с примерами использования.


Шпаргалка. Начало работы с Git
Чтобы вам было проще запомнить все команды, о которых шла речь в этом модуле, мы собрали их в одном месте.
Инициализация репозитория
git init initialize, инициализировать — инициализируй репозиторий.
Синхронизация локального и удалённого репозиториев
git remote add origin https://github.com/YandexPracticum/first-project.git remote, удалённый + add, добавить — привяжи локальный репозиторий к удалённому с URL https://github.com/YandexPracticum/first-project.git;
git remote -v verbose, подробный — проверь, что репозитории действительно связались;
git push -u origin main push, толкать — в первый раз загрузи все коммиты из локального репозитория в удалённый с названием origin.
💡 Ваша ветка может называться master, а не main. Подправьте команду, если это необходимо.
git push push, толкать — загрузи коммиты в удалённый репозиторий после того, как он был привязан с помощью флага -u.
Подготовка файла к коммиту
git add todo.txt add, добавить — подготовь файл todo.txt к коммиту;
git add --all add, добавить + all, всё — подготовь к коммиту сразу все файлы, в которых были изменения, и все новые файлы;
git add . — подготовь к коммиту текущую папку и все файлы в ней.
Создание и публикация коммита
git commit -m "Комментарий к коммиту." commit, совершать, фиксировать + message, сообщение — сделай коммит и оставь комментарий, чтобы было проще понять, какие изменения сделаны;
git push push, толкать — добавь изменения в удалённый репозиторий.
Просмотр информации о коммитах
git log log, журнал [записей] — выведи подробную историю коммитов;
git log --oneline log, журнал [записей] + oneline, одной строкой — покажи краткую информацию о коммитах: сокращённый хеш и сообщение.
Просмотр состояния файлов
git status status, статус, состояние — покажи текущее состояние репозитория.
Добавление изменений в последний коммит
git commit --amend --no-edit amend, исправить — добавь изменения к последнему коммиту и оставь сообщение прежним;
git commit --amend -m "Новое сообщение" — измени сообщение к последнему коммиту на Новое сообщение.
💡 Выйти из редактора Vim: нажать Esc, ввести :qa!, нажать Enter.
Откат файлов и коммитов
git restore --staged hello.txt restore, восстановить — переведи файл hello.txt из состояния staged обратно в untracked или modified;
git restore hello.txt — верни файл hello.txt к последней версии, которая была сохранена через git commit или git add;
git reset --hard b576d89 reset, сброс, обнуление + hard, суровый — удали все незакоммиченные изменения из staging и рабочей зоны вплоть до указанного коммита.
Просмотр изменений
git diff difference, отличие, разница — покажи изменения в рабочей зоне, то есть в modified-файлах;
git diff a9928ab 11bada1 — выведи разницу между двумя коммитами;
git diff --staged — покажи изменения, которые добавлены в staged-файлах.

Как назвать новую ветку
Есть разные подходы к наименованию веток. Каждая команда разработки выбирает свой. Но независимо от подхода ветки нужно называть так, чтобы другим участникам было понятно, что в них происходит.
Мы будем использовать указатели feature (англ. особенность, деталь для веток, где прорабатывается новая функциональность, и bugfix bug — жук, ошибка и fix — исправить для веток, где ведётся работа по исправлению ошибок.

Шпаргалка. Работа с ветками
В этой шпаргалке мы собрали все ключевые команды модуля — они наверняка пригодятся вам в реальной работе с ветками!
Клонирование чужого репозитория
git clone git@github.com:YandexPraktikum/first-project.git clone, клон, копия — склонируй репозиторий с URL first-project.git из аккаунта YandexPraktikum на мой локальный компьютер.
Создание веток
git branch feature/the-finest-branch branch, ветка — создай ветку от текущей с названием feature/the-finest-branch;
git checkout -b feature/the-finest-branch — создай ветку feature/the-finest-branch и сразу переключись на неё.
Навигация по веткам
git branch branch, ветка — покажи, какие есть ветки в репозитории и в какой из них я нахожусь (текущая ветка будет отмечена символом *;
git checkout feature/br — переключись на ветку feature/br.
Сравнение веток
git diff main HEAD difference, отличие, разница — покажи разницу между веткой main и указателем на HEAD;
git diff HEAD~2 HEAD — покажи разницу между тем коммитом, который был два коммита назад, и текущим.
Удаление веток
git branch -d br-name — удали ветку br-name, но только если она является частью main;
git branch -D br-name — удали ветку br-name, даже если она не объединена с main.
Слияние веток
git merge main merge, сливать, поглощать — объедини ветку main с текущей активной веткой. 
Работа с удалённым репозиторием
git push -u origin my-branch push, толкнуть, протолкнуть — отправь новую ветку my-branch в удалённый репозиторий и свяжи локальную ветку с удалённой, чтобы при дополнительных коммитах можно было писать просто git push без -u;
git push my-branch — отправь дополнительные изменения в ветку my-branch, которая уже существует в удалённом репозитории;
git pull pull, вытянуть — подтяни изменения текущей ветки из удалённого репозитория.
\


Алгоритм-шпаргалка для создания PR
1.	Склонировать репозиторий.
1.	Если вы не участник проекта, предварительно сделать форк исходного репозитория.
2.	На странице репозитория или форка нажать кнопки: Code → SSH → скопировать ссылку.
3.	Выполнить команду git clone <ссылка на репозиторий>.
2.	Создать ветку для вашей задачи: git checkout -b my-task-branch-name.
3.	Добавить и закоммитить изменения, которые вы хотите внести в проект.
4.	Запушить ветку: git push --set-upstream origin HEAD или git push -u origin my-task-branch-name.
1.	GitHub (с помощью Git выведет ссылку на создание PR. По ней нужно перейти.
2.	PR можно также создать через интерфейс GitHub.
5.	Сообщить о пул-реквесте ревьюеру.
1.	Иногда ревьюеры назначаются автоматически, тогда сообщать не нужно.
6.	Обсуждать с ревьюером предлагаемые изменения и вносить правки, пока эти изменения не будут одобрены (пока не будет получен апрув. 
6.1. Если кто-то добавил конфликтующие изменения в main, пока ваш PR был на ревью, нужно разрешить конфликт: 
o	Обновить main: git checkout main && git pull.
o	Влить main в свою ветку: git checkout my-task-branch-name && git merge main.
o	Разрешить конфликты слияния с помощью IDE или вручную.
o	Создать коммит слияния: git commit --no-edit или git commit -m 'merge main'.
o	Сделать git push своей ветки.
	Нажать кнопку Merge или подождать, пока её нажмёт кто-то ещё.
	Ещё раз обновить main, чтобы подтянуть ваши изменения в основную ветку локального репозитория: git checkout main && git pull.
	Вы великолепны! Можете начинать снова со второго пункта.
Алгоритм-шпаргалка для разрешения конфликтов слияния
1.	Открыть проект в IDE (VS Code, IDEA или другие.
2.	Открыть файл, в котором есть конфликт.
3.	Выбрать, какие части файла нужно взять из одной ветки, а какие — из другой.
4.	Когда конфликты разрешены, сделать коммит: git commit --no-edit или git commit -m 'merge branch <название ветки>'.


