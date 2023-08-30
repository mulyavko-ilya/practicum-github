# GIT OVERVIEW

## Installing
1. Install from site
2. Setting global settings
Set name & e-mail

git config user.email "bob@example.com"
git config user.name "Name Fullname"


## Adding SSH key
1. Generate key
2. Adding key
	- adding to github
	- adding to sshagent
3. Verify key

### Generate
ssh-keygen -t ed25519 -C <e-mail>

Put private key to
~/.ssh/


### Adding to sshagent

# start the ssh-agent in the background
$ eval "$(ssh-agent -s)"
> Agent pid 59566


ssh-add ~/.ssh/id_ed25519


[Ссылка на документацию:](https://docs.github.com/ru/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)

## Commands

### Create repo

### Создание пустого репозитория
```bash
git init
```

### Клонирование репозитария

```bash
git clone
```

### Убедиться, что репозитории связаны

```bash
git remote -v
```

### Привязать удалённый репозиторий к локальному - git remote add

```bash
cd ~/dev/first-project
git remote add origin git@github.com:%ИМЯ_АККАУНТА%/first-project.git
```

## Добавление коммита
1. Добавить файлы в stage-состояние
2. Закоммитить файлы
3. Запушить на удаленный сервер

```bash
git add .
git commit -m "описание коммита"
git push
```



## Описание Markdown

### Заголовки

# H1 — заголовок первого уровня, самый большой
## H2 — заголовок второго уровня, поменьше
### H3
#### H4
##### H5
###### H6 — заголовок шестого уровня, самый маленький


### Горизонтальная черта

Текст над чертой

---

Текст под чертой 


### Курсив, полужирный шрифты 

Курсив — это *звёздочки* или _подчёркивания_.


Полужирный шрифт — двойные **звёздочки** или двойные __подчёркивания__.
Можно совместить выделение **звёздочки и _подчёркивания_**. 


### Нумерованный список

1. Первый пункт нумерованного списка.
2. Второй пункт.


### Ненумерованный список

* первый пункт ненумерованного списка;
* второй пункт ненумерованного списка

- первый пункт ненумерованного списка;
- второй пункт ненумерованного списка 

### Ссылки

Чтобы сделать ссылкой часть текста, его заключают в квадратные скобки, а затем указывают нужный адрес в круглых скобках.

[Яндекс](https://www.yandex.ru)

Также можно добавить ссылке тайтл (от англ title — «название», «заголовок»). Тайтл — это всплывающая подсказка, которая появляется при наведении мыши на ссылку. Тайтл нужно заключить в кавычки и указать внутри скобок после адреса.

### Код

Чтобы оформить текст как код, нужно окружить его тройками косых кавычек — грависов. После первой тройки грависов указывают язык программирования, на котором написан код. В маркдауне есть поддержка синтаксиса почти всех популярных языков и инструментов.


Ссылки:
[https://gist.github.com/fomvasss/8dd8cd7f88c67a4e3727f9d39224a84c](https://gist.github.com/fomvasss/8dd8cd7f88c67a4e3727f9d39224a84c)

[https://www.markdownguide.org/cheat-sheet/](https://www.markdownguide.org/cheat-sheet/)