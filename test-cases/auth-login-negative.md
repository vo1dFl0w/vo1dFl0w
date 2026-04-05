# [Neg] Вход в систему пользователя с невалидным email

## Метаданные

**ID:** 15
**Автоматизирован:** Нет
**Приоритет:** Средний
**Статус:** Готов
**Оценка:** 0h 10m 0s

## Тестовые данные
- email: `userexample.org`; password: `password`;
- email: `user@exampleorg`; password: `password`;
- email: `<empty>`; password: `password`;

## Предусловия
- Пользователь с email `user@example.org` и паролем `password` зарегистрирован в системе и существует запись в базе данных

## Шаги и ожидаемые результаты
1. **Шаг:** Отправить запрос POST /api/v1/auth/login с телом: {“email“: “`%email`”, “password“: “`%password`”}
   **Ожидаемый результат:** Сервер отправляет ответ со статусом `400 Bad Request` и сообщение об ошибке: “Wrong email or password“