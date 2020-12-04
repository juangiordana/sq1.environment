```sh
# Build services.
docker-compose build

# Install Laravel via the Composer `create-project` command.
docker-compose run --rm composer \
    composer create-project --prefer-dist laravel/laravel . "7.*"

# Install the `laravel/ui` Composer package.
docker-compose run --rm composer \
    composer require laravel/ui:^2.4

# Install the Bootstrap frontend with Authentication scaffolding.
docker-compose run --rm php-fpm \
    php artisan ui bootstrap --auth

# Install frontend dependencies via the Node package manager (NPM).
docker-compose run --rm node \
    npm install

# Run Laravel Mix tasks to compile frontend dependencies.
docker-compose run --rm node \
    npm run dev

# Start containers in detached mode.
docker-compose up -d

```
