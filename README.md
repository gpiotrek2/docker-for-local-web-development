# docker-for-local-web-development
My docker compose for local web development LEMP

## Clone this repo
```
git clone git@github.com:gpiotrek2/docker-for-local-web-development.git
```

## Build backend

```
docker compose build backend
```


## Download required packages

```
docker compose run --rm backend composer install
```

## Run all (nginx, php, mariadb, adminer)
```
docker compose up
```

## Access to services
* nginx   :80
* adminer :8080
* mariadb :3306

