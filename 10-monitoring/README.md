# 10. Мониторинг

## 🎯 Что изучить

### Prometheus + Grafana
- **Метрики** - counter, gauge, histogram, summary
- **Экспортеры** - Node, Blackbox, Process, MySQL, PostgreSQL
- **Alerting rules** - запись правил, severity, labels
- **Service discovery** - static, file, DNS, Kubernetes
- **Pushgateway** - push метрик
- **Alertmanager** - маршрутизация алертов, inhibition, silences

### ELK Stack
- **Elasticsearch** - индексы, шарды, mapping, templates
- **Logstash** - pipeline, filter, input, output
- **Kibana** - dashboards, visualizations, index patterns
- **Filebeat, Metricbeat** - сбор логов и метрик

### Loki
- **Лог-агрегация** - Promtail, LogQL
- **Grafana integration** - datasource, queries
- **Labels** - метки для фильтрации

## 📖 Документация
- [Prometheus Docs](https://prometheus.io/docs/) - официальная документация
- [Grafana Tutorials](https://grafana.com/tutorials/) - обучение
- [Elastic Docs](https://www.elastic.co/guide/index.html) - документация
- [Loki Docs](https://grafana.com/docs/loki/latest/) - документация
- [Prometheus Best Practices](https://prometheus.io/docs/practices/) - best practices

## ✅ Чекпоинты для самоконтроля

### Чекпоинт 1: Prometheus
- [ ] Понимаю типы метрик (counter, gauge, histogram)
- [ ] Могу установить Prometheus
- [ ] Понимаю экспортеры
- [ ] Могу писать alerting rules
- [ ] Понимаю service discovery

### Чекпоинт 2: Grafana
- [ ] Понимаю dashboard creation
- [ ] Могу создавать panels
- [ ] Понимаю templating
- [ ] Могу настроить alertmanager
- [ ] Понимаю data sources

### Чекпоинт 3: ELK
- [ ] Понимаю Elasticsearch индексы
- [ ] Могу настроить Logstash pipeline
- [ ] Понимаю Kibana visualizations
- [ ] Могу использовать Filebeat
- [ ] Понимаю LogQL (Loki)

## 📁 Практические задания
- [Задание 1: Prometheus Setup](exercises/prometheus-setup.md)
- [Задание 2: Log Aggregation](exercises/log-aggregation.md)