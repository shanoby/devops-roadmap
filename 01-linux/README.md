# 1. Основы Linux

## 🎯 Что изучить

### Система
- Файловая иерархия (/, /etc, /var, /home, /opt, /usr, /tmp)
- Процессы (ps, top, htop, kill, killall, pkill)
- Память и CPU (free, vmstat, iostat, sar)
- Диски (df, du, fdisk, mount, umount, lsblk)

### Пакеты
- apt (Debian/Ubuntu)
- yum/dnf (RHEL/CentOS)
- Репозитории и источники

### Сеть
- netstat/ss, ip, ping, traceroute, dig, nslookup
- SSH, scp, rsync, scp
- firewall (ufw, firewalld, iptables)

### Сервисы
- systemd (systemctl, journalctl, systemd-analyze)
- cron (crontab, systemd timers)
- logrotate, rsyslog

## 📖 Документация
- [Linux Journey](https://linuxjourney.com/)
- [Ubuntu Server Guide](https://ubuntu.com/server/docs)
- [Red Hat Documentation](https://access.redhat.com/documentation/)

## ✅ Тесты для самоконтроля

### Тест 1: Базовые команды
1. Какой командой посмотреть использование диска?
2. Как найти файл содержащий "error"?
3. Как перезапустить сервис nginx?

### Тест 2: Практика
- Установить и настроить Nginx
- Настроить виртуальный хост
- Написать скрипт мониторинга

## 📁 Практические задания
- [Задание 1: Настройка LAMP stack](exercises/lamp-setup.md)
- [Задание 2: Скрипт мониторинга](exercises/disk-monitor.md)