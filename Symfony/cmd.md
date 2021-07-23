# Commande Symfony

Créer un ``Projet``
-
```shell
$ symfony new <NAME> --full
```

Lancer le ``Serveur`` symfo 
-
```powershell
$ symfony serve
``` 

Créer un ``Controller``
-
```powershell
$ php bin/console make:controller
```

Creer une ``Entity``
-
```powershell
$ php bin/console make:entity
```

Faire un commit de la ``Migration``
-
```powershell
$ php bin/console make:migration
```

Appliquer la ``Migration``
-
```powershell
$ php bin/console doctrine:migrations:migrate
```

Créer un ficher ``Type``, pour un ``Form``
-
```powershell
$ php bin/console make:form
```

Setup les ``Fixture``
-
```powershell
$ composer require orm-fixtures --dev
```

Créer une ``Fixture``
-
```powershell
$ php bin/console make:fixtures
``` 

Load les ``Fixture``
-
```powershell
$ php bin/console doctrine:fixtures:load
```

Vider le ``Cache``
-
```powershell
$ php bin/console cache:clear
```