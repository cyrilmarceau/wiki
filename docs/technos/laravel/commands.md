---
id: commands
title: Commandes
sidebar_position: 2
---

## Création du model / controller / ressource

```sh
php artisan make:model <ModelName> -mcr
```

> Note: `-mcr` va créer le model controlleur et la ressource.
> Note: `-mcrfs` créera également la factory et le seeder associé au model.

## Migrations

Supprimer les tables et re-migrer:

```sh
php artisan migrate:fresh
```

Supprime les tables puis recrée en ajoutant les seeders:

```sh
php artisan migrate:refresh --seed
```

## Classe

Si il y a un problème avec les classes:

```sh
composer dump-autoload
```

## Cache

Réinitialiser le cache de la config:

```sh
php artisan config:clear
```

Réinitialiser le cache de l'application:

```sh
php artisan cache:clear
```

Réinitialiser le cache du routeur:

```sh
php artisan route:clear
```

Réinitialiser le cache des vues compilé

```sh
php artisan view:clear
```
