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
