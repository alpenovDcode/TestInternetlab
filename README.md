# User Management API

REST API для управления пользователями, реализованное с использованием Symfony.

## Методы API

### Регистрация пользователя
- **URL**: `/api/register`
- **Метод**: `POST`
- **Тело запроса**:
  ```json
  {
    "username": "string",
    "password": "string"
  }
  ```
- **Успешный ответ**: `201 Created`
  ```json
  {
    "message": "User registered successfully"
  }
  ```

### Обновление информации пользователя
- **URL**: `/api/user/{id}`
- **Метод**: `PUT`
- **Тело запроса**:
  ```json
  {
    "username": "string",
    "password": "string"
  }
  ```
- **Успешный ответ**: `200 OK`
  ```json
  {
    "message": "User updated successfully"
  }
  ```

### Удаление пользователя
- **URL**: `/api/user/{id}`
- **Метод**: `DELETE`
- **Успешный ответ**: `200 OK`
  ```json
  {
    "message": "User deleted successfully"
  }
  ```

### Получение информации о пользователе
- **URL**: `/api/user/{id}`
- **Метод**: `GET`
- **Успешный ответ**: `200 OK`
  ```json
  {
    "id": "integer",
    "username": "string"
  }
  ```

### Авторизация пользователя
- **URL**: `/api/login`
- **Метод**: `POST`
- **Тело запроса**:
  ```json
  {
    "username": "string",
    "password": "string"
  }
  ```
- **Успешный ответ**: `200 OK`
  ```json
  {
    "user": "string"
  }
  ```
- **Ошибка**: `401 Unauthorized`
  ```json
  {
    "message": "missing credentials"
  }
  ```

## Установка и запуск

1. Клонируйте репозиторий
2. Установите зависимости: `composer install`
3. Настройте базу данных в `.env.local`
4. Выполните миграции: `php bin/console doctrine:migrations:migrate`
5. Запустите сервер: `symfony server:start` 