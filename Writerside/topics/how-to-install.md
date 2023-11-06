# Comment installer ?
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

### Création du projet

Nous allons créer le projet à l'aide du gestionnaire de paquets "composer". Cette étape vous permettra de construire la base du projet en une seule ligne de commande.

> Remplacez **NOM_DU_PROJET** par le nom de votre projet
> {style="warning"}

Saisir cette commande dans votre terminal :

````Bash
composer create-project studoo/edu-framework-skeleton NOM_DU_PROJET
````

