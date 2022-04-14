# Configuré le SSL sur un serveur linux

il sert a ajouter le s dans le protocole"https"

et vas chiffré les donné entre l'utilisateur et le site

#

## Installation

- Mise a jour des packets

```powershell
$ sudo apt update
```

- Puit installation de certbot

```powershell
$ sudo apt install -y certbot
```

### - Choix du moteur

Sois Apache2

```powershell
$ sudo apt install -y python3-certbot-apache
```

Sois Nginx

```powershell
$ sudo apt install -y python3-certbot-nginx
```

## Configuration

Sois Apache2

```powershell
$ sudo certbot certonly --apache -d example.com
```

Sois Nginx

```powershell
$ sudo certbot certonly --nginx -d example.com
```

*Pensez bien à mettre votre nom de domaine à la place de ``example.com``

Attention votre nom domain dois pointez sur l'ip du serveur avec le protocole ``A`` (pour une ipV4) ou ``AAA`` (ou pour ipV6), ou utilisé la redirection avec un autre nom de domaine mais **UNIQUEMENT** le protocole ``CNAME``

Puis si tout est fait correctement redémarré votre apache ou votre Nginx