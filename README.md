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

## How to add Docker to an existint Laravel project

- Copy the directories `nginx` and `docker` and the files `compose.yml` and `compose-prod.yml`
to the root directory of your Laravel project.
- Run the commands:
```
docker compose up --build -d
docker compose exec php composer install && php artisan key:generate
```
