# Тесты: Kubernetes

## Теория

### Вопросы

1. **Что такое Pod в Kubernetes?**
   - a) Виртуальная машина
   - b) Группа контейнеров
   - c) Сервис

2. **Какой объект обеспечивает доступ к Pod извне?**
   - a) ConfigMap
   - b) Service
   - c) Secret

3. **Что такое Namespace?**
   - a) Пространство имён
   - b) Папка
   - c) Сеть

### Ответы
1. b) Группа контейнеров
2. b) Service
3. a) Пространство имён

## Практика

### Задание 1: Deployment с ConfigMap

Создайте Deployment с:
- 3 репликами
- ConfigMap для конфигурации
- Service (ClusterIP)
- Health checks

**Решение:**
```yaml
# configmap.yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: app-config
data:
  APP_ENV: production
  LOG_LEVEL: info
---
# deployment.yaml
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
        envFrom:
        - configMapRef:
            name: app-config
        livenessProbe:
          httpGet:
            path: /
            port: 80
          initialDelaySeconds: 30
          periodSeconds: 10
        readinessProbe:
          httpGet:
            path: /
            port: 80
          initialDelaySeconds: 5
          periodSeconds: 5
---
# service.yaml
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
  type: ClusterIP
```

### Задание 2: Helm Chart

Создайте Helm chart для приложения:
- Values для настройки реплик
- Шаблон Deployment
- Шаблон Service

**Решение:**
```yaml
# values.yaml
replicaCount: 3
image:
  repository: nginx
  tag: alpine
  pullPolicy: IfNotPresent

service:
  type: ClusterIP
  port: 80
```

```yaml
# templates/deployment.yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: {{ include "app.fullname" . }}
spec:
  replicas: {{ .Values.replicaCount }}
  selector:
    matchLabels:
      {{- include "app.selectorLabels" . | nindent 8 }}
  template:
    metadata:
      labels:
        {{- include "app.selectorLabels" . | nindent 8 }}
    spec:
      containers:
      - name: {{ .Chart.Name }}
        image: "{{ .Values.image.repository }}:{{ .Values.image.tag }}"
        imagePullPolicy: {{ .Values.image.pullPolicy }}
```

## Самоконтроль

- [ ] Понимаю разницу между Deployment и StatefulSet
- [ ] Умею работать с kubectl
- [ ] Могу создать Helm chart
- [ ] Понимаю принципы health checks