# Лабораторная работа 2

Развёртывания WordPress и кластера MySQL с синхронизацией данных в изолированных Docker-контейнерах.

## Структура
- `playbook1.yml` — плейбук 1 работы: установка Docker, Wordpress, MySQL
- `playbook2.yml` — плейбук 2 работы: создание кластера, настройка репликации
- `roles/docker` — установка Docker и плагина Compose v2.
- `roles/wordpress` — деплой WordPress и MySQL через `docker-compose`.
- `templates/docker-compose.yml.j2` — шаблон `docker-compose.yml`.

## Используемые версии
- **WordPress**: `wordpress:6.6-php8.2-apache`
- **MySQL**: `mysql:8.0`

## Запуск
- Обновить inventories/hosts.ini используя свой IP, проверить подключение
  ```bash
  ansible all -i inventories/hosts.ini -m ping
  
- Установка docker, wordpress, MySQL
  ```bash
  ansible-playbook -i inventories/hosts.ini playbook1.yml

- Создание кластера, настройка репликации Master -> Slave
  ```bash
  ansible-playbook -i inventories.hosts.ini playbook2.yml

