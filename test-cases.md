# API Test Cases — JSONPlaceholder

## TC-001: Получить список всех постов

**Метод:** `GET`
**URL:** `https://jsonplaceholder.typicode.com/posts`
**Preconditions:** Postman открыт

**Steps:**
1. Выбрать метод `GET`
2. Ввести URL
3. Нажать `Send`
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

---

## TC-002: Получить пост по ID

**Метод:** `GET`
**URL:** `https://jsonplaceholder.typicode.com/posts/1`
**Preconditions:** Postman открыт

**Steps:**
1. Выбрать метод `GET`
2. Ввести URL
3. Нажать `Send`
4. Проверить статус-код
5. Проверить тело ответа

**Expected result:**
- Статус-код: `200 OK`
- Тело ответа: JSON с полями `userId=1`, `id=1`, `title`, `body`

**Actual result:**
- Статус-код: `200 OK`
- Тело: JSON с полями `userId=1`, `id=1`, `title`, `body`

**Status:** ✅ Passed

---

## TC-003: Удалить пост

**Метод:** `DELETE`
**URL:** `https://jsonplaceholder.typicode.com/posts/1`
**Preconditions:** Postman открыт

**Steps:**
1. Выбрать метод `DELETE`
2. Ввести URL
3. Нажать `Send`
4. Проверить статус-код
5. Проверить тело ответа

**Expected result:**
- Статус-код: `200 OK`
- Тело ответа: `{}`

**Actual result:**
- Статус-код: `200 OK`
- Тело ответа: `{}`

**Status:** ✅ Passed

---

## TC-004: Получить несуществующий пост

**Метод:** `GET`
**URL:** `https://jsonplaceholder.typicode.com/posts/999`
**Preconditions:** Postman открыт

**Steps:**
1. Выбрать метод `GET`
2. Ввести URL
3. Нажать `Send`
4. Проверить статус-код
5. Проверить тело ответа

**Expected result:**
- Статус-код: `404 Not Found`
- Тело ответа: `{}`

**Actual result:**
- Статус-код: `404 Not Found`
- Тело ответа: `{}`

**Status:** ✅ Passed

---

## TC-005: Получить пост с нечисловым ID

**Метод:** `GET`
**URL:** `https://jsonplaceholder.typicode.com/posts/abc`
**Preconditions:** Postman открыт

**Steps:**
1. Выбрать метод `GET`
2. Ввести URL
3. Нажать `Send`
4. Проверить статус-код
5. Проверить тело ответа

**Expected result:**
- Статус-код: `400 Bad Request` (ID должен быть числом)
- Тело ответа: сообщение об ошибке

**Actual result:**
- Статус-код: `200 OK`
- Тело ответа: `{}`

**Status:** ❌ Failed

---

## TC-006: Удалить несуществующий пост

**Метод:** `DELETE`
**URL:** `https://jsonplaceholder.typicode.com/posts/999`
**Preconditions:** Postman открыт

**Steps:**
1. Выбрать метод `DELETE`
2. Ввести URL
3. Нажать `Send`
4. Проверить статус-код
5. Проверить тело ответа

**Expected result:**
- Статус-код: `404 Not Found` (поста не существует)
- Тело ответа: сообщение об ошибке

**Actual result:**
- Статус-код: `200 OK`
- Тело ответа: `{}`

**Status:** ❌ Failed

---

## TC-007: Создать новый пост

**Метод:** `POST`
**URL:** `https://jsonplaceholder.typicode.com/posts`
**Preconditions:** Postman открыт, Body → raw → JSON

**Test data:**
```json
{
  "title": "My first post",
  "body": "This is a test post",
  "userId": 1
}
```

**Steps:**
1. Выбрать метод `POST`
2. Ввести URL
3. Открыть вкладку Body → raw → JSON
4. Вставить тело запроса
5. Нажать `Send`
6. Проверить статус-код
7. Проверить тело ответа

**Expected result:**
- Статус-код: `201 Created`
- Тело ответа: JSON с полями `title`, `body`, `userId`, `id`

**Actual result:**
- Статус-код: `201 Created`
- Тело ответа: JSON с `id: 101`

**Status:** ✅ Passed

---

## TC-008: Создать пост с пустым телом (негативный)

**Метод:** `POST`
**URL:** `https://jsonplaceholder.typicode.com/posts`
**Preconditions:** Postman открыт, Body → raw → JSON

**Test data:**
```
(пустое тело)
```

**Steps:**
1. Выбрать метод `POST`
2. Ввести URL
3. Открыть вкладку Body → raw → JSON
4. Оставить тело пустым
5. Нажать `Send`
6. Проверить статус-код
7. Проверить тело ответа

**Expected result:**
- Статус-код: `400 Bad Request` (обязательные поля title, body, userId отсутствуют)
- Тело ответа: сообщение об ошибке

**Actual result:**
- Статус-код: `201 Created`
- Тело ответа: `{"id": 101}`

**Status:** ❌ Failed
