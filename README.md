# API Testing — JSONPlaceholder

Портфолио тест-кейсов для JSONPlaceholder API.

## Инструменты
- Postman
- REST, JSON

## Что внутри
- `test-cases.md` — 8 тест-кейсов (позитивные и негативные)
- `collections/` — коллекция Postman
- `bug-reports/` — 3 баг-репорта
- `screenshots/` — 8 скриншотов ответов

## Покрытие
- `GET /posts` — получить все посты
- `GET /posts/1` — получить один пост
- `DELETE /posts/1` — удалить пост
- `GET /posts/999` — несуществующий пост (404)
- `GET /posts/abc` — нечисловой ID (баг)
- `DELETE /posts/999` — удаление несуществующего (баг)
- `POST /posts` — создание поста
- `POST /posts` (пустой body) — валидация (баг)

## Автотесты в Postman

В коллекции Postman **добавлены автотесты** (вкладка `Scripts` → `After response`) для 5 запросов:

| Запрос | Кол-во тестов | Что проверяет |
|---|---|---|
| `GET all posts` | 4 | Статус 200, массив, 100 постов, время < 1000ms |
| `GET post by ID` | 3 | Статус 200, id = 1, наличие title |
| `POST create post` | 3 | Статус 201, новый id, title совпадает |
| `DELETE post` | 2 | Статус 200, время < 1000ms |
| `GET nonexistent post` | 1 | Статус 404 |

**Скриншоты:** `screenshots/postman-*-tests.png`

## Результаты
- 8 тест-кейсов
- 5 Passed
- 3 Failed

## Найденные баги
- [BUG-001: `GET /posts/abc` возвращает `200 OK` вместо `400`](bug-reports/BUG-001-invalid-id-returns-200.md)
- [BUG-002: `DELETE /posts/999` возвращает `200 OK` вместо `404`](bug-reports/BUG-002-delete-nonexistent-returns-200.md)
- [BUG-003: `POST /posts` с пустым телом возвращает `201` вместо `400`](bug-reports/BUG-003-empty-body-returns-201.md)

## Скриншоты

- [TC-001: GET all posts](screenshots/screenshot-tc-001-get-all-posts.png)
- [TC-002: GET post by ID](screenshots/screenshot-tc-002-get-post-by-id.png)
- [TC-003: DELETE post](screenshots/screenshot-tc-003-delete-post.png)
- [TC-004: GET nonexistent post](screenshots/screenshot-tc-004-get-nonexistent-post.png)
- [TC-005: GET post with invalid ID](screenshots/screenshot-tc-005-get-post-invalid-id.png)
- [TC-006: DELETE nonexistent post](screenshots/screenshot-tc-006-delete-nonexistent-post.png)
- [TC-007: POST create post](screenshots/screenshot-tc-007-post-create-post.png)
- [TC-008: POST empty body](screenshots/screenshot-tc-008-post-empty-body.png)
