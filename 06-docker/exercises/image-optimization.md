# Задание 1: Image Optimization

## 🎯 Цель
Собрать оптимизированный Docker образ с минимальным размером.

## 📋 Задачи

### 1. Multi-stage build
- [ ] Использовать builder stage
- [ ] Скопировать артефакты из builder
- [ ] Использовать alpine образ

### 2. Security
- [ ] Non-root user
- [ ] Healthcheck
- [ ] .dockerignore

### 3. Оптимизация
- [ ] Размер < 100MB
- [ ] Минимальное количество слоев
- [ ] Кеширование зависимостей

## 🔧 Решение

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

## ✅ Проверка
- [ ] Образ собирается
- [ ] Размер < 100MB
- [ ] Healthcheck работает
- [ ] Non-root user
- [ ] Приложение работает

## 📖 Документация
- [Docker Best Practices](https://docs.docker.com/develop/develop-images/dockerfile_best-practices/)
- [Multi-stage builds](https://docs.docker.com/build/building/multi-stage/)