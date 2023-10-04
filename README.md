# Описание 
---
Проект kittygram является сервисом для обмена людей фотографиями и достижениями их котов. Данный проект можно загрузить на сервер использую пароль от него и SSH_KEY
# Стек технологий :
---
- Python
- Django
- Linux (Ubuntu)
- Docker
# Как запустить проект:
---
1. Клонировать репозиторий
```
    git clone git@github.com:Etl0n/kittygram_final.git
```
2. Создать файл .env в корне проекте и заполнить его нужными данными для создания БД PostgreSQL
-    POSTGRES_DB=
-    POSTGRES_USER=
-    POSTGRES_PASSWORD=
-    DB_NAME=
-    DB_HOST=
-    DB_PORT=5432

3. После зайти в настройки этого проекта на GitHub, после Settings/Secrets and Varieble и добавить необходимые переменные
- DOCKER_USERNAME (имя на DockerHub)
- DOCKER_PASSWORD (пароль на DockerHub)
- HOST (ip адрес вашего сервера)
- USER (имя пользователя на сервере)
- SSH_KEY (SSH ключ от сервера)
- TELEGRAM_TO (ваш id в телеграме, чтобы отправить уведомления о успешном деплое проекта на сервер)
- TELEGRAM_TOKEN (TOKEN любого вашего бота в Telegram)
4. После нужно настроить nginx на вашем сервере чтобы запросы приходящие на ваш домен перенаправлялись на нужный порт
```
location / {
    proxy pass http://127.0.0.1:9000;
}
```
5. Затем переходим на сервер в новую появившуюся папку на сервере kittygram и выполняем команду в терминали
```
    docker compose -f docker-compose.production.yml up --build
```
# Автор
https://github.com/Etl0n (Ученик Яндекс Практикум)
