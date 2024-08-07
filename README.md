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

Copy the docker-laravel files to your Laravel project
```
cp -rf docker-laravel/* laravel/
```
Enter the project:
```
cd laravel
```
Create a `.env` file, but only if you're in a new project:
```
cp .env.example .env
```
Run the commands:
```
docker compose up --build -d
docker compose exec php composer install && php artisan key:generate
docker compose exec php npm install && npm run dev
```
Go to the `.env` file and rename the variable *DB_HOST*:
```
DB_HOST=mysql
```

Add the *server* block to the `vite.config.js` file, so it would look like this:
```
export default defineConfig({
    plugins: [
        laravel({
            input: ['resources/css/app.css', 'resources/js/app.js'],
            refresh: true,
        }),
    ],
    server : {
        host: '0.0.0.0',
        hmr : {
            host: 'localhost'
        }
    }
});
```

You can access the app containers with the command:
```
# In this case PHP is the service name specified in the compose.yml file
docker compose exec php sh
```
Access the app in http://localhost:8080.
