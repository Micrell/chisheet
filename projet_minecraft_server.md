---
tags:
  - linux
status: inprogress
---

# Commande du VPS
## Choix de la configuration OVH
- debian
- 2 go de RAM
- 2 core CPU
- Pas de besoin de GPU
## Mise en place de la zone DNS (optionnel)
- zone A
## Première connexion
```sh
ssh debian@<server ip>
```
# Sécurisation de la connexion SSH

- Changer port SSH par défaut
- Connexion par certificat
- Désactiver connexion par mot de passe

```sh
vim /etc/ssh/sshd_config.d/.50-cloud-init.conf
```

```toml
# Disable authentication with passwords
PasswordAuthentication no
# Modify SSH server port, better to be in range 49152-65535
Port 50022
# Allow authentication with certificate
PubkeyAuthentication yes
# Set path to authorized_keys file
AuthorizedKeysFile      .ssh/authorized_keys .ssh/authorized_keys2
```

# Sécurisation avec un pare-feu logiciel
## Identifier les flux du serveur

| service          | port  | protocol | direction | description                        |
| ---------------- | ----- | -------- | --------- | ---------------------------------- |
| ssh              | 22    | tcp      | in / out  | shell interactif, maintenance      |
| http             | 80    | tcp      | in / out  | téléchargements, maintenance       |
| https            | 443   | tcp      | in / out  | téléchargements, maintenance       |
| minecraft server | 25565 | tcp      | in / out  | connexion des joueurs aux serveurs |
## Installation UFW
```sh
sudo apt install ufw
```
## Interdire par défaut
```sh
sudo ufw default deny incoming
sudo ufw default allow outgoing
```
## Autoriser les flux légitimes
```sh
sudo ufw allow ssh
sudo ufw allow http
sudo ufw allow https
sudo ufw allow 25565/tcp # Minecraft server
```
# Activer UFW
```sh
sudo ufw enable
```

# Utilisateur, groupe et permissions

NE PAS UTILISER SUDO
