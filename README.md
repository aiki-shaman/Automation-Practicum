# Git / GitHub — учебный конспект

Этот README.md можно использовать как личную шпаргалку по Git, GitHub и базовой работе в консоли.

---

## 1. Что такое Git

**Git** — это система контроля версий.

Она помогает:

- сохранять историю изменений в проекте;
- возвращаться к старым версиям файлов;
- работать с ветками;
- понимать, кто, что и когда изменил;
- работать в команде без хаоса.

Простыми словами: Git — это как «история сохранений» для проекта, но намного мощнее.

---

## 2. Что такое GitHub

**GitHub** — это онлайн-сервис для хранения Git-репозиториев.

Git работает локально на компьютере, а GitHub хранит копию проекта в интернете.

Похожие сервисы:

- GitHub;
- GitLab;
- Bitbucket.

На работе может использоваться GitLab, а на учебе — GitHub. Основные команды Git почти одинаковые для всех этих сервисов.

---

## 3. Основные понятия

### Repository / Репозиторий

Репозиторий — это проект, который отслеживается Git.

Он может быть:

- **local repository** — локальный репозиторий на компьютере;
- **remote repository** — удаленный репозиторий, например на GitHub или GitLab.

---

### Commit / Коммит

Коммит — это сохраненное состояние проекта.

Коммит можно воспринимать как контрольную точку.

Обычно коммит содержит:

- изменения в файлах;
- сообщение с описанием изменений;
- автора;
- дату и время.

Пример сообщения:

```bash
git commit -m "Add README file"
```

---

### Branch / Ветка

Ветка — это отдельная линия разработки.

Главная ветка часто называется:

```bash
main
```

или

```bash
master
```

Ветки нужны, чтобы работать над новой задачей отдельно от основного кода.

---

### Remote / Удаленный репозиторий

Remote — это ссылка на удаленный репозиторий.

Чаще всего удаленный репозиторий называется:

```bash
origin
```

Проверить remote:

```bash
git remote -v
```

Пример:

```bash
origin  git@github.com:username/project-name.git (fetch)
origin  git@github.com:username/project-name.git (push)
```

---

### Working Directory / Рабочая директория

Это папка проекта, где мы редактируем файлы.

---

### Staging Area / Индекс

Это промежуточная зона перед коммитом.

Файлы попадают туда через команду:

```bash
git add
```

---

## 4. Установка и проверка Git

Проверить, установлен ли Git:

```bash
git --version
```

Пример результата:

```bash
git version 2.53.0.windows.2
```

Если версия отображается, значит Git уже установлен.

---

## 5. Базовые команды консоли

### Посмотреть текущую папку

```bash
pwd
```

### Посмотреть список файлов

```bash
ls
```

На Windows также может работать:

```bash
dir
```

### Перейти в папку

```bash
cd folder-name
```

### Перейти на уровень выше

```bash
cd ..
```

### Создать папку

```bash
mkdir folder-name
```

### Создать файл

```bash
touch README.md
```

В PowerShell можно использовать:

```powershell
New-Item README.md
```

### Очистить консоль

```bash
clear
```

В Windows CMD:

```cmd
cls
```

---

## 6. Настройка Git

Перед работой нужно указать имя и email.

```bash
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
```

Проверить настройки:

```bash
git config --list
```

Или отдельно:

```bash
git config user.name
git config user.email
```

---

## 7. Инициализация проекта

Перейти в папку проекта:

```bash
cd project-folder
```

Создать Git-репозиторий:

```bash
git init
```

После этого Git начнет отслеживать проект.

---

## 8. Проверка статуса

Команда:

```bash
git status
```

Она показывает:

- какие файлы изменены;
- какие файлы еще не отслеживаются;
- какие файлы уже добавлены в staging area;
- есть ли что коммитить.

---

## 9. Добавление файлов в Git

Добавить один файл:

```bash
git add README.md
```

Добавить все изменения:

```bash
git add .
```

После `git add` изменения подготовлены к коммиту.

---

## 10. Создание коммита

Создать коммит:

```bash
git commit -m "Add README file"
```

Хорошее сообщение коммита должно коротко объяснять, что было сделано.

Примеры:

```bash
git commit -m "Initial commit"
git commit -m "Add project description"
git commit -m "Fix typo in README"
git commit -m "Update test cases"
```

---

## 11. Просмотр истории коммитов

Полная история:

```bash
git log
```

Короткий вариант:

```bash
git log --oneline
```

Пример:

```bash
a1b2c3d Add README file
e4f5g6h Initial commit
```

---

## 12. Работа с ветками

Посмотреть список веток:

```bash
git branch
```

Создать новую ветку:

```bash
git branch feature-name
```

Переключиться на ветку:

```bash
git switch feature-name
```

Или старый вариант:

```bash
git checkout feature-name
```

Создать ветку и сразу перейти в нее:

```bash
git switch -c feature-name
```

Или:

```bash
git checkout -b feature-name
```

---

## 13. Слияние веток

Перейти в основную ветку:

```bash
git switch main
```

Слить другую ветку в текущую:

```bash
git merge feature-name
```

---

## 14. Подключение GitHub-репозитория

Если локальный проект уже создан, а на GitHub создан пустой репозиторий, нужно добавить remote.

Пример для SSH:

```bash
git remote add origin git@github.com:username/repository-name.git
```

Пример для HTTPS:

```bash
git remote add origin https://github.com/username/repository-name.git
```

Проверить remote:

```bash
git remote -v
```

---

## 15. Первый push на GitHub

Если главная ветка называется `main`:

```bash
git push -u origin main
```

Если главная ветка называется `master`:

```bash
git push -u origin master
```

Флаг `-u` связывает локальную ветку с удаленной. После этого можно использовать просто:

```bash
git push
```

---

## 16. Получение изменений с GitHub

Забрать изменения и сразу применить:

```bash
git pull
```

Забрать информацию об изменениях, но не применять автоматически:

```bash
git fetch
```

---

## 17. Клонирование репозитория

Склонировать репозиторий по HTTPS:

```bash
git clone https://github.com/username/repository-name.git
```

Склонировать репозиторий по SSH:

```bash
git clone git@github.com:username/repository-name.git
```

---

## 18. Типовой workflow работы с Git

Обычный порядок работы:

```bash
git status
git add .
git commit -m "Describe changes"
git push
```

Более полный вариант:

```bash
git pull
git switch -c new-feature
# внести изменения в файлы
git status
git add .
git commit -m "Add new feature"
git push -u origin new-feature
```

---

## 19. Регистрация на GitHub

Общий порядок:

1. Открыть сайт GitHub.
2. Создать аккаунт.
3. Подтвердить email.
4. Создать новый repository.
5. Скопировать ссылку на репозиторий.
6. Подключить local repository через `git remote add origin`.
7. Сделать `git push`.

---

## 20. SSH-ключ для GitHub

SSH-ключ нужен, чтобы GitHub понимал, что именно этот компьютер имеет право пушить код в репозиторий.

### Проверить существующие SSH-ключи

```bash
ls ~/.ssh
```

Часто ключи называются:

```bash
id_ed25519
id_ed25519.pub
id_rsa
id_rsa.pub
```

Файл `.pub` — это публичный ключ. Его можно добавлять в GitHub.

---

### Создать новый SSH-ключ

```bash
ssh-keygen -t ed25519 -C "your-email@example.com"
```

Если `ed25519` не поддерживается:

```bash
ssh-keygen -t rsa -b 4096 -C "your-email@example.com"
```

---

### Запустить ssh-agent

```bash
eval "$(ssh-agent -s)"
```

Добавить ключ:

```bash
ssh-add ~/.ssh/id_ed25519
```

---

### Скопировать публичный ключ

```bash
cat ~/.ssh/id_ed25519.pub
```

Скопировать результат и добавить его в GitHub:

```text
GitHub → Settings → SSH and GPG keys → New SSH key
```

---

### Проверить подключение к GitHub

Правильная команда:

```bash
ssh -T git@github.com
```

Неправильно:

```bash
ssh -T git@github.com~
```

Символ `~` в конце ломает адрес, поэтому появляется ошибка:

```text
Could not resolve hostname github.com~
```

---

## 21. Ошибка Permission denied (publickey)

Ошибка:

```text
git@github.com: Permission denied (publickey).
fatal: Could not read from remote repository.
```

Означает, что GitHub не смог подтвердить SSH-ключ.

Возможные причины:

1. SSH-ключ не создан.
2. SSH-ключ не добавлен в ssh-agent.
3. Публичный ключ не добавлен в GitHub.
4. Remote использует SSH, но SSH не настроен.
5. У пользователя нет доступа к репозиторию.
6. Репозиторий не существует или указан неверно.

---

### Что проверить

Проверить remote:

```bash
git remote -v
```

Проверить SSH-соединение:

```bash
ssh -T git@github.com
```

Проверить ключи:

```bash
ls ~/.ssh
```

Добавить ключ в agent:

```bash
ssh-add ~/.ssh/id_ed25519
```

---

### Альтернатива: использовать HTTPS вместо SSH

Если SSH не хочется настраивать, можно заменить remote на HTTPS:

```bash
git remote set-url origin https://github.com/username/repository-name.git
```

Проверить:

```bash
git remote -v
```

После этого push:

```bash
git push -u origin main
```

или:

```bash
git push -u origin master
```

---

## 22. Файл .gitignore

`.gitignore` — это файл, в котором указывают, что Git не должен отслеживать.

Например:

```gitignore
.idea/
target/
build/
*.log
.env
node_modules/
```

Это полезно, чтобы не коммитить:

- временные файлы;
- логи;
- настройки IDE;
- секреты;
- зависимости;
- сгенерированные файлы.

---

## 23. README.md

`README.md` — это главный файл с описанием проекта.

Обычно в нем пишут:

- название проекта;
- описание;
- как установить проект;
- как запустить проект;
- какие технологии используются;
- список команд;
- примеры использования;
- важные заметки.

---

## 24. Markdown

README обычно пишется в формате Markdown.

### Заголовки

```markdown
# Заголовок 1
## Заголовок 2
### Заголовок 3
```

### Список

```markdown
- item 1
- item 2
- item 3
```

### Код

````markdown
```bash
git status
```
````

### Жирный текст

```markdown
**важный текст**
```

---

## 25. Полезные команды Git

### Проверить статус

```bash
git status
```

### Добавить все изменения

```bash
git add .
```

### Сделать коммит

```bash
git commit -m "Message"
```

### Отправить изменения

```bash
git push
```

### Получить изменения

```bash
git pull
```

### Посмотреть историю

```bash
git log --oneline
```

### Посмотреть ветки

```bash
git branch
```

### Создать и перейти в новую ветку

```bash
git switch -c branch-name
```

### Переключиться на ветку

```bash
git switch branch-name
```

### Добавить remote

```bash
git remote add origin repository-url
```

### Изменить remote

```bash
git remote set-url origin repository-url
```

### Проверить remote

```bash
git remote -v
```

---

## 26. Частые ошибки новичка

### 1. Забыли сделать git add

Если сделать только:

```bash
git commit -m "Message"
```

Git может написать, что нечего коммитить.

Сначала нужно:

```bash
git add .
```

---

### 2. Пуш не в ту ветку

Нужно проверить текущую ветку:

```bash
git branch
```

---

### 3. Remote не настроен

Ошибка может быть из-за отсутствия удаленного репозитория.

Проверка:

```bash
git remote -v
```

---

### 4. Неправильный адрес репозитория

Например, опечатка в имени пользователя или репозитория.

Проверить:

```bash
git remote -v
```

---

### 5. SSH не настроен

Если remote выглядит так:

```bash
git@github.com:username/repository.git
```

значит используется SSH. Для него нужен SSH-ключ.

---

## 27. Мини-инструкция: создать проект и отправить на GitHub

```bash
mkdir my-project
cd my-project
git init
touch README.md
git add README.md
git commit -m "Initial commit"
git branch -M main
git remote add origin git@github.com:username/my-project.git
git push -u origin main
```

Если используется `master`:

```bash
git push -u origin master
```

---

## 28. Мини-инструкция: обновить проект

```bash
git status
git add .
git commit -m "Update project"
git push
```

---

## 29. Мини-инструкция: скачать проект с GitHub

```bash
git clone git@github.com:username/repository-name.git
cd repository-name
```

Или через HTTPS:

```bash
git clone https://github.com/username/repository-name.git
cd repository-name
```

---

## 30. Главное, что нужно запомнить

Самые важные команды:

```bash
git status
git add .
git commit -m "Message"
git push
git pull
git log --oneline
git branch
git switch
git remote -v
```

Самая частая логика работы:

1. Изменил файл.
2. Проверил статус.
3. Добавил изменения.
4. Сделал коммит.
5. Отправил на GitHub/GitLab.

```bash
git status
git add .
git commit -m "Describe changes"
git push
```

---

## 31. Полезная мысль

GitHub и GitLab могут отличаться интерфейсом, но Git-команды остаются почти одинаковыми.

Если научиться работать с Git в консоли, эти знания помогут и на GitHub, и на GitLab, и почти на любом IT-проекте.
