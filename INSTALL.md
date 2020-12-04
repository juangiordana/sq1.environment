```sh
# Copy and review the Docker environment dotenv file.
cp .env.example .env

# Build services.
docker-compose build

# Fetch source files from repository.
git clone https://github.com/username/repository src

# Copy your Laravel project dotenv file.
cp .env.local src/.env

# Install Laravel application with Composer.
docker-compose run --rm composer \
    composer install

# Install frontend dependencies via the Node package manager (NPM).
docker-compose run --rm node \
    npm install

# Run Laravel Mix tasks to compile frontend dependencies.
docker-compose run --rm node \
    npm run dev

# Start containers in detached mode.
docker-compose up -d

# Run database migrations.
docker-compose exec php-fpm \
    php artisan migrate

```
