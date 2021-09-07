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

**PS : J'ai fait une documentations pour expliqué ce que vous avez besoin dans screen**

[![Docs de screen](https://img.shields.io/badge/MyDocs-Screen-FF0000)](https://github.com/TheMaxium69/MyDocumentation/blob/main/Linux/Screen.md)

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

mais on a aussi besoin de apache pour lancer **phpmyadmin**, il en a besoin pour etre accesible avec un navigateur

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

[![Docs de apache2](https://img.shields.io/badge/Docs-PhpMyAdmin-3960ef)](https://doc.ubuntu-fr.org/phpmyadmin/)

*PhpMyAdmin* est un panel pour gerez votre moteur sql, au lieu de le faire par ligne Sql

```powershell
$ sudo apt-get install phpmyadmin
```

après cette installation on vas configurez **apache2** pour qu'il lance **PhpMyAdmin**

il vas faloir déplacer le ficher de config de **phpMyAdmin** dans un dossier **apache2**

```powershell
$ sudo mv /etc/phpmyadmin/apache.conf /etc/apache2/conf-enabled/apache.conf
```

et on oublie pas de relancer **apache2** et votre moteur sql pour qu'il comprenne les changement

MySQL
```powershell
$ sudo service mysql restart
$ sudo service apache2 restart
```
ou MariaDB
```powershell
$ sudo service mariadb restart
$ sudo service apache2 restart
```

## Après le front et db

### - Tester le front

pour savoir si tout marche bien essayer d'allez sur l'url de votre site web

HostName = Votre Ip

``http://``HOSTNAME``/``

*https ne marchera pas verifer bien et faire attentions certaines extentions ou navigateur (brave par exemple) mette un S sans vous prevenir

si une page de configurations apache ce lance c'est que tout est configuré

### - Tester la db

On vas devoir configuré un utilisateur SQL

on ce connecte au terminal SQL

MySQL
```powershell
sudo mysql
```
ou MariaDB
```powershell
sudo mariadb
```

* la suite est identique entre MariaDB ou MySQL

Nous venons de nous connecter a l'acces route des command sql (ici on pourrais créer nos table et tout mais nous on vas utuliser **PhpMyAdmin**) 
mais avant il nous faut nous créer un utilisateur qui aura les permision de tout faire pour ce conneter a **PhpMyAdmin**

```sql
$ CREATE USER '<UserName>'@'localhost' IDENTIFIED BY '<PassWord>';
```

je vous laisse appeler et mettre le password que vous voulez 

*ne changez **SURTOUT PAS** localhost

puis on vas lui donné tout les permission

```sql
$ GRANT ALL PRIVILEGES ON *.* TO '<UserName>'@'localhost' WITH GRANT OPTION;
```

pour quittez le moteur sql il vous suffit de faire ça

```sql
$ exit
```

puis rendez vous sur 

``http://``HOSTNAME``/phpmyadmin``

je vous laisse vous connecter avec l'utilisateur qu'on viens de créer 

grace a ce qu'on viens de faire vous avez un compte qui a tout les permission

[![Docs](https://img.shields.io/badge/Docs-En%20Cas%20De%20Probleme-3960ef)](https://www.digitalocean.com/community/tutorials/how-to-install-and-secure-phpmyadmin-on-debian-9)

## Le BackEnd
