# Задание 1: Git Workflow

## 🎯 Цель
Смоделировать командную разработку с Git Flow.

## 📋 Задачи

### 1. Настройка репозитория
- [ ] Создать репозиторий
- [ ] Настроить ветки (main, develop)
- [ ] Добавить .gitignore

### 2. Feature development
- [ ] Создать feature ветку
- [ ] Внести изменения
- [ ] Создать pull request
- [ ] Code review

### 3. Release
- [ ] Создать release ветку
- [ ] Тестирование
- [ ] Merge в main и develop
- [ ] Tag версии

## 🔧 Команды

```bash
# Настройка
git init
git checkout -b develop
git checkout -b main

# Feature
git checkout -b feature/new-feature develop
# ... внести изменения ...
git add .
git commit -m "Add new feature"
git push origin feature/new-feature

# PR -> merge -> delete branch

# Release
git checkout -b release/1.0.0 develop
# ... тестирование ...
git checkout main
git merge release/1.0.0
git tag -a v1.0.0 -m "Release 1.0.0"
git checkout develop
git merge release/1.0.0
```

## ✅ Проверка
- [ ] Ветки созданы корректно
- [ ] Feature ветка смержена
- [ ] Release процесс работает
- [ ] Tag создан
- [ ] .gitignore настроен

## 📖 Документация
- [Git Flow](https://nvie.com/posts/a-successful-git-branching-model/)
- [GitHub Flow](https://docs.github.com/en/get-started/quickstart/github-flow)
- [Conventional Commits](https://www.conventionalcommits.org/)