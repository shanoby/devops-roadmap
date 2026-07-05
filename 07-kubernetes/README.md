# 7. Kubernetes

## 🎯 Что изучить

### Объекты
- Pod, Deployment, StatefulSet, DaemonSet
- Service (ClusterIP, NodePort, LoadBalancer)
- ConfigMap, Secret
- Ingress, ServiceAccount
- PersistentVolume, PersistentVolumeClaim

### Продвинуто
- RBAC (Role, RoleBinding, ClusterRole)
- Helm (Charts, Values, Templates)
- Operators
- Custom Resource Definitions

## 📖 Документация
- [Kubernetes Documentation](https://kubernetes.io/docs/home/)
- [Kubernetes Bootcamp](https://kubernetes.io/docs/tutorials/kubernetes-basics/)

## ✅ Тесты для самоконтроля

### Тест 1: Deployment
```yaml
# Создайте:
# - Deployment с 3 репликами
# - Service (ClusterIP)
# - Ingress с TLS
# - ConfigMap
# - Health checks
```

### Тест 2: Helm
- Создать chart
- Values для конфигурации
- Установить в k8s

## 📁 Практические задания
- [Задание 1: Application Deployment](exercises/app-deployment.md)
- [Задание 2: Helm Chart](exercises/helm-chart.md)