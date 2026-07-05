# Задание 2: GitHub Actions

## 🎯 Цель
Создать CI/CD pipeline в GitHub Actions.

## 📋 Задачи

### 1. CI Pipeline
- [ ] Тестирование PR
- [ ] Сборка образа
- [ ] Security scanning

### 2. CD Pipeline
- [ ] Автодеплой на staging
- [ ] Manual approval для production
- [ ] Slack уведомления

### 3. Оптимизация
- [ ] Cache зависимостей
- [ ] Matrix builds
- [ ] Secrets

## 🔧 Решение

```yaml
name: CI/CD Pipeline

on:
  push:
    branches: [ main ]
  pull_request:
    branches: [ main ]

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v3
    - name: Run tests
      run: npm test

  build:
    needs: test
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v3
    - name: Build Docker image
      run: docker build -t app:${{ github.sha }} .
    - name: Security scan
      uses: aquasecurity/trivy-action@master
      with:
        image-ref: app:${{ github.sha }}

  deploy-staging:
    needs: build
    runs-on: ubuntu-latest
    if: github.ref == 'refs/heads/main'
    steps:
    - name: Deploy to staging
      run: kubectl apply -f k8s/staging/

  deploy-production:
    needs: deploy-staging
    runs-on: ubuntu-latest
    environment: production
    steps:
    - name: Deploy to production
      run: kubectl apply -f k8s/production/
```

## ✅ Проверка
- [ ] CI запускается при PR
- [ ] Тесты выполняются
- [ ] Docker образ собирается
- [ ] Security scan работает
- [ ] Deploy на staging
- [ ] Manual approval для production

## 📖 Документация
- [GitHub Actions](https://docs.github.com/en/actions)
- [Workflow Syntax](https://docs.github.com/en/actions/using-workflows/workflow-syntax-for-github-actions)
- [Trivy Action](https://github.com/aquasecurity/trivy-action)