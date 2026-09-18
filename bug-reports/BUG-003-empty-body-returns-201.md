# BUG-003: `POST /posts` с пустым телом возвращает `201 Created` вместо `400 Bad Request`

**Severity:** Major
**Priority:** High
**Environment:** Postman v.11.68.0, https://jsonplaceholder.typicode.com
**Related test case:** TC-008

## Description
При создании поста с **пустым телом** API возвращает `201 Created` вместо ошибки `400 Bad Request`. API не валидирует обязательные поля (`title`, `body`, `userId`).

## Steps to reproduce
1. Открыть Postman
2. Создать запрос `POST https://jsonplaceholder.typicode.com/posts`
3. Открыть вкладку Body → raw → JSON
4. **Оставить тело пустым**
5. Нажать Send
6. Посмотреть статус-код и тело ответа

## Expected result
- Статус-код: `400 Bad Request`
- Тело ответа: сообщение об ошибке

## Actual result
- Статус-код: `201 Created`
- Тело ответа: `{"id": 101}`

## Attachments
- [Скриншот TC-008](../screenshots/screenshot-tc-008-post-empty-body.png)
