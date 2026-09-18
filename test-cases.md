# API Test Cases — JSONPlaceholder

## TC-001: Получить список всех постов

**Метод:** GET
**URL:** `https://jsonplaceholder.typicode.com/posts`
**Preconditions:** Postman открыт

**Steps:**
1. Выбрать метод GET
2. Ввести URL
3. Нажать Send
4. Проверить статус-код
5. Проверить тело ответа

**Expected result:**
- Статус-код: `200 OK`
- Тело ответа: массив JSON из 100 постов
- Каждый пост содержит поля: `userId`, `id`, `title`, `body`

**Actual result:**
- Статус-код: `200 OK`
- Тело: массив из 100 постов

**Status:** ✅ Passed
**Скриншот:** [screenshot-tc-001-get-all-posts.png](screenshots/screenshot-tc-001-get-all-posts.png)

---

## TC-002: Получить пост по ID

**Метод:** GET
**URL:** `https://jsonplaceholder.typicode.com/posts/1`
**Preconditions:** Postman открыт

**Steps:**
1. Выбрать метод GET
2. Ввести URL
3. Нажать Send
4. Проверить статус-код
5. Проверить тело ответа

**Expected result:**
- Статус-код: `200 OK`
- Тело ответа: JSON с полями `userId=1`, `id=1`, `title`, `body`

**Actual result:**
- Статус-код: `200 OK`
- Тело: JSON с полями `userId=1`, `id=1`, `title`, `body`

**Status:** ✅ Passed
**Скриншот:** [screenshot-tc-002-get-post-by-id.png](screenshots/screenshot-tc-002-get-post-by-id.png)

---

## TC-003: Удалить пост

**Метод:** DELETE
**URL:** `https://jsonplaceholder.typicode.com/posts/1`
**Preconditions:** Postman открыт

**Steps:**
1. Выбрать метод DELETE
2. Ввести URL
3. Нажать Send
4. Проверить статус-код
5. Проверить тело ответа

**Expected result:**
- Статус-код: `200 OK`
- Тело ответа: `{}`

**Actual result:**
- Статус-код: `200 OK`
- Тело ответа: `{}`

**Status:** ✅ Passed
**Скриншот:** [screenshot-tc-003-delete-post.png](screenshots/screenshot-tc-003-delete-post.png)
