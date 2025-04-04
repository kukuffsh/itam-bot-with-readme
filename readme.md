# ITAM Telegram Бот

Многофункциональный Telegram бот для управления коворкинг-пространствами, клубами и профилями пользователей. Бот поддерживает несколько языков и включает функции управления коворкинг-пространствами, клубной деятельностью и административными задачами.

## Возможности

- **Многоязычная поддержка**: Поддержка нескольких языков с интеграцией i18n
- **Управление коворкинг-пространством**: 
  - Бронирование и управление коворкинг-пространствами
  - Управление расписанием
- **Управление клубом**:
  - Клубные мероприятия и события
  - Управление участниками
- **Профили пользователей**:
  - Регистрация и управление профилями пользователей
  - Система административных привилегий
- **Рассылка**: Возможность отправки сообщений нескольким пользователям
- **Планировщик задач**: Автоматическое планирование задач с использованием APScheduler

## Технический стек

- Python 3.x
- aiogram (Фреймворк для Telegram ботов)
- PostgreSQL (База данных)
- APScheduler (Планировщик задач)
- i18n (Интернационализация)

## Структура проекта

```
├── src/
│   ├── bot/           # Основной функционал бота
│   ├── controllers/   # Контроллеры бизнес-логики
│   ├── repositories/  # Репозитории базы данных
│   └── utils/         # Вспомогательные функции
├── translations/      # Файлы локализации
├── docker/           # Конфигурация Docker
├── postgres/         # Скрипты базы данных
└── requirements/     # Зависимости Python
```

## Настройка

1. Клонируйте репозиторий
2. Создайте виртуальное окружение:
   ```bash
   python -m venv venv
   source venv/bin/activate  # Для Unix/macOS
   # или
   .\venv\Scripts\activate  # Для Windows
   ```

3. Установите зависимости:
   ```bash
   pip install -r requirements/base.txt
   ```

4. Создайте файл `.env` на основе `.env.template`:
   ```
   BOT_TOKEN='ваш_токен_бота'
   BOT_NAME='имя_вашего_бота'
   POSTGRES_USER='пользователь_базы_данных'
   POSTGRES_PASSWORD='пароль_базы_данных'
   POSTGRES_DB='имя_базы_данных'
   POSTGRES_HOST='хост_базы_данных'
   SECRET='ваш_секретный_ключ'
   ```

5. Настройте базу данных:
   ```bash
   make db-up
   ```

6. Запустите бота:
   ```bash
   make run
   ```

## Развертывание в Docker

Для запуска бота с использованием Docker:

```bash
make docker-up
```

## Разработка

- Запуск тестов: `make test`
- Форматирование кода: `make format`
- Проверка кода: `make lint`

## Middleware

Бот использует несколько компонентов middleware:
- UserMiddleware: Обрабатывает аутентификацию и управление пользователями
- CoworkingMiddleware: Управляет операциями с коворкинг-пространством
- ClubMiddleware: Обрабатывает операции, связанные с клубом
- Localization: Управляет настройками языка
- SettingsMiddleware: Обрабатывает конфигурацию бота
- BotMiddleware: Основной функционал бота
- SchedulerMiddleware: Управляет запланированными задачами

## Участие в разработке

1. Сделайте форк репозитория
2. Создайте ветку для новой функции
3. Зафиксируйте изменения
4. Отправьте изменения в ветку
5. Создайте Pull Request

## Лицензия

[Добавьте информацию о лицензии]

# TODO:
- [ ] контроллер для управлением состояния коворкинга
- [ ] система ролей для управления / просмотра информации о коворке
- [ ] 