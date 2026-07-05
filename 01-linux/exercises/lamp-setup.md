# Задание 1: Настройка LAMP stack

## 🎯 Цель
Установить и настроить LAMP stack (Linux, Apache, MySQL, PHP) на Ubuntu Server.

## 📋 Задачи

### 1. Установка компонентов
- [ ] Установить Apache (httpd)
- [ ] Установить MySQL/MariaDB
- [ ] Установить PHP
- [ ] Проверить версии установленных компонентов

### 2. Настройка Apache
- [ ] Создать виртуальный хост
- [ ] Настроить DocumentRoot
- [ ] Настроить логирование
- [ ] Проверить работу сайта

### 3. Настройка MySQL
- [ ] Создать базу данных
- [ ] Создать пользователя
- [ ] Настроить права доступа
- [ ] Проверить подключение

### 4. Настройка PHP
- [ ] Установить необходимые модули
- [ ] Настроить php.ini
- [ ] Проверить работу PHP

### 5. SSL сертификат
- [ ] Установить certbot
- [ ] Получить сертификат Let's Encrypt
- [ ] Настроить автоматическое обновление

## 🔧 Команды для выполнения

```bash
# Установка
sudo apt update
sudo apt install apache2 mysql-server php php-mysql

# Создание виртуального хоста
sudo nano /etc/apache2/sites-available/myapp.conf

# Включение сайта
sudo a2ensite myapp.conf
sudo systemctl reload apache2

# SSL
sudo apt install certbot python3-certbot-apache
sudo certbot --apache -d myapp.example.com
```

## ✅ Проверка
- [ ] Сайт открывается по HTTP
- [ ] Сайт открывается по HTTPS
- [ ] PHP работает (info.php)
- [ ] MySQL подключается
- [ ] SSL сертификат валиден

## 📖 Документация
- [Apache Docs](https://httpd.apache.org/docs/)
- [MySQL Docs](https://dev.mysql.com/doc/)
- [PHP Docs](https://www.php.net/docs.php)
- [Certbot Docs](https://certbot.eff.org/docs/)