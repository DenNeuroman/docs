# 🐙 Git + GitHub — Шпаргалка

Справочник по основным командам и процессам для работы с Git и GitHub.

---

## ⚙️ Первоначальная настройка

```bash
# Настроить имя и email (один раз после установки Git)
git config --global user.name "Твоё Имя"
git config --global user.email "твой@email.com"

# Проверить настройки
git config --global --list
```

---

## 🆕 Создание нового репозитория

### Шаг 1 — Создать на GitHub
1. Зайти на github.com → кнопка **+** → **New repository**
2. Заполнить: название, описание, поставить галочку **Add a README file**
3. Нажать **Create repository**

### Шаг 2 — Клонировать на компьютер
```bash
cd '/c/!MyGit'
git clone https://github.com/твой-логин/название-репо.git
cd название-репо
```

### Шаг 3 — Создать структуру папок
```bash
mkdir -p папка1/подпапка
mkdir -p папка2
```

---

## 📋 Основной workflow (каждый день)

```bash
# 1. Перейти в папку репозитория
cd '/c/!MyGit/название-репо'

# 2. Проверить статус изменений
git status

# 3. Добавить все изменения
git add .

# 4. Создать коммит с описанием
git commit -m "тип: описание изменения"

# 5. Отправить на GitHub
git push origin main
```

---

## 💬 Как писать сообщения коммитов

Формула:
```bash
git commit -m "тип: что сделал"
```

**Тип** — выбираешь из списка:

| Тип | Когда использовать | Пример |
|-----|--------------------|--------|
| `feat:` | Добавил новую функцию или файл | `feat: add contact form fix` |
| `fix:` | Исправил ошибку | `fix: correct From header` |
| `docs:` | Добавил или изменил документацию | `docs: add git cheatsheet` |
| `refactor:` | Переделал код без изменения поведения | `refactor: simplify mail block` |
| `chore:` | Служебные изменения | `chore: update version to 1.2` |

**Глаголы для описания** — коротко по-английски:

| Глагол | Значение |
|--------|----------|
| `add` | добавил |
| `update` | обновил |
| `fix` | исправил |
| `remove` | удалил |
| `create` | создал |

**Примеры:**
```bash
git commit -m "docs: add seo checklist"
git commit -m "docs: update README catalog"
git commit -m "feat: add contact form ocmod"
git commit -m "fix: correct From header in mail"
git commit -m "chore: update version to 1.3"
```

> 💡 Главное правило — читая сообщение коммита через год, ты должен понять **что именно было сделано** без открытия файлов.

---

## 📖 Справочник команд

### Статус и история
```bash
git status              # состояние файлов
git log --oneline       # краткая история коммитов
git log --oneline -10   # последние 10 коммитов
git diff                # что изменилось в файлах
```

### Работа с файлами
```bash
git add .               # добавить все файлы
git add имя_файла       # добавить конкретный файл
git restore имя_файла   # отменить изменения в файле
git rm имя_файла        # удалить файл из репозитория
```

### Синхронизация с GitHub
```bash
git push origin main    # отправить на GitHub
git pull                # получить изменения с GitHub
git fetch               # проверить изменения без применения
```

### Отмена изменений
```bash
# Отменить последний коммит (файлы останутся изменёнными)
git reset --soft HEAD~1

# Полностью отменить последний коммит (файлы вернутся к прежнему виду)
git reset --hard HEAD~1
```

---

## 🗂️ Работа с ветками

```bash
git branch                    # список веток
git branch название           # создать ветку
git checkout название         # переключиться на ветку
git checkout -b название      # создать и сразу переключиться
git merge название            # слить ветку в текущую
git branch -d название        # удалить ветку
```

---

## ⚠️ Частые проблемы

| Проблема | Решение |
|----------|---------|
| `!MyGit: event not found` | Используй одинарные кавычки: `cd '/c/!MyGit'` |
| Вставка не работает в Git Bash | `Shift+Insert` или правая кнопка → Paste |
| `mkdir -p` не работает | Используй Git Bash, не Git CMD |
| `nothing to commit` | Файл не сохранился в нужную папку, проверь путь |
| `LF will be replaced by CRLF` | Предупреждение, не ошибка — игнорируй |

---

## 📁 Структура репозитория docs