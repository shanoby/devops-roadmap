# Задание 1: Prometheus Setup

## 🎯 Цель
Настроить Prometheus + Grafana для мониторинга серверов.

## 📋 Задачи

### 1. Prometheus
- [ ] Установить Prometheus
- [ ] Настроить scrape targets
- [ ] Node Exporter на серверах
- [ ] Alerting rules

### 2. Grafana
- [ ] Установить Grafana
- [ ] Добавить Prometheus datasource
- [ ] Создать dashboard
- [ ] Настроить alertmanager

### 3. Метрики
- [ ] CPU usage
- [ ] Memory usage
- [ ] Disk usage
- [ ] Network traffic

## 🔧 Решение

```yaml
# prometheus.yml
global:
  scrape_interval: 15s

scrape_configs:
  - job_name: 'node'
    static_configs:
    - targets: ['node-exporter:9100']

  - job_name: 'app'
    static_configs:
    - targets: ['app-server:8080']

rule_files:
  - "alert.rules"
```

## ✅ Проверка
- [ ] Prometheus собирает метрики
- [ ] Node Exporter работает
- [ ] Grafana подключена
- [ ] Dashboard создан
- [ ] Алерты работают

## 📖 Документация
- [Prometheus Docs](https://prometheus.io/docs/)
- [Grafana Docs](https://grafana.com/docs/)
- [Node Exporter](https://github.com/prometheus/node_exporter)