# Основные команды для работы с Git

- 22 февраля 2023


Работа с Git через терминал — это обязательная часть практики фронтендера. Однако для начинающих разработчиков этот инструмент может показаться сложным. Чтобы вам было проще учиться, мы собрали основные команды для работы с Git.

☝ В некоторых командах мы будем писать URL-адрес удалённого репозитория и название проекта в квадратных скобках, вот так — `[ссылка на удалённый репозиторий]`. Мы делаем это только для наглядности. Вам квадратные скобки ставить не нужно.

## Первоначальная настройка Git

Работа с любой программой всегда начинается с её настройки. Git можно настроить один раз и менять что-то только по мере необходимости.

**Указать имя пользователя** 
Задаёт имя пользователя, от которого будут идти коммиты. Вместо `Ivan Ivanov` нужно написать свои данные на латинице. Если имя состоит из одного слова, кавычки можно не ставить.
```
git config --global user.name "Emil Hasanov"
```


**Указать электронную почту**
Вместо `mail@gmail.com` нужно указать вашу почту. Обратите внимание, она должна совпадать с той, на которую зарегистрирован аккаунт в Гитхабе.
```
git config --global user.email hasanoveo@gmail.com
```

**Посмотреть настройки**
Параметры можно посмотреть и в конфигурационном файле, но этот способ быстрее.
```
git config --list
```

## Работа с репозиторием

**Создать репозиторий** 
Инициализирует пустой репозиторий.
```
git init
```

**Склонировать удалённый репозиторий** Проект появится в директории, где вы находились в момент клонирования.
```
git clone [ссылка на удалённый репозиторий]
```

**Связать удалённый и локальный репозитории** — `git remote add origin [ссылка на удалённый репозиторий]`.

## Работа с изменениями

Любая работа с изменениями начинается с получения последней версии проекта из удалённого репозитория. Далее вы можете внести правки в проект, добавить изменения в индекс и сделать коммит. В конце нужно отправить изменения в удалённый репозиторий или удалить, если они больше не нужны.

**Подтянуть изменения** — `git pull`. Подтягивает в локальный репозиторий последнюю версию проекта. Будьте внимательны, вызов этой команды сотрёт все незафиксированные изменения. Иногда после ввода этой команды появляется конфликт.

[Как решать проблемы в Git](https://htmlacademy.ru/blog/git/first-aid-git)

**Посмотреть статус файлов** — `git status`. Вы увидите, какие файлы изменили, удалили или добавили в проект. При этом статус «Закоммичен» не отобразится.

**Добавить файлы в индекс** — `git add [название файла]`. После ввода этой команды вы можете сделать коммит.

Есть похожие команды, например, `git add .` индексирует сразу все изменённые файлы и папки в директории, где вы находитесь. Обратите внимание, между точкой и словом `add`нужно ставить пробел. Команда `git add :/` добавляет в индекс все файлы независимо от того, в какой директории вы находитесь.

**Сделать коммит** — `git commit -m "Комментарий к коммиту"` — фиксирует изменения. До выполнения этой команды локальные изменения никуда не запишутся.

Нужно правильно разбивать изменения и давать полные комментарии к коммитам. Подробнее об этом читайте в статье «[Как оформлять коммиты](https://habrahabr.ru/company/Voximplant/blog/276695/)».

**Посмотреть историю коммитов** — `git log`. Выводит список всех коммитов. У этой команды есть разные опции, самая используемая из них — `--oneline`. Она показывает хеш в укороченном формате, ветку, в которой сделан коммит, а также текст коммита. Чтобы использовать эту опцию (как и любую другую), нужно добавить её после команды: `git log--oneline`.

**Запушить изменения** — `git push`. Отправляет все зафиксированные изменения с локального репозитория в удалённый. Это одна из самых важных команд, ведь все вышеописанные действия производятся в локальной копии репозитория. Когда вы закончите работу, эту копию нужно будет отправить в удалённый репозиторий. Только так другие участники процесса смогут получить актуальную версию.

## Работа с ветками

Работая с Git, приходится постоянно создавать и перемещаться по веткам. А иногда ветки нужно удалять или сливать.

☝ Здесь мы для примера используем `branch-name.` Вам при вводе команды нужно указать название вашей ветки.

**Создать ветку** — `git switch --create branch-name`. Добавляет новую ветку с названием `branch-name` и автоматически переключает на неё.

**Переключить ветку** — `git switch branch-name`. Вы перейдёте на уже созданную ветку `branch-name`.

Для создания и переключения веток также можно использовать `git checkout`. Эта команда появилась раньше, у неё есть множество дополнительных функций. Например, она может восстанавливать изменения в коммите. Как раз из-за такого разнообразия задач разработчики решили создать отдельную команду для переключения между ветками — `git switch`. Вы можете использовать любую из команд, однако `git switch` доступна только в версиях от 2.23.

**Посмотреть все локальные ветки** — `git branch`.

**Переименовать ветку** — `git branch -m [старое-название-ветки] [новое-название-ветки]` — переименовывает ветку. Названия нужно писать на латинице.

**Отправить ветку** — `git push origin [branch-name]` — отправляет ветку в удалённый репозиторий.

**Удалить ветки** — `git branch --delete [branch-name]`. Команда удаляет ветку `[branch-name]`в локальном репозитории. Если нужно избавиться от ветки в удалённом репозитории, используйте `git push --delete origin [branch-name]`.

**Влить ветки** — `git merge [branch-name]`. Вливает ветку `branch-name` в ветку, в которой вы находитесь.

**Перебазировать коммиты** — `git rebase [branch-name]`. Перебазирует коммиты из ветки, в которой вы находитесь, в ветку `[branch-name]`.

**Создать точную копию коммитов** — `git cherry-pick`. Команду часто совмещают с `git merge` и `git rebase`, чтобы сохранить линейную историю коммитов. То есть создаётся точная копия коммитов, выполняется перебазирование и слияние веток.

## Откладывание и удаление

**Отложить изменения** — `git stash push`. Откладывает изменения, чтобы вы, например, могли срочно перейти к другой задаче. Чтобы отложить только часть изменений, используйте `git stash --patch`.

**Вернуть отложенные изменения** — `git stash pop`.

**Отменить изменения, не добавленные в индекс** — `git restore [название файла]`. Удалит изменения в одном файле. Чтобы удалить изменения во всех файлах, используйте `git restore :/`.

**Отменить изменения, добавленные в индекс** — `git reset --hard`. Возвращает изменения из индекса и полностью их отменяет.

**Удалить коммит** — `git revert [195dfb0]`. Вместо `[195dfb0]` указывается хеш коммита, его можно узнать с помощью команды `git log`.

**Отменить слияние с конфликтом** — `git merge --abort`. Используется, когда нет времени решать конфликт прямо здесь и сейчас.

**Удалить лишнее** — `git clean`. Команда «наводит чистоту» — удаляет неотслеживаемые файлы из рабочего каталога.







…or create a new repository on the command line

  

echo "# obsidian" >> README.md

  git init

  git add README.md

  git commit -m "first commit"

  git branch -M main

  git remote add origin https://github.com/hasanoveo/obsidian.git

  git push -u origin main

…or push an existing repository from the command line

  

git remote add origin https://github.com/hasanoveo/obsidian.git

  git branch -M main

  git push -u origin main

  

  

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