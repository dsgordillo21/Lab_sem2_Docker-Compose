# Laboratorio 02 - Docker Compose

Autor: Gordillo Saona Diego Manuel

El objetivo es trabajar un docker compose, especificando configuración y comandos para despliegue.

## Servicios

Se configuran tres instancias de la misma API, construidas localmente a partir del Dockerfile ubicado en la carpeta api.

- api01: puerto 3000
- api02: puerto 3001
- api03: puerto 3002

## Validación de Docker Compose

Para validar la configuración del archivo docker-compose.yaml se utiliza el siguiente comando:

```bash
docker compose config
```

## Despliegue

Para construir y levantar los servicios:

```bash
docker compose up -d --build
```

Para verificar los contenedores en ejecución:

```bash
docker compose ps
```

Para detener los servicios:

```bash
docker compose down
```

## Base de datos

Se utiliza PostgreSQL 17 como base de datos del proyecto.

La configuración se realiza mediante variables de entorno definidas en el archivo .env:

- POSTGRES_DB
- POSTGRES_USER
- POSTGRES_PASSWORD

## Volumen

Se utiliza el volumen postgres_data para almacenar de manera persistente los datos de PostgreSQL, evitando que se pierdan al eliminar o volver a crear el contenedor.

## Tipos de redes en Docker

- Bridge: Red utilizada por defecto. Permite la comunicación entre contenedores que se encuentran en el mismo host.
- Host: Elimina el aislamiento de red. El contenedor utiliza directamente la red del equipo anfitrión.
- None: Deja al contenedor sin acceso a una red externa.
- Overlay: Permite comunicar contenedores que se encuentran en diferentes hosts Docker.
- Macvlan: Asigna una dirección MAC al contenedor, haciendo que aparezca como un dispositivo dentro de la red.
- IPvlan: Permite conectar contenedores directamente a redes externas utilizando direccionamiento IP.

## Tipos de almacenamiento en Docker

- Volumes: Son administrados por Docker y permiten mantener los datos aunque el contenedor sea eliminado.
- Bind mounts: Enlazan una carpeta o archivo del equipo anfitrión con una ubicación dentro del contenedor.
- Tmpfs mounts: Almacenan información temporalmente en la memoria RAM y los datos se pierden cuando el contenedor se detiene.