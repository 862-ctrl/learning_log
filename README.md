
# Learning Log

Веб-приложение для ведения журнала изучения различных тем.

## Используемые технологии

- Python 3.12
- Django 5.2
- SQLite
- Bootstrap 4
- Gunicorn
- WhiteNoise
- Docker

## Запуск проекта через Docker

1. Установить Docker и Docker Compose.
2. Склонировать репозиторий:

```bash
git clone ССЫЛКА_НА_РЕПОЗИТОРИЙ
cd learning_log
```

3. Создать файл `.env` на основе необходимых переменных.

4. Запустить приложение:

```bash
docker compose up -d --build
```

5. Проверить состояние контейнера:

```bash
docker compose ps
```

6. Посмотреть журналы приложения:

```bash
docker compose logs -f web
```

## Переменные окружения

| Переменная | Назначение |
|---|---|
| DJANGO_SECRET_KEY | Секретный ключ Django |
| DJANGO_DEBUG | Режим отладки |
| DJANGO_ALLOWED_HOSTS | Разрешённые адреса |
| DJANGO_CSRF_TRUSTED_ORIGINS | Доверенные источники CSRF |
| DJANGO_USE_HTTPS | Использование HTTPS |
| SQLITE_PATH | Путь к базе данных |
| APP_BIND_IP | IP-адрес привязки |
| APP_PORT | Внешний порт приложения |

## Остановка приложения

```bash
docker compose down
```

Данные SQLite хранятся в Docker volume `learning_log_data`.

## Структура проекта

- `learning_log/` — настройки Django.
- `learning_logs/` — приложение с темами и записями.
- `users/` — приложение пользователей.
- `Dockerfile` — инструкция сборки Docker-образа.
- `compose.yaml` — конфигурация Docker Compose.
