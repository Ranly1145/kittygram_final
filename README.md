#  Kittygram

Kittygram — социальная сеть для обмена фотографиями любимых питомцев. Это полностью рабочий проект, который состоит из бэкенд-приложения на Django и фронтенд-приложения на React.

## Как развернуть проект

Настроить запуск проекта Kittygram в контейнерах и CI/CD с помощью GitHub Actions

1. Клонировать репозиторий git@github.com:Ranly1145/kittygram_final.git
```
git clone git@github.com:Ranly1145/kittygram_final.git
```

2. Создать файл .env в корне проекта
```
touch .env
```

3. Ввести данные для переменных
```
DJANGO_SECRET_KEY=<ключ Django>
DEBUG=<True/False>
ALLOWED_HOSTS=<разрешенные хосты, через запятую>
DATABASES=postgres
POSTGRES_USER=<имя пользователя>
POSTGRES_PASSWORD=<пароль>
POSTGRES_DB=<база данных>
DB_NAME=<имя базы данных>
DB_HOST=db
DB_PORT=5432
```

4. Запустить docker compose
```
sudo docker compose -f docker-compose.production.yml up -d
```

5. Выполнить миграции, сбор статики
```
sudo docker compose -f docker-compose.production.yml exec backend python manage.py makemigrations
sudo docker compose -f docker-compose.production.yml exec backend python manage.py migrate
sudo docker compose -f docker-compose.production.yml exec backend python manage.py collectstatic --no-input
```

## Как проверить работу с помощью автотестов

В корне репозитория создайте файл tests.yml со следующим содержимым:
```yaml
repo_owner: ваш_логин_на_гитхабе
kittygram_domain: полная ссылка (https://доменное_имя) на ваш проект Kittygram
taski_domain: полная ссылка (https://доменное_имя) на ваш проект Taski
dockerhub_username: ваш_логин_на_докерхабе
```

Скопируйте содержимое файла `.github/workflows/main.yml` в файл `kittygram_workflow.yml` в корневой директории проекта.
Для локального запуска тестов создайте виртуальное окружение, установите в него зависимости из backend/requirements.txt и запустите в корневой директории проекта `pytest`.

## Автор
[Гарбуз Роман](https://github.com/Ranly1145)