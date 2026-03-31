# Todo API (Laravel)

Простое API для работы с задачами (Tasks) с поддержкой CRUD-операций и валидацией.

---

## Описание

API позволяет:

- **Создавать задачи**  
  `POST /api/tasks`  
  Параметры: `title` (обязательное), `description` (необязательное), `status` (`pending`, `in_progress`, `done`)

- **Просматривать список задач**  
  `GET /api/tasks`  
  Можно фильтровать по статусу: `GET /api/tasks?status=pending`

- **Просматривать одну задачу**  
  `GET /api/tasks/{id}`

- **Обновлять задачу**  
  `PUT /api/tasks/{id}`  
  Параметры: `title`, `description`, `status`

- **Удалять задачу**  
  `DELETE /api/tasks/{id}`

---

## Валидация

- `title` — обязательное поле, не может быть пустым
- `status` — обязательное, только `pending`, `in_progress`, `done`
- `description` — необязательное строковое поле

Ошибки валидации возвращаются с **HTTP 422** и JSON-ответом:

```json
{
  "message": "The title field is required.",
  "errors": {
    "title": [
      "The title field is required."
    ]
  }

```

## Примеры запросов
Все примеры приведены для Postman.
Скриншоты с тестами находятся в папке: `postman_screenshots`
