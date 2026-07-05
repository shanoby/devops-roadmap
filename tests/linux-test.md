# Тесты: Основы Linux

## Теория

### Вопросы

1. **Что такое init система и какие бывают?**
   - a) SysV init, systemd, OpenRC
   - b) Windows, Linux, macOS
   - c) Docker, Kubernetes, Jenkins

2. **Какой уровень логирования в journalctl показывает ошибки?**
   - a) info
   - b) error
   - c) critical

3. **Что такое inode?**
   - a) Файл
   - b) Метаданные файла
   - c) Папка

### Ответы
1. a) SysV init, systemd, OpenRC
2. b) error
3. b) Метаданные файла

## Практика

### Задание 1: Скрипт мониторинга диска

Напишите bash скрипт, который:
- Проверяет использование диска
- При превышении 80% отправляет email
- Логирует результат в /var/log/disk_monitor.log

**Решение:**
```bash
#!/bin/bash

THRESHOLD=80
EMAIL="admin@example.com"
LOG="/var/log/disk_monitor.log"

USAGE=$(df / | tail -1 | awk '{print $5}' | sed 's/%//')

if [ $USAGE -gt $THRESHOLD ]; then
    echo "Warning: Disk usage is ${USAGE}%" | mail -s "Disk Alert" $EMAIL
    echo "$(date): Disk usage ${USAGE}% - ALERT sent" >> $LOG
else
    echo "$(date): Disk usage ${USAGE}% - OK" >> $LOG
fi
```

### Задание 2: Nginx setup

1. Установите Nginx
2. Создайте виртуальный хост
3. Настройте SSL (самоподписанный сертификат)

**Решение:**
```bash
# Установка
sudo apt update
sudo apt install nginx

# Виртуальный хост
sudo nano /etc/nginx/sites-available/myapp
```

```nginx
server {
    listen 80;
    server_name myapp.local;
    
    location / {
        root /var/www/myapp;
        index index.html;
    }
}
```

```bash
# SSL
sudo openssl req -x509 -nodes -days 365 -newkey rsa:2048 \
    -keyout /etc/ssl/private/nginx-selfsigned.key \
    -out /etc/ssl/certs/nginx-selfsigned.crt
```

## Самоконтроль

- [ ] Могу объяснить разницу между systemd и SysV init
- [ ] Понимаю файловую иерархию Linux
- [ ] Умею писать базовые bash скрипты
- [ ] Могу настроить веб-сервер