# 🌐 Project Pikta

Проект **Pikta** — это социальная платформа / веб-приложение с функционалом публикаций, комментариев, чатов и системой аутентификации.  
Цель проекта — создание полноценного full-stack приложения с использованием **React** на фронтенде и **Django + DRF + Channels** на бэкенде, с хранением данных в **PostgreSQL и MongoDB**.

---
## 🧰 Технологии и стек

| Слой                | Технологии / библиотеки                                      |
|----------------------|--------------------------------------------------------------|
| **Backend**          | Django, Django REST Framework (DRF), Channels, SimpleJWT     |
| **Основная база данных** | PostgreSQL (через Django ORM)                             |
| **Дополнительная база данных** | MongoDB (pymongo, dnspython, bson) для хранения вспомогательных данных |
| **Frontend**         | React, React Router, Redux                                   |
| **Аутентификация**   | JWT (JSON Web Tokens) через DRF SimpleJWT                   |
| **Чаты / WebSocket** | Django Channels для real-time сообщений                     |
| **Медиа и файлы**    | Django media-папка для хранения изображений и аватаров       |
| **Email восстановление** | Поддержка восстановления пароля через почту               |

---

## 🎯 Назначение проекта

**Pikta** предоставляет пользователям следующие возможности:

- 🔐 Регистрация и вход в систему  
- 📧 Восстановление пароля через email  
- 📝 Создание и редактирование публикаций (текст + изображение)  
- 💬 Комментирование публикаций  
- 💭 Общение в реальном времени через встроенный чат  
- 👤 Управление профилем пользователя (аватар, данные, настройки)  
- 📰 Просмотр ленты публикаций других пользователей  

> Это учебный / портфельный проект, демонстрирующий навыки **full-stack разработки**: от базы данных и API до интерактивного клиентского интерфейса.

---
## 📷 Скриншоты

| Экран | Превью |
|-------|--------|
| 🔑 Авторизация | ![Auth](./screenshots/Auth.png) |
| 💬 Чат | ![Chat](./screenshots/Chat.png) |
| 📝 Создание поста | ![Create Post](./screenshots/Create%20Post.png) |
| 🌍 Лента публикаций (Explore) | ![Explore](./screenshots/Explore.png) |
| 🔔 Уведомления | ![Notifications](./screenshots/Notifications.png) |
| 📰 Пост | ![Post](./screenshots/Post.png) |
| 📄 Детали поста | ![PostDetail](./screenshots/PostDetail.png) |
| 👤 Профиль пользователя | ![Profile](./screenshots/Profile.png) |

---

## 🏃 Как запустить проект локально

```bash
git clone https://github.com/Aibatyr11/Project_Pikta.git
cd Project_Pikta
python -m venv venv
# для Windows
venv\Scripts\activate
# для macOS / Linux
source venv/bin/activate
pip install -r backend/requirements.txt

# Настройка базы данных и переменных окружения
# Убедись, что запущен MongoDB (локально или удалённо)
# В настройках Django (или .env) укажи URL подключения к MongoDB, например:
MONGODB_URI=mongodb+srv://user:password@cluster.mongodb.net/pikta
# Настрой SECRET_KEY, CORS, SMTP для восстановления пароля по email и т.д.

cd backend
python manage.py migrate
python manage.py createsuperuser


# Запуск серверов
# Бэкенд (ASGI/Daphne)
daphne samplesite.asgi:application --port 8000

# Фронтенд (React)
cd ../frontend
npm install
npm start


После запуска:
Фронтенд: http://localhost:3000
API / Бэкенд: http://localhost:8000

🧩 Структура проекта
Project_Pikta/
├── backend/           # Серверная часть Django + DRF + Channels
├── frontend/          # Клиентская часть React
├── screenshots/     
├── README.md
└── requirements.txt
