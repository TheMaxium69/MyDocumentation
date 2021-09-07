# Configurations d'un server linux

## Nos besoin

- Un Front End 
- Une Base de donnée
- Symfony

#


## Ce connecter au serveur

- Ssh 

[Wiki ssh](https://fr.wikipedia.org/wiki/Secure_Shell)

Ouvré un terminal

```powershell
$ ssh <UserName>@<HostName>
password : <password>
```

*pour copier dans un terminal (Ctrl + Maj + V)

## Au début

- Mise a jour des packets

```powershell
$ apt update
```

- Mise a jour logiciel

```powershell
$ apt full-upgrade 
```

## Nos Premier logiciel

### - Installer Screen 

[Docs de screen](https://doc.ubuntu-fr.org/screen)

il nous permet de créer des sessions et de gardez notre symfony allumé même quand on ce déconnectera du ssh

```powershell
$ apt install screen
```