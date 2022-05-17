---
id: commands
title: Commandes
sidebar_position: 2
---

## Création du model / controller / ressource

```shell
php artisan make:model <ModelName> -mcr
```

> Note: `-mcr` va créer le model controlleur et la ressource.
> Note: `-mcrfs` créera également la factory et le seeder associé au model.

## Migrations

Supprimer les tables et re-migrer:

```shell
php artisan migrate:fresh
```

Supprime les tables puis recrée en ajoutant les seeders:

```shell
php artisan migrate:refresh --seed
```

## Classe

Si il y a un problème avec les classes:

```shell
composer dump-autoload
```

## Cache

Réinitialiser le cache de la config:

```shell
php artisan config:clear
```

Réinitialiser le cache de l'application:

```shell
php artisan cache:clear
```

Réinitialiser le cache du routeur:

```shell
php artisan route:clear
```

Réinitialiser le cache des vues compilé

```shell
php artisan view:clear
```
