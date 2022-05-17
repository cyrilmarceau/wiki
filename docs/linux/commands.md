---
id: commands
title: Commandes
sidebar_position: 1
---

## Groupe d'utilisateur

CHanger le groupe d'utilisateur d'un dossier ou fichier

```shell
sudo chown -R [USERNAME]:[USERNAME] <path>
```

> Note: En générale on remplace [USERNAME] par `www-data`

Afficher tous les membres d'un groupe

```shell
grep ^www-data /etc/group
```

Ajouter un utilisateur à un groupe

```shell
sudo adduser cyril-linux www-data  
sudo passwd cyril-linux
```

Vérifier le groupe d'un utilisateur

```shell
id cyril-linux
```

> Output: `uid=1001(cyril-linux) gid=33(www-data) groupes=33(www-data)`

## Permissions

> Note: `chmod -R` pour appliquer les modifications de manière recursive

Modifie les permissions d'un fichier (lecture et écriture)

```shell
chmod 644
```

Modifie les permissions d'un dossier (lecture / écriture / exécution)

```shell
chmod 755
```
