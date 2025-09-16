# Лабораторная работа 3

Настроить мониторинг для кластера MySQL, созданного ранее.

## Структура
- `playbook1.yml` — плейбук 1 работы: установка Docker, Wordpress, MySQL
- `playbook2.yml` — плейбук 2 работы: создание кластера, настройка репликации
- `playbook3.yml` - плейбук 3 работы: настройка мониторинга (Prometheus + Grafana)
- `roles/docker` — установка Docker и плагина Compose v2.
- `roles/wordpress` — деплой WordPress и MySQL через `docker-compose`.
- `roles/monitoring` - установка и настройка Prometheus + Grafana
- `templates/docker-compose.yml.j2` — шаблон `docker-compose.yml`.

## Используемые версии
- **WordPress**: `wordpress:6.6-php8.2-apache`
- **MySQL**: `mysql:8.0`
- **Prometheus**: "prom/prometheus:v2.54.1"
- **Grafana**: "grafana/grafana:11.2.0"
- **MySQL_exporter**: "prom/mysqld-exporter:v0.15.1"

## Запуск
- Обновить inventories/hosts.ini используя свой IP, проверить подключение
  ```bash
  ansible all -i inventories/hosts.ini -m ping
  
- Установка docker, wordpress, MySQL
  ```bash
  ansible-playbook -i inventories/hosts.ini playbook1.yml

- Создание кластера, настройка репликации Master -> Slave
  ```bash
  ansible-playbook -i inventories/hosts.ini playbook2.yml

- Настройка мониторинга (Prometheus + Grafana)
  ```bash
  ansible-playbook -i inventories/hosts.ini playbook3.yml

