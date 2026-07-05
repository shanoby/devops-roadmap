# Задание 2: K8s in Cloud

## 🎯 Цель
Развернуть Kubernetes кластер в облаке.

## 📋 Задачи

### 1. EKS/AKS/GKE
- [ ] Создать кластер
- [ ] Настроить node groups
- [ ] Настроить networking

### 2. Load Balancer
- [ ] Создать Service LoadBalancer
- [ ] Настроить DNS
- [ ] SSL сертификат

### 3. Monitoring
- [ ] Установить metrics server
- [ ] Настроить CloudWatch/Monitor
- [ ] Алерты

## 🔧 Решение (EKS)

```bash
# Создание кластера
eksctl create cluster \
  --name my-cluster \
  --region us-west-2 \
  --nodegroup-name my-nodes \
  --node-type t3.medium \
  --nodes 3

# Приложение
kubectl apply -f app-deployment.yaml

# Load Balancer
kubectl expose deployment app --port=80 --type=LoadBalancer
```

## ✅ Проверка
- [ ] Кластер создан
- [ ] Node groups работают
- [ ] Load Balancer доступен
- [ ] DNS запись создана
- [ ] SSL сертификат валиден

## 📖 Документация
- [EKS Docs](https://docs.aws.amazon.com/eks/)
- [AKS Docs](https://learn.microsoft.com/en-us/azure/aks/)
- [GKE Docs](https://cloud.google.com/kubernetes-engine/docs)