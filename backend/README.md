### Как запустить бэкенд-часть проекта:

Клонировать репозиторий и перейти в него в командной строке:

```
git clone https://github.com/Ranly1145/kittygram_backend.git
```

```
cd kittygram_backend
```

Cоздать и активировать виртуальное окружение:

```
python3 -m venv env
```

* Если у вас Linux/macOS

    ```
    source env/bin/activate
    ```

* Если у вас windows

    ```
    source env/scripts/activate
    ```

```
python3 -m pip install --upgrade pip
```

Установить зависимости из файла requirements.txt:

```
pip install -r requirements.txt
```

Выполнить миграции:

```
python3 manage.py migrate
```

Запустить проект:

```
python3 manage.py runserver
```