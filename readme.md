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

## Вывод лога

Получить список коммитов

```bash
git log
```


Получить сокращённый лог 

```bash
git log --oneline
```




## Описание Markdown

[Ссылка](/markdown.md)