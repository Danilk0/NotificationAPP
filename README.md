# NotificationAPP
Этот репозиторий содержит `docker-compose` конфигурацию для запуска микросервисного приложения, состоящего из двух сервисов:

- 🔐 **auth-service** — сервис аутентификации пользователей.
- 📧 **notification-service** — сервис отправки email-уведомлений

Микросервисы взаимодействуют между собой через **RabbitMQ**, обеспечивая асинхронную и надёжную доставку сообщений.

---

## ⚙️ Настройка Notification Service

Чтобы `notification-service` мог отправлять письма, необходимо корректно настроить `application.yaml`.  
А именно указать корректные данные 
```yaml

mail:
    host: YOUR_EMAIL_HOST
    port: 587
    username: YOUR_EMAIL_USERNAME
    password: YOUR_EMAIL_APP_PASSWORD

```
### Запуск через Docker Compose

1. Убедись, что у тебя установлен Docker и Docker Compose
2. В корне проекта уже есть файл `docker-compose.yml` (при необходимости настрой его)
3. Собери Docker-образ приложения:

   ```bash
   docker build -t bankcards-api .
4. Запусти сервисы командой:
   ```bash
    docker-compose up -d
---