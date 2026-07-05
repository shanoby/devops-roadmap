# Тесты: Docker

## Теория

### Вопросы

1. **Что такое слой (layer) в Docker образе?**
   - a) Файловая система
   - b) Изолированная файловая система
   - c) Коммит в git

2. **Какая команда показывает запущенные контейнеры?**
   - a) docker ps
   - b) docker images
   - c) docker run

3. **Что такое multi-stage build?**
   - a) Сборка в несколько этапов
   - b) Сборка с несколькими базовыми образами
   - c) Сборка в разных контейнерах

### Ответы
1. b) Изолированная файловая система
2. a) docker ps
3. b) Сборка с несколькими базовыми образами

## Практика

### Задание 1: Оптимизированный Dockerfile

Создайте Dockerfile для Node.js приложения:
- Используйте multi-stage build
- Размер образа < 100MB
- Healthcheck
- Непривилегированный пользователь

**Решение:**
```dockerfile
# Build stage
FROM node:18-alpine AS builder
WORKDIR /app
COPY package*.json ./
RUN npm ci --only=production
COPY . .
RUN npm run build

# Production stage
FROM node:18-alpine AS production
WORKDIR /app
COPY --from=builder /app/dist ./dist
COPY --from=builder /app/node_modules ./node_modules
COPY --from=builder /app/package*.json ./

RUN addgroup -g 1001 -S nodejs
RUN adduser -S nextjs -u 1001
USER nextjs

EXPOSE 3000
HEALTHCHECK --interval=30s --timeout=3s --start-period=5s --retries=3 \
    CMD node healthcheck.js

CMD ["node", "dist/index.js"]
```

### Задание 2: docker-compose.yml

Создайте docker-compose с 3 сервисами:
- web (nginx)
- db (postgres)
- cache (redis)

**Решение:**
```yaml
version: '3.8'

services:
  web:
    image: nginx:alpine
    ports:
      - "80:80"
    volumes:
      - ./nginx.conf:/etc/nginx/nginx.conf
    depends_on:
      - db
      - cache
    networks:
      - app-network

  db:
    image: postgres:15-alpine
    environment:
      POSTGRES_DB: myapp
      POSTGRES_USER: admin
      POSTGRES_PASSWORD: secret
    volumes:
      - db-data:/var/lib/postgresql/data
    networks:
      - app-network

  cache:
    image: redis:7-alpine
    volumes:
      - cache-data:/data
    networks:
      - app-network

volumes:
  db-data:
  cache-data:

networks:
  app-network:
    driver: bridge
```

## Самоконтроль

- [ ] Понимаю разницу между image и container
- [ ] Умею писать оптимизированные Dockerfile
- [ ] Могу настроить docker-compose
- [ ] Понимаю работу сетей в Docker