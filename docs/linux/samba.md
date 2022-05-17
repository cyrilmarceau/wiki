---
id: samba
title: Samba
sidebar_position: 2
---

Samba est un outil qui permet de partager des dossier sur un même réseau local entre plusieurs poste

## Installation

```shell
sudo apt update
sudo apt install samba
```

Vérifier que samba est bien installé

```shell
whereis samba
```

Fichier de configuration samba

```shell
nano /etc/samba/smb.conf
```

En bas du fichier ajouter ces lignes

```shell
[yourName]
    comment = Little description
    path = /var/www/folderToShare
    read only = no
    browsable = yes
```

Redémarrer le serveur smb

```shell
sudo service smbd restart
```

Ajouter samba au firewall pour accepter le traffic

```shell
sudo ufw allow samba
```

Crée un compte pour accéder au partage

```shell
sudo smbpasswd -a <yourName>
```

Sur linux:

- Ouvrir le gestionnaire de fichier
- Allez dans l'onglet `+ autre emplacement`
- Dans connexion à un serveur renseigner la commande ci-dessous

Sur macOS:

- Ouvrir l'onglet `allez`
- Puis sur `se connecter à un serveur`
- renseigner la commande ci-dessous

Sur windows:

- Ouvrir le menu démarrer
- Puis dans la recherche executer la commande `\\<your-local-ip>`
- renseigner la commande ci-dessous

```shell
smb://<your-local-ip>/
```

> Note: L'ip local doit correspondre à l'ordinateur où samba est configurer !
