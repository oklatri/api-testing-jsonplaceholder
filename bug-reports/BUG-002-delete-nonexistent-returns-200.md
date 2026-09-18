# BUG-002: `DELETE /posts/999` возвращает `200 OK` вместо `404 Not Found`

**Severity:** Major
**Priority:** High
**Environment:** Postman v.11.68.0, https://jsonplaceholder.typicode.com
**Related test case:** TC-006

## Description
При попытке **удалить несуществующий пост** (`id=999`) API возвращает `200 OK` вместо `404 Not Found`. API не проверяет, существует ли ресурс перед удалением.

## Steps to reproduce
1. Открыть Postman
2. Создать запрос `DELETE https://jsonplaceholder.typicode.com/posts/999`
3. Нажать Send
4. Посмотреть статус-код

## Expected result
- Статус-код: `404 Not Found`
- Тело ответа: сообщение об ошибке

## Actual result
- Статус-код: `200 OK`
- Тело ответа: `{}`

## Attachments
- [Скриншот TC-006](../screenshots/screenshot-tc-006-delete-nonexistent-post.png)
