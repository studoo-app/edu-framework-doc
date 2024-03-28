# Liste des erreurs

> Cette page liste les erreurs courantes que vous pourriez rencontrer lors de l'installation ou de l'utilisation du projet Edu Framework.
> D'autres erreurs peuvent survenir, mais celles-ci sont dans les pages de la documentation.
> Nous vous recommandons d'utiliser le moteur de recherche pour trouver des solutions à vos problèmes.
> {style="warning"}

## Failed to listen on localhost:8042 (reason: Address already in use)
Cette erreur vient que le port d'écoute (socket) 8042 est déjà utilisé (ou mal fermé)
Pour résoudre cette erreur, vous pouvez "killer" le processus attaché au port d'écoute.

La commande pour tuer le processus lié au port 8042 sur macOS est la suivante :

```bash
lsof -i :8042 | awk 'NR!=1 {print $2}' | xargs kill -9
```

Cette commande fonctionne en trois parties :

1. `lsof -i :8042` : Cette commande liste tous les processus utilisant le port 8042.
2. `awk 'NR!=1 {print $2}'` : Cette commande extrait le numéro de processus (PID) de la sortie de la commande précédente.
3. `xargs kill -9` : Cette commande utilise le PID extrait pour tuer le processus.

Sous Windows, la commande pour tuer le processus lié au port 8042 est légèrement différente. Voici comment vous pouvez le faire :

```bash
FOR /F "tokens=5" %P IN ('netstat -a -n -o ^| findstr :8042') DO TaskKill.exe /F /PID %P
```

Cette commande fonctionne en deux parties :

1. `netstat -a -n -o ^| findstr :8042` : Cette commande liste tous les processus utilisant le port 8042.
2. `TaskKill.exe /F /PID %P` : Cette commande utilise le PID extrait pour tuer le processus.


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

## Si vous ne parvenez pas à vous connecter à votre base de données

Si vous ne parvenez pas à vous connecter à votre base de données, vous pouvez vérifier les points suivants :

- Dans le fichier `docker/docker-compose-***.yml` (*** remplacer par la version et le type de base de donnée), vérifiez que la configuration `networks` est bien renseignée

````
   database:
    container_name: ${APP_NAME}-database
    image: mysql:5.7
    platform: linux/amd64
    ports:
      - "3306:3306"
    restart: always
    environment:
      #MYSQL_ALLOW_EMPTY_PASSWORD: 'yes'
      MYSQL_ROOT_PASSWORD: ${DB_PASSWORD}
      MYSQL_DATABASE: ${DB_NAME}
      #MYSQL_USER: app_db_user
      #MYSQL_PASSWORD: app_db_password
+   networks:
+     - dev
    volumes:
      - ../var/dbdata:/var/lib/mysql
  #PHP My Admin
  phpmyadmin:
    container_name: ${APP_NAME}-pma
    image: phpmyadmin:latest
    restart: always
    depends_on:
      - database
    ports:
      - "8081:80"
    environment:
-      PMA_HOST: db
+      PMA_HOST: database
    networks:
      - dev
````

> Attention de bien respecter indentation et les espaces dans le fichier docker-compose
> {style="warning"}

Supprimez votre environnement docker

````Shell
  docker-compose down
````
  