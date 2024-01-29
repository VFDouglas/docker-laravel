# docker-laravel
Laravel example project with Docker, MySQL and Redis

Installation guide:

Clone the project
```
git clone https://github.com/VFDouglas/docker-laravel.git
```
Clone a Laravel project or use an existing one.
```
git clone https://github.com/laravel/laravel.git
```
Enter the project and run the commands:
```
cd laravel
cp .env.example .env
docker compose up --build -d
docker compose exec php composer install && php artisan key:generate
```

You can access the app containers with the command:
```
# In this case PHP is the service name specified in the compose.yml file
docker compose exec php sh
```
Access the app in http://localhost:8080.
