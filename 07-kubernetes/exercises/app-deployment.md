# Задание 1: Application Deployment

## 🎯 Цель
Развернуть приложение в Kubernetes с полной конфигурацией.

## 📋 Задачи

### 1. Deployment
- [ ] Создать Deployment с 3 репликами
- [ ] Настроить rolling update
- [ ] Добавить resource limits

### 2. Service и Ingress
- [ ] Service (ClusterIP)
- [ ] Ingress с TLS
- [ ] Health checks

### 3. Конфигурация
- [ ] ConfigMap для конфигурации
- [ ] Secret для паролей
- [ ] Environment variables

## 🔧 Решение

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: app-deployment
spec:
  replicas: 3
  selector:
    matchLabels:
      app: myapp
  template:
    metadata:
      labels:
        app: myapp
    spec:
      containers:
      - name: app
        image: nginx:alpine
        ports:
        - containerPort: 80
        resources:
          limits:
            cpu: "500m"
            memory: "128Mi"
        envFrom:
        - configMapRef:
            name: app-config
        livenessProbe:
          httpGet:
            path: /
            port: 80
        readinessProbe:
          httpGet:
            path: /
            port: 80
---
apiVersion: v1
kind: Service
metadata:
  name: app-service
spec:
  selector:
    app: myapp
  ports:
  - port: 80
    targetPort: 80
```

## ✅ Проверка
- [ ] Deployment создан
- [ ] 3 реплики работают
- [ ] Service доступен
- [ ] Ingress работает
- [ ] Health checks работают

## 📖 Документация
- [Kubernetes Deployment](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/)
- [Kubernetes Service](https://kubernetes.io/docs/concepts/services-networking/service/)
- [Kubernetes Ingress](https://kubernetes.io/docs/concepts/services-networking/ingress/)