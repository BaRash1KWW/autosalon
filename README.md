# AutoSalon Web

Веб-система управления автосалоном. Учебный проект по дисциплине "Проектирование, разработка и оптимизация веб-приложений".

## 🛠 Технологический стек
- **Backend:** Node.js, стандартный HTTP-модуль, Express-подобный роутинг.
- **Frontend:** HTML5, CSS3, Vanilla JS (рендеринг на стороне сервера).
- **Database:** Microsoft SQL Server (основная), SQLite (для unit-тестов).
- **DevOps:** Docker, Docker Compose, GitHub Actions (CI), Nginx (reverse proxy).

## 📂 Структура проекта
- `src/` — исходный код приложения (роутинг, работа с БД).
- `static/` — статические файлы (стили, robots.txt, sitemap.xml).
- `tests/` — unit-тесты (запускаются через `node --test`).
- `database/` — SQL-скрипты для инициализации MSSQL.
- `deploy/` — файлы для локальной репетиции деплоя (Nginx, HTTPS, Docker Compose).
- `.github/workflows/` — конфигурация CI/CD (GitHub Actions).

## 🚀 Запуск для разработки (SQLite)
Для быстрого запуска без установки SQL Server можно использовать SQLite (режим по умолчанию):
1. Установите зависимости: `npm install`
2. Запустите сервер: `node server.js`
3. Откройте `http://localhost:5000`

## 🚀 Запуск для разработки (MSSQL)
1. Выполните `database/sqlserver/AutoSalonDB_Create_And_Seed.sql` в SSMS.
2. Создайте в корне файл `.env`:
   ```env
   DB_CLIENT=mssql
   MSSQL_SERVER=localhost
   MSSQL_PORT=1433
   MSSQL_DATABASE=AutoSalonDB
   MSSQL_USER=sa
   MSSQL_PASSWORD=ваш_пароль