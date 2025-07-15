# Backend (FastAPI) для groceries_delivery_app

## Структура backend/

- backend/
-     - app/
-         - __init__.py
-             - main.py            # Точка входа FastAPI
-                 - models/            # SQLAlchemy / Pydantic модели
-                     - api/               # Маршруты и CRUD API
-                         - db/                # Логика подключения к PostgreSQL
-                                 - __init__.py
-                                         - session.py
-                                             - core/              # общие утилиты (валидация, настройки, jwt)
-                                             - requirements.txt       # pip-зависимости
-                                             - Dockerfile             # Docker для FastAPI
-                                             - docker-compose.yaml    # Compose FastAPI + PostgreSQL
-                                             - alembic/               # Миграции

## Стек технологий
- FastAPI
- - PostgreSQL
  - - SQLAlchemy (async)
    - - Alembic
      - - Pydantic
        - - Docker, Docker Compose
         
        - ## Основные API эндпоинты
        - | Endpoint                  | Method | Описание                                                |
        - |--------------------------|--------|---------------------------------------------------------|
        - | /categories              | GET    | Получение списка категорий                              |
        - | /products                | GET    | Получение товаров по категории                          |
        - | /products/search         | GET    | Поиск товаров по названию                               |
        - | /products/{id}           | GET    | Детальная инфо о товаре                                 |
        - | /orders                  | POST   | Создание заказа                                         |
        - | /auth/login              | POST   | Авторизация (заглушка/SMS)                              |
        - | /auth/verify             | POST   | Подтверждение кода                                      |
       
      - ## Быстрый старт локально
     
      - 1. Установить Docker и docker-compose
        2. 2. Перейти в папку backend/
           3. 3. Выполнить команду для запуска контейнеров:
              4. ```
                 docker-compose up --build
                 ```
                 4. Приложение будет доступно на http://localhost:8000 (Swagger: /docs)
                
                 5. ## Описание моделей и эндпоинтов — см. api/ и models/
                
                 6. ---
                 7. Для подробной схемы смотрите roadmap в todo.md. Следующие файлы: requirements.txt, docker-compose.yaml, app/main.py и настройки моделей.
