# 6. Docker

## 🎯 Что изучить

### Основы
- **Образы и контейнеры** - image, container, layer, registry
- **Dockerfile** - инструкции (FROM, RUN, COPY, ADD, CMD, ENTRYPOINT, ENV, EXPOSE, VOLUME)
- **docker-compose** - services, networks, volumes, environment, depends_on
- **Сети** - bridge, host, overlay, macvlan, none

### Продвинуто
- **Многоэтапная сборка** - multi-stage, builder pattern
- **Security scanning** - Trivy, Clair, Snyk, Docker Scout
- **Registry** - Docker Hub, ECR, GCR, Harbor, quay.io
- **Rootless контейнеры** - безопасность, user namespaces
- **Docker Swarm** - оркестрация, services, secrets

## 📖 Документация
- [Docker Documentation](https://docs.docker.com/) - официальная документация
- [Docker Curriculum](https://docker-curriculum.com/) - интерактивный курс
- [Docker Best Practices](https://docs.docker.com/develop/develop-images/dockerfile_best-practices/) - best practices
- [Docker Compose](https://docs.docker.com/compose/) - compose документация

## ✅ Чекпоинты для самоконтроля

### Чекпоинт 1: Основы
- [ ] Понимаю разницу между image и container
- [ ] Могу писать Dockerfile
- [ ] Понимаю lifecycle контейнера
- [ ] Могу использовать docker-compose
- [ ] Понимаю сети Docker

### Чекпоинт 2: Dockerfile
- [ ] Понимаю инструкции Dockerfile
- [ ] Могу использовать .dockerignore
- [ ] Понимаю layer cache
- [ ] Могу оптимизировать размер образа
- [ ] Понимаю healthcheck

### Чекпоинт 3: Продвинуто
- [ ] Могу писать multi-stage Dockerfile
- [ ] Понимаю security scanning
- [ ] Могу работать с registry
- [ ] Понимаю rootless контейнеры
- [ ] Понимаю Docker Swarm

## 📁 Практические задания
- [Задание 1: Image Optimization](exercises/image-optimization.md)
- [Задание 2: Multi-container App](exercises/multi-container.md)