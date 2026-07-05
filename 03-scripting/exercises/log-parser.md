# Задание 1: Log Parser

## 🎯 Цель
Написать скрипт для парсинга логов и отправки метрик.

## 📋 Задачи

### 1. Парсинг логов
- [ ] Читать лог файл
- [ ] Выделять IP адреса
- [ ] Выделять статус коды
- [ ] Выделять ошибки

### 2. Метрики
- [ ] Подсчитывать запросы по статус кодам
- [ ] Наиболее частые IP
- [ ] Ошибки (4xx, 5xx)

### 3. Экспорт
- [ ] Отправка в Prometheus Pushgateway
- [ ] Формат метрик
- [ ] Labels

## 🔧 Решение

```python
import re
from collections import Counter
import requests

def parse_logs(log_file):
    with open(log_file, 'r') as f:
        logs = f.readlines()
    
    status_codes = []
    ips = []
    
    for line in logs:
        # Извлечь IP
        ip_match = re.search(r'^(\d+\.\d+\.\d+\.\d+)', line)
        if ip_match:
            ips.append(ip_match.group(1))
        
        # Извлечь статус код
        status_match = re.search(r'" (\d{3})', line)
        if status_match:
            status_codes.append(status_match.group(1))
    
    return Counter(ips), Counter(status_codes)

def send_metrics(ip_counter, status_counter):
    metrics = ""
    for ip, count in ip_counter.most_common(10):
        metrics += f'log_requests_ip{{ip="{ip}"}} {count}\n'
    
    for status, count in status_counter.items():
        metrics += f'log_requests_status{{code="{status}"}} {count}\n'
    
    requests.post('http://pushgateway:9091/metrics/job/log_parser', 
                  data=metrics)
```

## ✅ Проверка
- [ ] Логи парсятся корректно
- [ ] IP адреса извлекаются
- [ ] Статус коды подсчитываются
- [ ] Метрики отправляются
- [ ] Pushgateway получает данные

## 📖 Документация
- [Python re module](https://docs.python.org/3/library/re.html)
- [Prometheus Pushgateway](https://github.com/prometheus/pushgateway)
- [Log Parsing](https://www.elastic.co/guide/en/logstash/current/plugins-filters-grok.html)