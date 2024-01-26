# docker-laravel
Laravel example project with Docker, MySQL and Redis

Requirements:
- Docker

Installation guide:

```
git clone https://github.com/VFDouglas/docker-laravel.git && cd docker-laravel
cp .env.example .env
docker compose up --build -d
docker compose exec php composer install && php artisan key:generate
```
Access the app in http://localhost:8080.
