# Comment installer Edu-F ?
Comment installer le framework Edu-Framework

## Installation
L'installation va se faire en ligne de commande via un terminal (git-bash, iterm, warp, tabby ...)

### Choisir son emplacement de projet
Utilisez la commande "cd" pour naviguer dans votre arborescence de fichiers et sélectionner l'emplacement de votre projet.

```Bash
cd NOM_DU_DOSSIER // pour avancer dans votre arboresence
cd .. // pour reculer
pwd // pour savoir ou vous êtes dans votre arboresence
```

# Création du projet

Nous allons créer le projet à l'aide du gestionnaire de paquets "composer". Cette étape vous permettra de construire la base du projet en une seule ligne de commande.

> Remplacez **NOM_DU_PROJET** par le nom de votre projet
> {style="warning"}

Saisir cette commande dans votre terminal :

````Bash
composer create-project studoo/edu-framework-skeleton NOM_DU_PROJET
````

Exemple d'affichage suite à la commande :

````Bash
Creating a "studoo/edu-framework-skeleton" project at "./NOM_DU_PROJET"
Installing studoo/edu-framework-skeleton (X.0.0)
  - Downloading studoo/edu-framework-skeleton (X.0.0)
  - Installing studoo/edu-framework-skeleton (X.0.0): Extracting archive
Created project in /Users/redbull/Projects/studoo/NOM_DU_PROJET
Loading composer repositories with package information
Updating dependencies
Lock file operations: 9 installs, 0 updates, 0 removals
  - Locking graham-campbell/result-type (X.1.x-dev 60c5f57)
    [...]
  - Locking vlucas/phpdotenv (dev-master 1a7ea2a)
Writing lock file
Installing dependencies from lock file (including require-dev)
Package operations: 9 installs, 0 updates, 0 removals
  - Installing symfony/polyfill-php80 (X.x-dev 6caa573): Extracting archive
    [...]
  - Installing studoo/edu-framework (dev-main c5cd9c5): Extracting archive
Generating autoload files
7 packages you are using are looking for funding.
Use the `composer fund` command to find out more!
No security vulnerability advisories found
````

Il est important de connaitre les étapes d'installation. Cela va vous permettre de comprendre en cas de problème d'installation.

> Voici es étapes de l'installation du projet :
> 
> **Creating "studoo/edu-framework-skeleton"** \
> Création d'un dossier temporaire \
> **Installing "studoo/edu-framework-skeleton"** \
> Téléchargement et installation du skeleton edu-framework \
> **Created project** \
> Création du dossier de votre projet dans votre arborescence de fichier \
> **Loading composer** \
> Lecture de votre fichier composer.json sur la partie "require" (liste des librairies) \
> **Updating dependencie** \
> Etude des dépendances de librairie (package) \
> **Writing lock file** \
> Ecriture du fichier composer.lock pour verrouiller les versions des librairies. \
> **Installing dependencie** \
> Installation des "vendor". C'est un dossier ou l'ensemble des librairies sont installées \
> **Generating autoload files** \
> Ecriture du fichier "/vendor/autoload.php" qui inclut l'ensemble des librairies. \
> **[...]** \
> Résultat de toutes les opérations. Des messages d'alerte concernant les mises à jour peuvent être générés dans cette section. \
> {style="tip"}

# Initialiser votre projet

Le projet vient de s'installer, la prochaine étape est d'initialiser les fichiers de configuration. \
Vous devez rentrer dans votre projet, via la commande "cd"

> Remplacez **NOM_DU_PROJET** par le nom de votre projet
> {style="warning"}

````Bash 
cd NOM_DU_PROJET
````

Puis, saisir cette commande dans votre terminal :

Exemple d'affichage suite à la commande :

> Ce résultat est un exemple et il ne sera probablement pas le vôtre. \
> L'importance est d'avoir les étapes suivantes : \
> Création du fichier ".env" si celui n'est pas déjà présent.
> {style="warning"}

````Bash 
composer edu:init
````

# Erreur de démarrage

Si vous démarrez votre serveur applicatif **sans le fichier ".env"** (Dotenv), voici le message d'erreur :

````Bash
Fatal error: Uncaught Dotenv\Exception\InvalidPathException: 
Unable to read any of the environment file(s) at [...]
````

