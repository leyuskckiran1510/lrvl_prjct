### requirements
- docker
- computer that can run docker
- gut to use docker

### running first time
- rename `.env.example` to `.env` 
- setup the project
```bash
# Build and start the containers
docker-compose up -d --build

# Check running containers
docker ps

```
```bash
docker exec -it laravel_app bash

```
```bash
# Install PHP dependencies
composer install

# Generate application key
php artisan key:generate

# Run migrations
php artisan migrate
```

- fix the appache config :-
 edit this file `/etc/apache2/sites-available/000-default.conf`
 to have follwoing contents
 ```html
 <VirtualHost *:80>

    ServerAdmin webmaster@localhost
    DocumentRoot /var/www/html/public

    <Directory /var/www/html/public>
        Options Indexes FollowSymLinks
        AllowOverride All
        Require all granted
    </Directory>

    
    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>
```

### running next time
```bash
docker-compose up -d
```
