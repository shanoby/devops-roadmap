# Задание 2: Скрипт мониторинга диска

## 🎯 Цель
Написать bash скрипт для мониторинга дискового пространства с алертами.

## 📋 Задачи

### 1. Скрипт мониторинга
- [ ] Проверить использование диска
- [ ] Сравнить с пороговым значением (80%)
- [ ] Отправить email при превышении
- [ ] Записать в лог

### 2. Cron задача
- [ ] Настроить периодический запуск
- [ ] Проверить работу cron
- [ ] Настроить логирование

### 3. Улучшения
- [ ] Добавить проверку нескольких дисков
- [ ] Добавить уведомление в Slack
- [ ] Добавить метрики для Prometheus

## 🔧 Решение

```bash
#!/bin/bash

# Конфигурация
THRESHOLD=80
EMAIL="admin@example.com"
LOG="/var/log/disk_monitor.log"
SLACK_WEBHOOK=""

# Проверка диска
check_disk() {
    local usage=$(df / | tail -1 | awk '{print $5}' | sed 's/%//')
    
    if [ $usage -gt $THRESHOLD ]; then
        echo "Warning: Disk usage is ${usage}%" >> $LOG
        echo "Warning: Disk usage is ${usage}%" | mail -s "Disk Alert" $EMAIL
        
        # Slack уведомление
        if [ -n "$SLACK_WEBHOOK" ]; then
            curl -X POST -H 'Content-type: application/json' \
                --data "{\"text\":\"Disk usage alert: ${usage}%\"}" \
                $SLACK_WEBHOOK
        fi
    else
        echo "$(date): Disk usage ${usage}% - OK" >> $LOG
    fi
}

# Запуск
check_disk
```

## ✅ Проверка
- [ ] Скрипт исполняется без ошибок
- [ ] Лог записывается корректно
- [ ] Email отправляется при превышении
- [ ] Cron задача работает
- [ ] Метрики доступны

## 📖 Документация
- [Bash Scripting](https://www.gnu.org/software/bash/manual/)
- [Cron HowTo](https://crontab.org/)
- [Mailutils](https://mailutils.org/)
- [Prometheus Node Exporter](https://github.com/prometheus/node_exporter)