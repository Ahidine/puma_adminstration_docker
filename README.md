# docker-compose-laravel
LEMP stack for laravel


## Usage

Port


- **nginx** - `:80`
- **mysql** - `:3306`
- **php** - `:9000`

Initialization.
- cd src && clone project from github
- `docker-compose run --rm composer install`
-  cp .example.env .env
- `docker-compose run --rm artisan key:generate`
- `docker-compose run --rm artisan migrate`  LATER
- `docker-compose run --rm npm run install` 
- `docker-compose run --rm npm run dev`

!! make sur that storage dir in laravel project has www-data:www-data 755
## Persistent MySQL Storage

Later if we use MySql

1. Create a `mysql` folder in the project root, alongside the `nginx` and `src` folders.
2. Under the mysql service in your `docker-compose.yml` file, add the following lines:

```
volumes:
  - ./mysql:/var/lib/mysql
```
