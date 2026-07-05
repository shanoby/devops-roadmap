# 6. Docker

## 🎯 Что изучить

### Основы
- Образы и контейнеры
- Dockerfile (инструкции, best practices)
- docker-compose (services, networks, volumes)
- Сети (bridge, host, overlay)

### Продвинуто
- Многоэтапная сборка (multi-stage)
- Security scanning (Trivy, Clair)
- Registry (Docker Hub, ECR, GCR)
- Rootless контейнеры

## 📖 Документация
- [Docker Documentation](https://docs.docker.com/)
- [Docker Curriculum](https://docker-curriculum.com/)

## ✅ Тесты для самоконтроля

### Тест 1: Dockerfile
```dockerfile
# Соберите образ:
# - База: alpine
# - Приложение: nginx
# - Размер < 50MB
# - Healthcheck
# - Non-root user
```

### Тест 2: docker-compose
- 3 сервиса: web, db, cache
- Настроить networks
- Volumes для данных

## 📁 Практические задания
- [Задание 1: Image Optimization](exercises/image-optimization.md)
- [Задание 2: Multi-container App](exercises/multi-container.md)