---
id: installation
title: Installation
sidebar_position: 1
---

## docker-compose

```shell
sudo curl -L "https://github.com/docker/compose/releases/download/${docker-compose.version}/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
```

> Note: `{docker-compose.version}` récupérer la dernière release disponible [ici](https://github.com/docker/compose/releases).

Ensuite, définissez les autorisations correctes de sorte que docker-compose soit exécutable:

```shell
sudo chmod +x /usr/local/bin/docker-compose
```

Vérifier que l'installation est réussis:

```shell
docker-compose --version
```

> Ouput: `docker-compose version 2.5.0, build 8a1c60f6`
