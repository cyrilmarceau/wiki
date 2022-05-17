---
id: mailhog
title: Mailhog
sidebar_position: 1
---

## Désactiver les logs lors d'envoie d'email

Dans le fichier `docker-compose.dev.yml` et dans le service mailhog, rajouté ces 2 lignes

```sh
logging:
    driver: 'none'
```

## Start

> Note: Pensez à créer un fichier  `docker-compose.yml` et un `docker-compose.dev.yml` pour faciliter le passage en production.

```sh
docker-compose -f docker-compose.yml -f docker-compose.dev.yml build &&
docker-compose -f docker-compose.yml -f docker-compose.dev.yml up -d
```

> Note: `-f` permet de lié plusieurs fichier `.yml` entre eux

> Note: `-d` permet de lancer le conteneur en tâche de fond
