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


## Despliegue

Para construir y levantar los servicios:

```bash
docker compose up -d --build