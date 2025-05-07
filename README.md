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