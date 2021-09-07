# Configurations d'un server linux

## Nos besoin

- Un Front End 
- Une Base de donnée
- Symfony

#


## Ce connecter au serveur

- SSH

[![Wikis SSH](https://img.shields.io/badge/Wikis-SSH-3960ef)](https://fr.wikipedia.org/wiki/Secure_Shell)

Ouvré un terminal

```powershell
$ ssh <UserName>@<HostName>
password : <password>
```

*pour copier dans un terminal (Ctrl + Maj + V)

## Au début

- Mise a jour des packets

```powershell
$ sudo apt update
```

- Mise a jour logiciel

```powershell
$ sudo apt full-upgrade 
```

## Nos Premier logiciel

### - Installer Screen 

[![Docs de screen](https://img.shields.io/badge/Docs-Screen-3960ef)](https://doc.ubuntu-fr.org/screen/)


il nous permet de créer des sessions et de gardez notre symfony allumé même quand on ce déconnectera du ssh

```powershell
$ sudo apt-get install screen
```

### - Installer apache

[![Docs de apache2](https://img.shields.io/badge/Docs-Apache2-3960ef)](https://doc.ubuntu-fr.org/apache2/)

pour ceux qui ne le save pas pour mettre un site web en ligne il nous suffit d'apache il vas créer un dossier, qui sera un dossier public accesible enligne

dossier : ``/var/www/html/``

*ne toucher pas ces dossier

mais on a besoin de apache pour lancer **phpmyadmin**, il en a besoin pour etre accesible avec un navigateur

```powershell
$ sudo apt-get install apache2
```

### - Installer PHP

On a besoin de php pour *PhpMyAdmin* qui est un panel fait en **php**, mais aussi *symfony* qui est un framework **php**

```powershell
$ sudo apt-get install php
```

*par default il instal Php **7.4**

hesité pas a regarder votre version de php avec cette commende

```powershell
$ php -v
```

### - Installer un monteur SQL

Sois MariaDB

```powershell
$ sudo apt install mariadb-server
```

Sois MySQL

```powershell
$ sudo apt-get install mysql-server
```

***Aucune différence** entre les 2 au niveau de l'installations de le configuration de votre serveur

### - Installer PhpMyAdmin

*PhpMyAdmin* est un panel pour gerez votre moteur sql, au lieu de le faire par ligne Sql

```powershell
$ sudo apt-get install phpmyadmin
```

après cette installation on vas configurez **apache2** pour qu'il lance **PhpMyAdmin**

il vas faloir déplacer le ficher de config de **phpMyAdmin** dans un dossier **apache2**

```powershell
$ sudo mv /etc/phpmyadmin/apache.conf /etc/apache2/conf-enabled/apache.conf
```
