# API для социальной сети Yatube

Данный проект представляет собой API для социальной сети Yatube, в которой реализованы публикации, комментарии, группы и подписки.

## Запуск проекта

1. Создайте и активируйте виртуальное окружение:

   ```bash
   python3 -m venv .venv
   source .venv/bin/activate
   ```

2. Обновите пакетный менеджер pip и установите зависимости:

   ```bash
   python -m pip install --upgrade pip
   pip install -r requirements.txt
   ```

3. Выполните миграции базы данных:

   ```bash
   python manage.py migrate
   ```

4. Запустите сервер разработки:

   ```bash
   python manage.py runserver
   ```

## Примеры запросов

Полный перечень доступных запросов и их описание можно найти в документации по адресу `/redoc/`.

### Создание публикации

```http
POST /api/v1/posts/
{
    "text": "string"
}
```

### Получение списка постов с пагинацией

```http
GET /api/v1/posts/?limit=10&offset=10
```

### Получение всех комментариев к посту

```http
GET /api/v1/posts/{post_id}/comments/
```

### Удаление комментария

```http
DELETE /api/v1/posts/{post_id}/comments/{comment_id}/
```

