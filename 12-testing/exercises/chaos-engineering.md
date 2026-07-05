# Задание 2: Chaos Engineering

## 🎯 Цель
Провести chaos-эксперимент на Kubernetes кластере.

## 📋 Задачи

### 1. Litmus Setup
- [ ] Установить Litmus
- [ ] Настроить chaos experiments
- [ ] Понимать workflow

### 2. Experiments
- [ ] Pod deletion
- [ ] Network latency
- [ ] CPU stress

### 3. Analysis
- [ ] Анализировать результаты
- [ ] Проверять pod restarts
- [ ] Мониторить метрики

## 🔧 Решение

```yaml
# pod-delete.yaml
apiVersion: litmuschaos.io/v1alpha1
kind: ChaosEngine
metadata:
  name: pod-delete
spec:
  engineState: "active"
  appinfo:
    appns: default
    applabel: "app=myapp"
  chaosServiceAccount: litmus-admin
  experiments:
    - name: pod-delete
      spec:
        components:
          env:
            - name: TOTAL_CHAOS_DURATION
              value: "30"
            - name: POD_DELETE_COUNT
              value: "1"
```

```bash
# Запуск эксперимента
kubectl apply -f pod-delete.yaml
kubectl get chaosengine pod-delete -o yaml
```

## ✅ Проверка
- [ ] Litmus установлен
- [ ] Experiment создан
- [ ] Pod deletion работает
- [ ] Network latency работает
- [ ] Результаты проанализированы

## 📖 Документация
- [Litmus Docs](https://litmuschaos.io/docs/)
- [Chaos Engineering Principles](https://principlesofchaos.org/)
- [Kubernetes Chaos Engineering](https://kubernetes.io/blog/2020/08/11/chaos-engineering-with-kubernetes/)