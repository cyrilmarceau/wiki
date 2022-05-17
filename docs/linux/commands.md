---
id: commands
title: Commandes
sidebar_position: 2
---

## Groupe d'utilisateur

CHanger le groupe d'utilisateur d'un dossier ou fichier

```sh
sudo chown -R [USERNAME]:[USERNAME] <path>
```

> Note: En générale on remplace [USERNAME] par `www-data`

Afficher tous les membres d'un groupe

```sh
grep ^www-data /etc/group
```

Ajouter un utilisateur à un groupe

```sh
sudo adduser cyril-linux www-data  
sudo passwd cyril-linux
```

Vérifier le groupe d'un utilisateur

```sh
id cyril-linux
```

> Output: `uid=1001(cyril-linux) gid=33(www-data) groupes=33(www-data)`

## Permissions

> Note: `chmod -R` pour appliquer les modifications de manière recursive

Modifie les permissions d'un fichier (lecture et écriture)

```sh
chmod 644
```

Modifie les permissions d'un dossier (lecture / écriture / exécution)

```sh
chmod 755
```
