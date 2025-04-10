## Проект «API для Yatube»

**Yatube** — это социальная сеть, которая получила новое расширение возможностей благодаря проекту «API для Yatube». Этот интерфейс предоставляет пользователям функционал для управления публикациями и подписками через API.

### Основные возможности

- Создание, просмотр, редактирование и удаление публикаций.
- Работа с комментариями: добавление, изменение, удаление и получение списка.
- Просмотр списка сообществ и информации о каждом из них.
- Управление подписками: возможность подписаться на интересующего автора и отслеживать обновления.
- Авторизация через JWT: получение, проверка и обновление токенов.

## Стек технологий

* Python 3.9
* Django 3.2
* Django REST framework
* JWT + Djoser

## Установка

**Клонировать репозиторий и перейти в него в командной строке.**

```
git clone https://github.com/MaksimBritsin/api_final_yatube.git
```

**Cоздать и активировать виртуальное окружение:**

```
python -m venv venv
source venv/Scripts/activate
```

**Установить зависимости из файла requirements.txt:**

```
python -m pip install --upgrade pip
pip install -r requirements.txt
```

**Выполнить миграции:**

```
python manage.py makemigrations
python manage.py migrate
```

**Создать суперюзера:**

```
python manage.py createsuperuser
```

**Запустить проект:**

```
python manage.py runserver
```

### Примеры запросов к API:

POST-запрос на эндпоинт api/v1/posts/:

```bash
{
    "text": "string",
    "image": "string",
    "group": 1
}
```

Ответ:

```
{
    "id": 1,
    "author": "username",
    "text": "string",
    "pub_date": "2022-03-13T14:15:22Z",
    "image": "string",
    "group": 1
}
```

GET-запрос на эндпоинт api/v1/posts/{post_id}/comments/ вернет список комментариев к посту:

```
[
    {
        "id": 1,
        "author": "username",
        "text": "string",
        "created": "2022-03-13T14:15:22Z",
        "post": 1
    },
    {
        "id": 2,
        "author": "username",
        "text": "string",
        "created": "2022-03-13T14:15:22Z",
        "post": 1
    }
]
```
Автор: Брицин Максим 