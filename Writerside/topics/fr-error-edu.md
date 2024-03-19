# Liste des erreurs

## Erreur APP_ENV : Warning: Undefined array key "APP_ENV"

Cette erreur vient d'une variable d'environnement non définie. 
Pour résoudre cette erreur, vous devez définir la variable d'environnement `APP_ENV` dans le fichier `.env` à la racine de votre projet.

Ouvrez le fichier `.env` à la racine de votre projet et ajoutez la ligne suivante :

````
## << Config application
APP_ENV=dev
## >> Config application
````

## Fatal error: Uncaught PDOException: SQLSTATE`[HY000] [2002]` Connection refused

Cette erreur vient de plusieurs problemes : 

- Votre base de donnée n'est pas disponible (service n'est pas démarré)
Démarrer votre service de base de donnée (docker ...)

- Vous n'avez pas les bons login/mot de passe
Ouvrez le fichier `.env` à la racine de votre projet et vérifier la ligne suivante :

````
## << Config Database
## pour activer la connexion à la base de données, il faut mettre DB_HOST_STATUS=true
DB_HOST_STATUS=true
DB_HOST=127.0.0.1
DB_SOCKET=3306
DB_USER=root
DB_PASSWORD=root
DB_NAME=app_db
## >> Config Database
````

Si vous ne voulez pas activer votre base de donnée, vous pouvez déactiver : 

````
## << Config Database
## pour activer la connexion à la base de données, il faut mettre DB_HOST_STATUS=true
DB_HOST_STATUS=false
````