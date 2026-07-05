# Задание 1: Container Scanning

## 🎯 Цель
Настроить сканирование Docker образов на уязвимости.

## 📋 Задачи

### 1. Trivy
- [ ] Установить Trivy
- [ ] Сканировать образ
- [ ] Понимать результаты

### 2. CI/CD Integration
- [ ] Добавить в pipeline
- [ ] Блокировать уязвимые образы
- [ ] Сохранять отчеты

### 3. Remediation
- [ ] Исправить уязвимости
- [ ] Обновить базовые образы
- [ ] Пересобрать образ

## 🔧 Решение

```yaml
# GitHub Actions
- name: Security scan
  uses: aquasecurity/trivy-action@master
  with:
    image-ref: app:${{ github.sha }}
    format: table
    exit-code: '1'
    ignore-unfixed: true
```

```bash
# Локальное сканирование
trivy image nginx:alpine
trivy image --severity HIGH,CRITICAL app:latest
```

## ✅ Проверка
- [ ] Trivy установлен
- [ ] Сканирование работает
- [ ] CI/CD интеграция
- [ ] Блокировка уязвимых образов
- [ ] Remediation выполнен

## 📖 Документация
- [Trivy Docs](https://aquasecurity.github.io/trivy/)
- [OWASP Docker Security](https://cheatsheetseries.owasp.org/cheatsheets/Docker_Security_Cheat_Sheet.html)
- [CIS Docker Benchmark](https://www.cisecurity.org/benchmark/docker)