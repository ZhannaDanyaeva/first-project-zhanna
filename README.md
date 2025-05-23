# Инициализируем репозиторий

```$ cd ~/dev/first-project # перешли в нужную папку

$ git init # создали репозиторий

$ cd <папка с репозиторием> # перешли в папку

$ rm -rf .git # удалили подпапку .git
```



## Добавляем файлы в репозиторий

```$ touch todo.txt
$ touch readme.txt
# создали файлы todo.txt и readme.txt

$ git status # проверили статус

$ git add --all # подготовили к сохранению все файлы в репозитории


$ git status # проверили статус

$ git add todo.txt
$ git add readme.txt
$ git status

$ git add . # добавить всю текущую папку
$ git status

$ git add todo.txt
# или
$ git add --all
```

---

# Делаем первый коммит

$ git commit -m ‘Мой первый коммит!‘



# Просматриваем историю коммитов

### История коммитов важна для отслеживания изменений в репозитории. Команда git log выводит журнал коммитов в обратном хронологическом порядке. Если в репозитории нет коммитов проверьте порядок вызова git add и git commit. 

# Проверка наличия SSH-ключа

```$ cd ~ # перешли в домашнюю директорию


$ ls -la .ssh/ # вывели список созданных ключей

$ ssh-keygen -t ed25519 -C "электронная почта, к которой привязан ваш аккаунт на GitHub"

$ ssh-keygen -t rsa -b 4096 -C "электронная почта, к которой привязан ваш аккаунт на GitHub"

> Generating public/private rsa key pair. # сгенерированы публичный и приватный ключи

> Enter a file in which to save the key (C:\Users\<имя_пользователя>\.ssh\):[Press enter]

> Enter passphrase (empty for no passphrase): [Type a passphrase]
> Enter same passphrase again: [Type passphrase again]

ls -a ~/.ssh

#### Привязываем SSH-ключ к GitHub
# скопировать содержимое ключа в буфер обмена:
$ pbcopy < ~/.ssh/id_rsa.pub
# для ed25519:
$ pbcopy < ~/.ssh/id_ed25519.pub

$ ssh -T git@github.com

The authenticity of host 'github.com (140.82.121.4)' can't be established. ED25519 key fingerprint is SHA256:+DiY3wvvV6TuJJhbpZisF/zLDA0zPMSvHdkr4UvCOqU. This key is not known by any other names. Are you sure you want to continue connecting (yes/no/[fingerprint])?

Hi %ВАШ_АККАУНТ%! You've successfully authenticated, but GitHub does not provide shell access.

```

# Связываем локальный и удалённый репозитории

```$ cd ~/dev/first-project
$ git remote add origin git@github.com:%ИМЯ_АККАУНТА%/first-project.git

$ git remote -v
origin    git@github.com:%ИМЯ_АККАУНТА%/%ИМЯ-ПРОЕКТА%.git (fetch)
origin    git@github.com:%ИМЯ_АККАУНТА%/%ИМЯ-ПРОЕКТА%.git (push)

```

# Синхронизируем локальный и удалённый репозитории

```$ git push -u origin main # Если команда приведёт к ошибке, попробуйте # заменить main на master.

$ git push
```



# Файл README.md - H1 — заголовок первого уровня, самый большой
## H2 — заголовок второго уровня, поменьше
### H3
#### H4
##### H5
###### H6 — заголовок шестого уровня, самый маленький


#### Заголовок 4

Текст над чертой

---

Текст под чертой  


Текст до переноса⋅⋅  
Текст после переноса <br>
Текст после второго переноса

line 
another line

Курсив — это *звёздочки* или _подчёркивания_.

Полужирный шрифт — двойные **звёздочки** или двойные __подчёркивания__.
Можно совместить выделение **звёздочки и _подчёркивания_**.

~~Зачёркнутый текст.~~

1. Первый пункт нумерованного списка.
2. Второй пункт.

* первый пункт ненумерованного списка;
* второй пункт ненумерованного списка

- первый пункт ненумерованного списка;
- второй пункт ненумерованного списка

[Яндекс](https://www.yandex.ru)

[Яндекс](https://www.yandex.ru "Я Yandex!")

```bash
ls - la
```
```html
<h1>А я просто текст</h1>
```

# Шпаргалка markdown

## Выделение текста

Вы можете выделять текст в markdown с помощью символов `_` или `*`. Например:

Пример _курсива_ и **жирного** текста.

## Заголовки

Заголовки можно создавать с помощью символа `#`. Чем больше `#`, тем меньше заголовок. Например:

# Заголовок первого уровня
## Заголовок второго уровня
### Заголовок третьего уровня

## Выделение кода

Чтобы выделить текст как код, поместите его в тройные кавычки `````. 

```
mkdir my_project
cd my_project
git init
```
Это лишь некоторые функции markdown.

# Практическая работа 2. Дополняем шпаргалку

## Хеш — идентификатор коммита

* Git преобразует информацию о коммитах с помощью алгоритма SHA-1 и для каждого из них рассчитывает уникальный идентификатор — хеш.
* Хеш — основной идентификатор коммита и позволяет узнать его автора, дату и содержимое закоммиченных файлов.
* Все хеши, а также таблицу соответствий хеш → информация о коммите Git хранит в папке .git.

## Исследуем лог

Разберём элементы, из которых состоит описание:
* строка из цифр и латинских букв после слова commit — это хеш коммита;
* Author — имя автора и его электронная почта;
* Date — дата и время создания коммита;
* в конце находится сообщение коммита.

### Получить сокращённый лог - git log --oneline


В сокращённом логе выводятся сокращённые хеши — их можно использовать точно так же, как и полные.

# HEAD

```$ pwd # посмотрели, где мы
/Users/user/dev/first-project

$ cd .git/
$ ls # посмотрели, какие есть файлы
COMMIT_EDITMSG  ORIG_HEAD  description  index  logs/     refs/
HEAD            config     hooks/       info/  objects/

$ cat HEAD # команда cat показывает содержимое файла
ref: refs/heads/master # в файле вот такая ссылка
```

```$ cat refs/heads/master # взяли ссылку из файла HEAD
# внутри хеш
e007f5035f113f9abca78fe2149c593959da5eb7

$ git log 
# сверяем с хешем последнего коммита
commit e007f5035f113f9abca78fe2149c593959da5eb7
Author: John Doe <johndoe@example.com>
Date:   Tue Mar 28 00:26:53 2023 +0300

    Добавить амбиций в список дел

... # другие коммиты
```

###### Папка .git содержит много непонятных файлов — об одном из них мы рассказали в этом уроке. Подытожим:
В числе прочих файлов в папке .git есть служебный файл HEAD. Он указывает на самый свежий коммит.
Вместо хеша последнего коммита можно написать слово HEAD — Git вас поймёт.

# Статусы файлов в Git

### Важное:
* Статусом untracked помечается файл, о существовании которого Git знает, но не следит за изменениями в нём. Этот статус — противоположность tracked, в который попадают все файлы, отслеживаемые Git.
* Файл переходит в статус staged после выполнения git add.
* Статус modified означает, что файл был изменён.
* Большинство файлов в проектах «шагает» по следующему циклу: «изменён» → «добавлен в список на коммит» → «закоммичен» → «изменён» → и так далее.

# Как читать git status

```$ cd ~/dev
$ mkdir git-status-lesson
$ cd git-status-lesson
$ git init
# тут Git выведет что-нибудь, но мы это пропустим
$ touch README.md
$ git add README.md
$ git commit -m 'Добавить README'
~~~~# по традиции первым создадим и закоммитим файл README.md
```

```$ git status
On branch master
nothing to commit, working tree clean 
```

```$ touch fileA.txt
$ git status
On branch master
Untracked files: # найдены неотслеживаемые файлы
  (use "git add <file>..." to include in what will be committed)
        fileA.txt

nothing added to commit but untracked files present (use "git add" to track)
```
```$ git add fileA.txt 
$ git status
On branch master
Changes to be committed: # новая секция
  (use "git restore --staged <file>..." to unstage)
        new file:   fileA.txt
```

```$ git commit -m 'Добавить файл fileA.txt'
# тут будет вывод комманды commit, он нас не интересует
$ git status
On branch master
nothing to commit, working tree clean
```

```# внесли в fileA.txt правки
# запросили статус
$ git status 
On branch master
Changes not staged for commit: # ещё одна секция
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   fileA.txt
```
```$ git add fileA.txt
$ git status
On branch master
Changes to be committed: # все изменения готовы к коммиту
  (use "git restore --staged <file>..." to unstage)
        modified:   fileA.txt
```
```# изменили fileA.txt
$ git status
On branch master
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
          modified:   fileA.txt

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
          modified:   fileA.txt
```
---
* tracked
Файл есть в папке, но не указан ни в staged, ни в untracked. Это значит, что его когда-то закоммитили и с тех пор не меняли.
* tracked
Все файлы из staged являются tracked.
* staged
Файл указан в списке Changes to be committed
* untracked
Да, файл в списке Untracked files.
* tracked
Файл указан в списке Untracked files, а значит, не может быть tracked.
* modified
Файла нет в списке Changes not staged for commit.
---
## Подытожим то, о чём рассказали в уроке:
* Команда git status всегда подскажет, что происходит с файлом: например, он добавлен в список «на коммит» или ещё вообще не отслеживается, или изменён.
* git status показывает явно следующие состояния файлов: untracked, staged и modified.
* git status подсказывает, какие команды можно выполнить, чтобы поменять состояние файла.

# Оформление сообщений к коммитам

Правильно описывать коммиты — искусство, к которому стоит приобщиться как можно раньше. Хорошо, когда:
* сообщение коммита легко читается;
* оно информативное;
* все сообщения оформлены в одном стиле.

# Шпаргалка. Ключевые команды модуля


Чтобы вам было проще запомнить все команды, о которых шла речь в этом модуле, мы собрали их в одном месте.


Инициализация репозитория
git init (от англ. initialize, «инициализировать») — инициализируй репозиторий.


Синхронизация локального и удалённого репозиториев
git remote add origin https://github.com/YandexPracticum/first-project.git (от англ. remote, «удалённый» + add, «добавить») — привяжи локальный репозиторий к удалённому с URL https://github.com/YandexPracticum/first-project.git;
git remote -v (от англ. verbose, «подробный») — проверь, что репозитории действительно связались;
git push -u origin main (от англ. push, «толкать») — в первый раз загрузи все коммиты из локального репозитория в удалённый с названием origin.


💡 Ваша ветка может называться master, а не main. Подправьте команду, если это необходимо.
git push (от англ. push, «толкать») — загрузи коммиты в удалённый репозиторий после того, как он был привязан с помощью флага -u.


Подготовка файла к коммиту
git add todo.txt (от англ. add, **«добавить») — подготовь файл todo.txt к коммиту;
git add --all (от англ. add, «добавить» + all, «всё») — подготовь к коммиту сразу все файлы, в которых были изменения, и все новые файлы;
git add . — подготовь к коммиту текущую папку и все файлы в ней.


Создание и публикация коммита
git commit -m "Комментарий к коммиту." (от англ. commit, «совершать», фиксировать» + message, «сообщение») — сделай коммит и оставь комментарий, чтобы было проще понять, какие изменения сделаны;
git push (от англ. push, «толкать») — добавь изменения в удалённый репозиторий.


Просмотр информации о коммитах
git log (от англ. log, «журнал [записей]») — выведи подробную историю коммитов;
git log --oneline (от англ. log, «журнал [записей]» + oneline, «одной строкой») — покажи краткую информацию о коммитах: сокращённый хеш и сообщение.


Просмотр состояния файлов
git status (от англ. status, «статус», «состояние») — покажи текущее состояние репозитория.


Добавление изменений в последний коммит
git commit --amend --no-edit (от англ. amend, «исправить») — добавь изменения к последнему коммиту и оставь сообщение прежним;
git commit --amend -m "Новое сообщение" — измени сообщение к последнему коммиту на Новое сообщение.


💡 Выйти из редактора Vim: нажать Esc, ввести :qa!, нажать Enter.
«Откат» файлов и коммитов
git restore --staged hello.txt (от англ. restore, «восстановить») — переведи файл hello.txt из состояния staged обратно в untracked или modified;
git restore hello.txt — верни файл hello.txt к последней версии, которая была сохранена через git commit или git add;
git reset --hard b576d89 (от англ. reset, «сброс», «обнуление» + hard, «суровый») — удали все незакоммиченные изменения из staging и «рабочей зоны» вплоть до указанного коммита.


Просмотр изменений
git diff (от англ. difference, «отличие», «разница») — покажи изменения в «рабочей зоне», то есть в modified-файлах;
git diff a9928ab 11bada1 — выведи разницу между двумя коммитами;
git diff --staged — покажи изменения, которые добавлены в staged-файлах.

Шпаргалка. Ключевые команды для работы с ветками
В этой шпаргалке мы собрали все ключевые команды модуля — они наверняка пригодятся вам в реальной работе с ветками!
Клонирование чужого репозитория

git clone git@github.com:YandexPraktikum/first-project.git (от англ. clone, «клон», «копия») — склонируй репозиторий с URL first-project.git из аккаунта YandexPraktikum на мой локальный компьютер.
Создание веток

git branch feature/the-finest-branch (от англ. branch, «ветка») — создай ветку от текущей с названием feature/the-finest-branch;
git checkout -b feature/the-finest-branch — создай ветку feature/the-finest-branch и сразу переключись на неё.
Навигация по веткам

git branch (от англ. branch, «ветка») — покажи, какие есть ветки в репозитории и в какой из них я нахожусь (текущая ветка будет отмечена символом *);
git branch -a — покажи все известные ветки, как локальные (в локальном репозитории), так и удалённые (в origin, или на GitHub).
git checkout feature/br — переключись на ветку feature/br.
Сравнение веток

git diff main HEAD (от англ. difference, «отличие», «разница») — покажи разницу между веткой main и указателем на HEAD;
git diff HEAD~2 HEAD — покажи разницу между тем коммитом, который был два коммита назад, и текущим.
Удаление веток

git branch -d br-name — удали ветку br-name, но только если она является частью main;
git branch -D br-name — удали ветку br-name, даже если она не объединена с main.
Слияние веток

git merge main (от англ. merge, «сливать», «поглощать») — объедини ветку main с текущей активной веткой. 
Работа с удалённым репозиторием

git push -u origin my-branch (от англ. push, «толкнуть», «протолкнуть») — отправь новую ветку my-branch в удалённый репозиторий и свяжи локальную ветку с удалённой, чтобы при дополнительных коммитах можно было писать просто git push без -u;
git push my-branch — отправь дополнительные изменения в ветку my-branch, которая уже существует в удалённом репозитории;
git pull (от англ. pull, «вытянуть») — подтяни изменения текущей ветки из удалённого репозитория.



