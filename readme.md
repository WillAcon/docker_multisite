# DOCKER CONTAINER
## PASOS PRA EJECUTAR DOCKER EN MULTIPLES SITIOS CON NGINX, PHP-FPM Y MYSQL

Luego de clonar el repositorio ejecutar:

```sh
docker-compose build
```

Para ejecutar la redacción en segundo plano, agregue la opción -d con el comando.

```sh
docker-compose -f ~/docker-compose/docker-compose.yml up -d
```

Después de ejecutar componer, verifique el estado del contenedor acoplable.

```sh
docker-compose ps
```

para agregar los sititios crear una carpeta sites/

```sh
mkdir sites
```
agregamos dos sitios

```sh
mkdir -p site1/web
mkdir -p site2/web
```
```sh
cd site1/web
touch index.php
```
```sh
cd site2/web
touch index.php
```
este es un ejemplo, pero ustedes pueden agregar un CMS, o cualquier otro proyecto estara ejecutandose dentro de la carpeta /web
