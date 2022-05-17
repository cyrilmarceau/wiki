---
id: commands
title: Commandes
sidebar_position: 2
---

## Build

> Note: Pensez à créer un fichier  `docker-compose.yml` et un `docker-compose.dev.yml` pour faciliter le passage en production.

```shell
docker-compose -f docker-compose.yml -f docker-compose.dev.yml build
```

## Start

> Note: Pensez à créer un fichier  `docker-compose.yml` et un `docker-compose.dev.yml` pour faciliter le passage en production.

```shell
docker-compose -f docker-compose.yml -f docker-compose.dev.yml build &&
docker-compose -f docker-compose.yml -f docker-compose.dev.yml up -d
```

> Note: `-f` permet de lié plusieurs fichier `.yml` entre eux

> Note: `-d` permet de lancer le conteneur en tâche de fond

## Récupérer le fichier d'environnement

Dans le fichier `docker-compose.dev.yml` et dans votre <mark>serviceName</mark>, rajouté ces 2 lignes

```shell
env_file:
    - .env
```

## Se connecter en shell

```shell
sudo docker-compose -f docker-compose.yml -f docker-compose.dev.yml exec serviceName bash
```

## Afficher les logs du conteneur

```shell
sudo docker-compose -f docker-compose.yml -f docker-compose.dev.yml logs -f serviceName
```

## Afficher la liste des conteneurs du projet

```shell
cd /var/www/html/yourProject
```

```shell
sudo docker-compose -f docker-compose.yml -f docker-compose.dev.yml ps
```
