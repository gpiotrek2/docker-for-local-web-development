# docker-for-local-web-development
My docker compose for local web development LEMP

## clone this repo
```
git clone ...
```

## build backend

```
docker compose build backend
```


## download required packages

```
docker compose run --rm backend composer install
```

## run all (nginx, php, mariadb, adminer)
```
docker compose -d up
```

