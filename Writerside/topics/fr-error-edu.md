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

