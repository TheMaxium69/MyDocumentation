# Screen est une applications Linux

il sert a créer des session de terminal

comment ce servire de screen

```powershell
screen -ls
```
ls : permert de voir tout le session screen créer par l'utilisateur

```powershell
screen -S <name>
```
S : permet de créer une session

une fois créer il vous sera possible de lancer des application et de les laisser tournée sans problème

```powershell
screen -x <name>
```
x : permet de rejoindre une session


### Raccourcie

- Pour quittez un screen sans le éteindre
``CTRL + A`` puis ``D``

- Pour quittez le screen et le supprimer en même temps.
*à exécutez dans le screen en question
```powershell
$ exit
```

- Si le logiciel dans le screen a crash et que vous ne pouvez plus écrire dans le terminal du screen il vous suffit de supprimer le ficher qui a le même nom du screen dans 

``/run/screen/S-``UserNameLinux``/``
