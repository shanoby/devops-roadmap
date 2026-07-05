# 7. Kubernetes

## 🎯 Что изучить

### Объекты
- **Pod** - базовая единица, контейнеры, init контейнеры
- **Deployment** - репликация, rolling update, rollback
- **StatefulSet** - stateful приложения, stable network ID
- **DaemonSet** - агенты на всех/некоторых узлах
- **Service** - ClusterIP, NodePort, LoadBalancer, ExternalName
- **ConfigMap, Secret** - конфигурация, секреты
- **Ingress** - маршрутизация HTTP, TLS, annotations
- **PersistentVolume, PersistentVolumeClaim** - хранилище, storage classes

### Продвинуто
- **RBAC** - Role, RoleBinding, ClusterRole, ClusterRoleBinding
- **Helm** - Charts, Values, Templates, Release, Rollback
- **Operators** - CRD, controller pattern, Operator SDK
- **Network Policies** - изоляция трафика
- **Resource Quotas** - ограничение ресурсов
- **Pod Disruption Budget** - доступность при обновлениях

## 📖 Документация
- [Kubernetes Documentation](https://kubernetes.io/docs/home/) - официальная документация
- [Kubernetes Bootcamp](https://kubernetes.io/docs/tutorials/kubernetes-basics/) - интерактивный курс
- [Helm Documentation](https://helm.sh/docs/) - оркестрация
- [Kubernetes Patterns](https://github.com/gravitational/workshop/blob/master/k8sprod.md) - паттерны

## ✅ Чекпоинты для самоконтроля

### Чекпоинт 1: Основные объекты
- [ ] Понимаю Pod и его lifecycle
- [ ] Могу создать Deployment
- [ ] Понимаю Service типы
- [ ] Могу использовать ConfigMap
- [ ] Понимаю Secret

### Чекпоинт 2: Хранилище и Ingress
- [ ] Понимаю PV и PVC
- [ ] Могу настроить Ingress с TLS
- [ ] Понимаю storage classes
- [ ] Могу использовать volumeMounts
- [ ] Понимаю emptyDir, hostPath

### Чекпоинт 3: Продвинуто
- [ ] Понимаю RBAC
- [ ] Могу создать Helm chart
- [ ] Понимаю Operators
- [ ] Могу писать templates
- [ ] Понимаю Network Policies

## 📁 Практические задания
- [Задание 1: Application Deployment](exercises/app-deployment.md)
- [Задание 2: Helm Chart](exercises/helm-chart.md)