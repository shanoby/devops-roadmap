# 🚀 DevOps Engineer Roadmap

> Полный путь становления DevOps инженера с нуля. Каждый раздел включает теорию, практику и тесты для самоконтроля.

## 📚 Содержание

1. [Основы Linux](#1-основы-linux)
2. [Сети и протоколы](#2-сети-и-протоколы)
3. [Скриптинг](#3-скриптинг)
4. [Git и VCS](#4-git-и-vcs)
5. [CI/CD](#5-cicd)
6. [Docker](#6-docker)
7. [Kubernetes](#7-kubernetes)
8. [Облачные провайдеры](#8-облачные-провайдеры)
9. [Infrastructure as Code](#9-infrastructure-as-code)
10. [Мониторинг](#10-мониторинг)
11. [Безопасность](#11-безопасность)
12. [Тестирование](#12-тестирование)

---

## 1. Основы Linux

### 🎯 Что изучить

**Система**
- Файловая иерархия (/, /etc, /var, /home)
- Процессы (ps, top, htop, kill)
- Память и CPU (free, vmstat, iostat)
- Диски (df, du, fdisk, mount)

**Пакеты**
- apt/yum/dnf (установка, обновление, удаление)
- Репозитории и источники

**Сеть**
- netstat/ss, ip, ping, traceroute
- SSH, scp, rsync

**Сервисы**
- systemd (systemctl, journalctl)
- cron (планировщик задач)

### 📖 Документация
- [Linux Journey](https://linuxjourney.com/)
- [Ubuntu Server Guide](https://ubuntu.com/server/docs)

### ✅ Тесты для самоконтроля

**Тест 1: Базовые команды**
1. Какой командой посмотреть использование диска?
2. Как найти файл содержащий "error"?
3. Как перезапустить сервис nginx?

**Тест 2: Практика**
- Установить и настроить Nginx
- Настроить виртуальный хост
- Написать скрипт логирования

---

## 2. Сети и протоколы

### 🎯 Что изучить

**Модели**
- OSI (7 уровней)
- TCP/IP стек

**Протоколы**
- HTTP/HTTPS (методы, статус коды)
- TCP vs UDP
- DNS, SSH, FTP

**Инструменты**
- tcpdump, wireshark
- nmap, netstat

### 📖 Документация
- [Computer Networking: A Top-Down Approach](https://wps.pearsoned.com/ecs_kurose_compnetw_6/)

### ✅ Тесты для самоконтроля

**Тест 1: Теория**
1. Чем TCP отличается от UDP?
2. Что такое CDN?
3. Как работает DNS?

**Тест 2: Практика**
- Настроить master-slave репликацию PostgreSQL
- Создать сеть с 3 серверами

---

## 3. Скриптинг

### 🎯 Что изучить

**Bash**
- Переменные, циклы, условия
- Функции
- Работа с файлами

**Python**
- requests, subprocess
- paramiko (SSH)
- Автоматизация

### 📖 Документация
- [Bash Manual](https://www.gnu.org/software/bash/manual/)
- [Python Docs](https://docs.python.org/3/)

### ✅ Тесты для самоконтроля

**Тест 1: Bash**
```bash
# Напишите скрипт который:
# 1. Проверяет дисковое пространство
# 2. Если > 80% - отправляет email
# 3. Логирует результат
```

**Тест 2: Python**
- Скрипт для парсинга логов
- Отправка метрик в Prometheus

---

## 4. Git и VCS

### 🎯 Что изучить

**База**
- commit, push, pull, fetch
- branch, merge, rebase

**Workflow**
- Git Flow
- GitHub Flow

**Инструменты**
- pre-commit hooks
- git-lfs

### 📖 Документация
- [Pro Git Book](https://git-scm.com/book/ru/v2)

### ✅ Тесты для самоконтроля

**Тест 1: Команды**
1. Как отменить последний коммит?
2. Как разрешить конфликт слияния?
3. Как создать patch?

**Тест 2: Практика**
- Смоделировать командную разработку
- Настроить pre-commit hooks

---

## 5. CI/CD

### 🎯 Что изучить

**Jenkins**
- Jenkinsfile (Declarative Pipeline)
- Плагины
- Агенты

**GitHub Actions**
- Workflows
- Actions marketplace
- Runners

**GitLab CI**
- .gitlab-ci.yml
- Variables, secrets

### 📖 Документация
- [Jenkins Handbook](https://www.jenkins.io/doc/book/)
- [GitHub Actions](https://docs.github.com/en/actions)

### ✅ Тесты для самоконтроля

**Тест 1: Pipeline**
```groovy
// Напишите Jenkinsfile:
// - Сборка
// - Тесты
// - Деплой на staging
// - Manual approval для production
```

**Тест 2: GitHub Actions**
- Workflow для тестирования PR
- Автодеплой на staging

---

## 6. Docker

### 🎯 Что изучить

**Основы**
- Образы и контейнеры
- Dockerfile
- docker-compose

**Продвинуто**
- Многоэтапная сборка
- Networks, volumes
- Security scanning

### 📖 Документация
- [Docker Docs](https://docs.docker.com/)

### ✅ Тесты для самоконтроля

**Тест 1: Dockerfile**
```dockerfile
# Соберите образ:
# - База: alpine
# - Приложение: nginx
# - Размер < 50MB
# - Healthcheck
```

**Тест 2: docker-compose**
- 3 сервиса: web, db, cache
- Настроить networks
- Volumes для данных

---

## 7. Kubernetes

### 🎯 Что изучить

**Объекты**
- Pod, Deployment, Service
- ConfigMap, Secret
- Ingress, ServiceAccount

**Продвинуто**
- RBAC
- Helm
- Operators

### 📖 Документация
- [Kubernetes Docs](https://kubernetes.io/docs/home/)

### ✅ Тесты для самоконтроля

**Тест 1: Deployment**
```yaml
# Создайте:
# - Deployment с 3 репликами
# - Service (ClusterIP)
# - Ingress с TLS
# - ConfigMap
```

**Тест 2: Helm**
- Создать chart
- Values для конфигурации
- Установить в k8s

---

## 8. Облачные провайдеры

### 🎯 Что изучить

**AWS**
- EC2, S3, VPC
- IAM, Security Groups
- EKS, ECS

**Azure**
- VM, Storage, VNet
- AKS

**GCP**
- Compute Engine, Cloud Storage
- GKE

### 📖 Документация
- [AWS Docs](https://docs.aws.amazon.com/)
- [Azure Docs](https://learn.microsoft.com/en-us/azure/)
- [GCP Docs](https://cloud.google.com/docs)

### ✅ Тесты для самоконтроля

**Тест 1: AWS**
- Развернуть EC2 с Security Group
- Настроить S3 bucket
- Создать VPC с публичным/приватным сабнетами

---

## 9. Infrastructure as Code

### 🎯 Что изучить

**Terraform**
- Providers, Resources
- State management
- Modules

**Ansible**
- Playbooks, Roles
- Inventory
- Handlers

### 📖 Документация
- [Terraform Registry](https://registry.terraform.io/)
- [Ansible Docs](https://docs.ansible.com/)

### ✅ Тесты для самоконтроля

**Тест 1: Terraform**
```hcl
# Создайте модуль VPC:
# - Переменные: cidr, azs
# - Outputs: vpc_id, subnet_ids
# - Remote state в S3
```

**Тест 2: Ansible**
- Playbook для настройки сервера
- Role для nginx
- Шаблоны конфигураций

---

## 10. Мониторинг

### 🎯 Что изучить

**Prometheus + Grafana**
- Метрики, экспортеры
- Alerting rules
- Dashboard

**ELK**
- Elasticsearch, Logstash, Kibana
- Filebeat

### 📖 Документация
- [Prometheus Docs](https://prometheus.io/docs/)
- [Grafana Tutorials](https://grafana.com/tutorials/)

### ✅ Тесты для самоконтроля

**Тест 1: Prometheus**
- Установить Prometheus
- Node Exporter на серверах
- Alerting rules для CPU/Memory

**Тест 2: Dashboard**
- Dashboard для HTTP запросов
- Алерты в Slack

---

## 11. Безопасность

### 🎯 Что изучить

**DevSecOps**
- SAST/DAST
- Container scanning
- Dependency scanning

**Secrets**
- HashiCorp Vault
- Kubernetes Secrets
- AWS Secrets Manager

### 📖 Документация
- [Vault Docs](https://www.vaultproject.io/docs)

### ✅ Тесты для самоконтроля

**Тест 1: Scanning**
- Trivy сканирование образов
- Интеграция в CI/CD
- Блок захвата уязвимых образов

**Тест 2: Vault**
- Установить Vault
- Хранить secrets
- Динамические credentials

---

## 12. Тестирование

### 🎯 Что изучить

**Terratest**
- Тесты Terraform
- Go basics

**Chaos Engineering**
- Chaos Monkey
- Litmus
- Gremlin

### 📖 Документация
- [Terratest](https://terratest.gruntwork.io/)

### ✅ Тесты для самоконтроля

**Тест 1: Terratest**
- Тест для VPC модуля
- Проверка созданных ресурсов

**Тест 2: Chaos**
- Сценарий pod deletion
- Сценарий network latency

---

## 🎯 Путь обучения

| Этап | Время | Цель |
|------|-------|------|
| 1 | 2-3 месяца | Linux + Сети |
| 2 | 1 месяц | Git + Scripting |
| 3 | 1-2 месяца | Docker |
| 4 | 1 месяц | CI/CD |
| 5 | 2-3 месяца | Kubernetes |
| 6 | 2-3 месяца | Cloud + IaC |
| 7 | 1-2 месяца | Monitoring + Security |
| 8 | 1 месяц | Портфолио + Поиск работы |

**Удачи в пути DevOps инженера! 🚀**