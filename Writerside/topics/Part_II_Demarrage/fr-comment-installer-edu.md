# Comment installer Edu Framework ?
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
> Remplacez **VERSION** par la version souhaitée (ex : 1.2.x-dev)
> {style="warning"}

Tableau des versions EDU-Framework :

| Version   | Etat                                   | Date sortie |
|-----------|----------------------------------------|-------------|
| 2.0.x-dev | <a href="fr-release-edu.md">alpha</a>  | en cours    |
| 1.2.x-dev | <a href="fr-release-edu.md">stable</a> | 01/03/2024  |

<a href="fr-release-edu.md">Lien sur les informations des releases EduFrame</a>

Saisir cette commande dans votre terminal :

````Bash
composer create-project studoo/edu-framework-skeleton NOM_DU_PROJET VERSION
````

> Attention, cette commande peut comporter des erreurs si vous n'avez pas installé PHP. \
> Voir le chapitre "Erreur d'intallation du projet"
> {style="warning"}

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

## Erreur d'intallation du projet

Si vous rencontrez des erreurs lors de l'installation du projet, voici quelques explications pour vous aider :

### OpenSSL extension
````Bash
The openssl extension is required for SSL/TLS protection but is not availab
  le. If you can not enable the openssl extension, you can disable this error
  , at your own risk, by setting the 'disable-tls' option to true.
````
Vous devez activer l'extension openssl dans votre fichier php.ini. \
Pour savoir ou se trouve votre fichier php.ini, vous pouvez utiliser la commande suivante :

````Bash
php --ini
````
Vous aurez un résultat similaire à celui-ci :

````Bash
Configuration File (php.ini) Path: /usr/local/etc/php/8.0
Loaded Configuration File:         /usr/local/etc/php/8.0/php.ini
Scan for additional .ini files in: /usr/local/etc/php/8.0/conf.d
Additional .ini files parsed:      /usr/local/etc/php/8.0/conf.d/ext-opcache.ini
````
Dans cet exemple, le fichier php.ini se trouve dans le dossier "/usr/local/etc/php/8.0". \

Pour cela, vous devez ouvrir votre fichier php.ini et décommenter la ligne suivante :

````Bash
;extension=openssl
````
Enlever le point-virgule pour activer l'extension.

### mbstring extension
````Bash
Cannot use studoo/edu-framework-skeleton's latest version v1.3.0 as it requires ext-mbstring * which is missing from your platform.
 
In CreateProjectCommand.php line 421:
 
  Could not find package studoo/edu-framework-skeleton with stability stable in a version installa
  ble using your PHP version, PHP extensions and Composer version.
````
 
Pour cela, vous devez ouvrir votre fichier php.ini et décommenter la ligne suivante :

````Bash
;extension=mbstring
````
Enlever le point-virgule pour activer l'extension.

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

# Erreur d'installation des dépendances

Au moment de la commande "composer create-project studoo/edu-framework-skeleton ...", vous pouvez rencontrer des erreurs d'installation des dépendances. \
Voici un exemple de message d'erreur :

````Bash
Problem 1
- Root composer.json requires studoo/edu-framework dev-main, found studoo/edu-framework[dev-dev, v0.2.1, ..., v0.6.0, v1.0.0, ..., 1.4.x-dev] but it does not match the constraint.
````

Pour résoudre ce problème, plusieurs solutions s'offrent à vous :
 - vous devez supprimer le fichier "composer.lock" et relancer la commande "composer install"
 - vous devez mettre à jour la version de votre projet dans le fichier "composer.json" et relancer la commande "composer install"

Dans le fichier composer.json, vous devez modifier la ligne suivante :

````
"require": {
-     "studoo/edu-framework": "dev-main"
+     "studoo/edu-framework": "1.2.x-dev"
}
````
