# Сервис анализа настроения отзывов.

## Установка и запуск

```bash
pip install flask
python app.py
```

## API

### POST /reviews
Создает отзыв и определяет настроение.

```bash
curl -X POST http://localhost:5000/reviews \
  -H "Content-Type: application/json" \
  -d '{"text": "Отличный сервис!"}'
```

Ответ:
```json
{
  "id": 1,
  "text": "Отличный сервис!",
  "sentiment": "positive",
  "created_at": "2024-01-15T10:30:00"
}
```

### GET /reviews?sentiment=negative
Получает отзывы с определенным настроением.

```bash
curl "http://localhost:5000/reviews?sentiment=negative"
```

Ответ:
```json
{
  "reviews": [
    {
      "id": 2,
      "text": "Плохой сервис",
      "sentiment": "negative",
      "created_at": "2024-01-15T10:35:00"
    }
  ]
}
```
