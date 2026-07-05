# 2. Сети и протоколы

## 🎯 Что изучить

### Модели
- **OSI** - 7 уровней модели, протоколы на каждом уровне
- **TCP/IP** - стек протоколов, IP, TCP, UDP, ICMP

### Протоколы
- **HTTP/HTTPS** - методы (GET, POST, PUT, DELETE), статус коды (2xx, 4xx, 5xx), заголовки, REST API
- **TCP vs UDP** - соединения, надежность, flow control, congestion control
- **DNS** - записи (A, AAAA, CNAME, MX, TXT, SRV), резолвинг, зоны
- **SSH** - ключи, tunneling, port forwarding, аутентификация
- **FTP/SFTP** - передача файлов, безопасность

### Инструменты
- **tcpdump, wireshark** - захват и анализ пакетов
- **nmap** - сканирование портов, OS detection, скрипты
- **netstat/ss** - просмотр соединений, слушающих портов
- **ipcalc** - вычисление сетей, broadcast, host range

### Сетевые устройства
- **Маршрутизаторы** - маршрутизация, NAT, ACL
- **Коммутаторы** - VLAN, STP, CAM table
- **Firewall** - правила, stateful, stateless

## 📖 Документация
- [Computer Networking: A Top-Down Approach](https://wps.pearsoned.com/ecs_kurose_compnetw_6/) - учебник
- [HTTP RFC](https://tools.ietf.org/html/rfc7230) - спецификация HTTP/1.1
- [TCP RFC](https://tools.ietf.org/html/rfc793) - спецификация TCP
- [DNS RFC](https://tools.ietf.org/html/rfc1035) - спецификация DNS
- [Wireshark Lab](https://www.wireshark.org/docs/) - документация Wireshark

## ✅ Чекпоинты для самоконтроля

### Чекпоинт 1: Модели и протоколы
- [ ] Понимаю 7 уровней OSI модели
- [ ] Понимаю разницу между TCP и UDP
- [ ] Могу объяснить как работает HTTP
- [ ] Понимаю статус коды HTTP (200, 404, 500, 503)
- [ ] Понимаю типы DNS записей

### Чекпоинт 2: Инструменты
- [ ] Могу захватить трафик tcpdump
- [ ] Могу проанализировать пакеты в Wireshark
- [ ] Могу выполнить сканирование nmap
- [ ] Могу проверить соединения ss -tuln
- [ ] Понимаю IP адреса, маски, CIDR

### Чекпоинт 3: Практика
- [ ] Могу настроить сеть с несколькими серверами
- [ ] Понимаю маршрутизацию
- [ ] Могу настроить firewall правила
- [ ] Понимаю VPN и туннелирование
- [ ] Могу диагностировать сеть

## 📁 Практические задания
- [Задание 1: Сетевая конфигурация](exercises/network-config.md)
- [Задание 2: Анализ трафика](exercises/traffic-analysis.md)