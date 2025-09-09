# Лабораторная работа 1

Деплой WordPress и MySQL в Docker-контейнерах с помощью Ansible.

## Структура
- `playbook.yml` — основной плейбук.
- `roles/docker` — установка Docker и плагина Compose v2.
- `roles/wordpress` — деплой WordPress и MySQL через `docker-compose`.
- `templates/docker-compose.yml.j2` — шаблон `docker-compose.yml`.

## Используемые версии
- **WordPress**: `wordpress:6.6-php8.2-apache`
- **MySQL**: `mysql:8.4`

## Запуск
- Обновить inventories/hosts.ini используя свой IP, проверить подключение
  ```bash
  ansible all -i inventory.ini -m ping
- Запустить плейбук
 ```
 ansible-playbook -i inventory.ini playbook.yml

