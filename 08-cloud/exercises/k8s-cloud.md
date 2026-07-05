# Задание 2: K8s in Cloud (Self-hosted)

## 🎯 Цель
Развернуть Kubernetes кластер локально (self-hosted) с Load Balancer.

## 📋 Задачи

### 1. Local K8s
- [ ] Установить kind/minikube/k3s
- [ ] Создать кластер
- [ ] Настроить ingress controller

### 2. Load Balancer
- [ ] Установить MetalLB (для kind)
- [ ] Создать Service LoadBalancer
- [ ] Настроить DNS (hosts файл)

### 3. Monitoring
- [ ] Установить metrics server
- [ ] Настроить Prometheus
- [ ] Алерты

## 🔧 Решение (kind)

```bash
# Установка kind
curl -Lo ./kind https://kind.sigs.k8s.io/dl/v0.20.0/kind-linux-amd64
chmod +x ./kind
sudo mv ./kind /usr/local/bin/kind

# Создание кластера с MetalLB
cat <<EOF | kind create cluster --config=-
kind: Cluster
apiVersion: kind.x-k8s.io/v1alpha4
networking:
  disableDefaultCNI: false
nodes:
- role: control-plane
- role: worker
- role: worker
EOF

# MetalLB
kubectl apply -f https://raw.githubusercontent.com/metallb/metallb/v0.13.10/config/manifests/metallb-native.yaml

# Ingress
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/main/deploy/static/provider/kind/deploy.yaml
```

## ✅ Проверка
- [ ] Кластер создан
- [ ] MetalLB работает
- [ ] Load Balancer доступен
- [ ] Ingress работает
- [ ] Metrics server установлен

## 📖 Документация
- [kind](https://kind.sigs.k8s.io/) - Kubernetes in Docker
- [minikube](https://minikube.sigs.k8s.io/) - локальный K8s
- [k3s](https://k3s.io/) - легкий K8s
- [MetalLB](https://metallb.universe.tf/) - load balancer для локального K8s
- [AWS Free Tier](https://aws.amazon.com/free/) - бесплатный EKS (12 месяцев)