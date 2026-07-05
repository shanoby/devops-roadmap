# 1. Основы Linux

## 🎯 Что изучить

### Система
- **Файловая иерархия** - понимание стандартной структуры (/, /etc, /var, /home, /opt, /usr, /tmp)
- **Процессы** - управление процессами (ps, top, htop, kill, killall, pkill, nice, renice)
- **Память и CPU** - мониторинг ресурсов (free, vmstat, iostat, sar, mpstat)
- **Диски** - работа с файловой системой (df, du, fdisk, mount, umount, lsblk, blkid, mkfs)

### Пакеты
- **apt** (Debian/Ubuntu) - управление пакетами, репозитории
- **yum/dnf** (RHEL/CentOS) - управление пакетами, репозитории
- **Репозитории** - добавление, удаление, приоритеты

### Сеть
- **netstat/ss** - просмотр соединений
- **ip** - управление сетевыми интерфейсами
- **ping, traceroute** - диагностика сети
- **dig, nslookup** - DNS запросы
- **SSH, scp, rsync** - удаленный доступ и синхронизация
- **firewall** - ufw, firewalld, iptables

### Сервисы
- **systemd** - systemctl, journalctl, systemd-analyze, unit files
- **cron** - crontab, systemd timers, at
- **logrotate, rsyslog** - управление логами

## 📖 Документация
- [Linux Journey](https://linuxjourney.com/) - интерактивный курс
- [Ubuntu Server Guide](https://ubuntu.com/server/docs) - официальная документация
- [Red Hat Documentation](https://access.redhat.com/documentation/) - документация RHEL
- [Arch Wiki](https://wiki.archlinux.org/) - лучшая wiki для Linux
- [Linux man pages](https://man7.org/linux/man-pages/) - справочные страницы

## ✅ Чекпоинты для самоконтроля

### Чекпоинт 1: Базовые команды
- [ ] Могу навигировать по файловой системе (cd, ls, pwd, tree)
- [ ] Понимаю разницу между абсолютными и относительными путями
- [ ] Умею искать файлы (find, locate, grep)
- [ ] Могу просматривать файлы (cat, less, head, tail, grep)
- [ ] Понимаю права доступа (chmod, chown, umask)

### Чекпоинт 2: Процессы и ресурсы
- [ ] Могу просматривать процессы (ps aux, top, htop)
- [ ] Понимаю состояния процессов (running, sleeping, zombie)
- [ ] Могу управлять процессами (kill, killall, pkill)
- [ ] Могу мониторить ресурсы (free, df, iostat)
- [ ] Понимаю приоритеты процессов (nice, renice)

### Чекпоинт 3: Сеть
- [ ] Могу проверить сетевые соединения (ss -tuln, netstat)
- [ ] Понимаю IP адреса и маски
- [ ] Могу настроить сетевой интерфейс (ip addr, ip route)
- [ ] Могу выполнить сетевой диагноз (ping, traceroute, dig)
- [ ] Понимаю SSH ключи и аутентификацию

### Чекпоинт 4: Сервисы
- [ ] Могу управлять сервисами (systemctl start/stop/restart/status)
- [ ] Понимаю unit файлы systemd
- [ ] Могу просматривать логи (journalctl, /var/log)
- [ ] Могу настроить cron задачи
- [ ] Понимаю работу firewall

## 📁 Практические задания
- [Задание 1: Настройка LAMP stack](exercises/lamp-setup.md)
- [Задание 2: Скрипт мониторинга](exercises/disk-monitor.md)