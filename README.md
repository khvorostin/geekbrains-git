# geekbrains-git
Домашние задания по курсу "GIT, базовый курс" (август 2021 г.)

## Главные операции GIT

### Вывод информации о текущем статусе проекта

Вывод информации о текущем статусе проекта:

```$ git status```

Компактный вывод этой же информации:

```$ git status -s```

Вывод разницы в файлах, которые отслеживаются гитом, были изменены, но ещё не проиндексированы (т.е. до *git add*):

```$ git diff```

Вывод разницы в файлах, которые отслеживаются гитом, были изменены и проиндексированы, но не закоммичены (т.е. между *git add* и *git commit*):

```$ git dif --cached```

Просмотр истории изменений:

```$ git log```

Ограничение истории измений двумя последними коммитами:

```$ git log -2```

Посмотреть, что было изменено:

```$ git log -p```

Просмотр статистики изменений (сколько строк затронуто коммитами):

```
$ git log --stat
commit 1d6451525a63d2d492d8e13fb057d65dba5d6a54 (HEAD -> basic_commands, origin/master, master)
Author: Denis Khvorostin <denis.khvorostin@gmail.com>
Date:   Sat Aug 7 23:37:24 2021 +0300

    rename .keep to .gitkeep

 emptydir/{.keep => .gitkeep} | 0
 1 file changed, 0 insertions(+), 0 deletions(-)

commit f6a3ff0b18d51ccde9ea81bc37bf43c8d6255df5
Author: Denis Khvorostin <denis.khvorostin@gmail.com>
Date:   Sat Aug 7 23:28:31 2021 +0300

    Хинт с индексированием пустой папки

 emptydir/.keep | 0
 1 file changed, 0 insertions(+), 0 deletions(-)

commit 0d5e1855aa9519c07c56bec6d12586d57a33a4be
Author: Denis Khvorostin <denis.khvorostin@gmail.com>
Date:   Sat Aug 7 23:25:27 2021 +0300

    Initial commit

 README.md | 2 ++
 1 file changed, 2 insertions(+)

```

Вывод статистики изменений в одну строку:

```
$ git log --pretty=oneline
1d6451525a63d2d492d8e13fb057d65dba5d6a54 (HEAD -> basic_commands, origin/master, master) rename .keep to .gitkeep
f6a3ff0b18d51ccde9ea81bc37bf43c8d6255df5 Хинт с индексированием пустой папки
0d5e1855aa9519c07c56bec6d12586d57a33a4be Initial commit

```

### Индексирование файлов и создание коммитов

Типовая последовательность команд:

```
git add .
git commit -m 'Описание изменений'
```

Сокращённая запись:

```git commit -am 'Описание изменений'```

Изменение последнего коммита:

```git add .
git commit -m 'Описание изменений' --amend```

Вывод файла из индексного состояния (т.е. был сделан *git add*, нужно отменить его для файла):

```
git reset <file>
git reset HEAD <file>
git restore --staged <file>
git rm --cached <file>
```

(все четыре команды делают одно и то же)
