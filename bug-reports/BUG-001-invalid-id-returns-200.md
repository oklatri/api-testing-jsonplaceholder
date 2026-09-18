# BUG-001: `GET /posts/abc` возвращает `200 OK` вместо `400 Bad Request`

**Severity:** Major
**Priority:** High
**Environment:** Postman v.11.68.0, https://jsonplaceholder.typicode.com
**Related test case:** TC-005

## Description
При запросе поста с **нечисловым ID** (`abc`) API возвращает `200 OK` и пустой объект вместо ошибки `400 Bad Request`. ID должен быть **числом**, но API не валидирует тип данных.

**Note:** Баг воспроизводился 18.09.2026. API нестабилен и может возвращать разные ответы.

## Steps to reproduce
1. Открыть Postman
2. Создать запрос `GET https://jsonplaceholder.typicode.com/posts/abc`
3. Нажать Send
4. Посмотреть статус-код и тело ответа

## Expected result
- Статус-код: `400 Bad Request`
- Тело ответа: сообщение об ошибке

## Actual result
- Статус-код: `200 OK`
- Тело ответа: `{}`

## Attachments
- [Скриншот TC-005](../screenshots/screenshot-tc-005-get-post-invalid-id.png)
