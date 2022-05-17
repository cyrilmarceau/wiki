---
id: apache
title: Mise en place
sidebar_position: 2
---

## Mise en place d'un domaine sur un serveur apache en local

### Ajouter le domaine dans le fichier hosts

```shell
sudo vim /etc/hosts
127.0.0.1 ecole.com
```

### Création du dossier dans le dossier wwww

```shell
cd /var/www/
mkdir ecole.com
cd ecole.com
sudo vim index.html
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ECOLE.COM</title>
</head>
<body>
    <h1>DOMAINE ecole.com ONLINE</h1>
</body>
</html>
```

On modifie les droits du dossier pour qu'on puisse y accéder et enregistrer de nouveau fichier / dossier
```shell
cd ../
sudo chown -R <user>:<user> ecole.com/
```

### Mise en place du virtual host

```shell
cd /etc/apache2/sites-available/
sudo vim ecole.com.conf
```

```shell
<VirtualHost *:80>
    DocumentRoot "/var/www/ecole.com"
    ServerName ecole.com
    ServerAlias www.ecole.com
</VirtualHost>
```

> Note: Si il y a besoin de faire pointer un sous domaine vers un serveur local

```shell
<VirtualHost *:80>
    DocumentRoot "/var/www/demo.monDomaine.com"
    ServerName demo.monDomaine.com
    ServerAlias www.demo.monDomaine.com
</VirtualHost>
```

> Note: Le lien se fais entre le serveurName et le DocumentRoot

Activer la conf apache

```shell
sudo a2ensite ecole.com.conf
```

> Note: Pour vérifier que la configuration est effectué

```shell
cd ../site-enabled
```

> Note: Vous devriez avoir un lien symbolique: `ecole.com.conf -> ../sites-available/ecole.com.conf`

```shell
sudo systemctl reload apache2
```

> Accéder à l'[url](http://ecole.com) et vous devriez avoir le contenu de votre fichier index.html qui s'affiche
