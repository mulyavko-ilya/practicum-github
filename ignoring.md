# Игнорирование файлов в Git

Правила из *.gitignore* применяются только к новым (untracked) файлам. Если файл уже попал в staging area или в коммит, то правила на него не распространяются.



## Шаблоны игнорирования в Git

- Просто название файла
- Звёздочка (\*)
- Вопросительный знак (?)
- Квадратные скобки ([…])
- Слеш (/)
- Парные звёздочки (\*\*)
- Восклицательный знак (!)


### Просто название файла

```bash
.DS_Store 
```

Git будет игнорировать файлы с именем .DS_Store, причём не только в корне репозитория, но и во всех вложенных папках.


### Звёздочка


Символ звёздочки (\*) соответствует любой строке, включая пустую. Если такой символ используется в шаблоне в *.gitignore*, значит, файл будет проигнорирован вне зависимости от того, что будет на месте звёздочки.

Если задать правило, которое состоит только из звёздочки, Git будет игнорировать все файлы. Это происходит потому, что под звёздочку подходит любое имя файла.


### Вопросительный знак

Вопросительный знак ? соответствует одному любому символу.


### Квадратные скобки

Квадратные скобки, как и вопросительный знак, соответствуют одному символу. При этом символ не любой, а только из списка, который указан в скобках.


В скобках можно либо перечислить символы (*[abc]*), либо задать диапазон (*[a-z]*).


### Слеш 

Косая черта, или слеш (*/*), указывает на каталоги. Если шаблон в *.gitignore* начинается со слеша, то Git проигнорирует файлы или каталоги только в корневой директории.


### Парные звёздочки


Функция парных звёздочек (\*\*) похожа на функцию одинарной (\*). Отличие в том, как они работают с вложенными папками. Двойная звёздочка может соответствовать любому количеству таких папок (в том числе нулю). Одинарная может соответствовать только одной.


### Восклицательный знак

Любое правило в файле *.gitignore* можно инвертировать с помощью восклицательного знака (*!*).




## Игнорирование ранее закоммиченного файла


Чтобы игнорировать файл, для которого ранее был сделан коммит, необходимо удалить этот файл из репозитория, а затем добавить для него правило в *.gitignore* . Используйте команду *git rm* с параметром *--cached*, чтобы удалить этот файл из репозитория, но оставить его в рабочем каталоге как игнорируемый файл.


```bash
echo debug.log >> .gitignore
  
git rm --cached debug.log
rm 'debug.log'
  
git commit -m "Start ignoring debug.log"
```


## Отладка файлов .gitignore 

Если шаблоны *.gitignore* сложны или разбиты на множество файлов *.gitignore*, бывает непросто отследить, почему игнорируется определенный файл. Используйте команду *git check-ignore* с параметром *-v* (или *--verbose*), чтобы определить, какой шаблон приводит к игнорированию конкретного файла:

```bash
$ git check-ignore -v debug.log
.gitignore:3:*.log  debug.log
```


Резюме:

1. Если нужно, чтобы Git игнорировал какие-то файлы, стоит составить файл *.gitignore*.
2. Посмотреть, что игнорируется, можно с помощью команды *git status --ignored*.
3. Сам файл *.gitignore* — это обычный файл в репозитории. Его тоже стоит закоммитить.
4. Шаблонов много, но их легко найти в интернете вместе с примерами использования.