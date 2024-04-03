# Versionner avec GIT

Nous allons utiliser un système de contrôle de version distribué appelé "GIT"

Il permet de suivre les modifications apportées à un ensemble de fichiers au fil du temps, ce qui facilite la collaboration entre les développeurs.

Il offre également des fonctionnalités avancées telles que la possibilité de revenir à des versions antérieures de fichiers, de gérer les conflits de fusion et de collaborer avec d'autres développeurs.

Pour savoir sur GIT est installé sur votre poste de travail, tapez cette commande dans un terminal

````Bash
git --version
````

> Ce résultat est un exemple et il ne sera probablement pas le vôtre.
{style="tip"}

Voici le résultat :

````Bash
git version 2.39.2 (Apple Git-143)
````

## Installation

<tabs>
    <tab title="WINDOWS">
        Pour installation GIT, ouvrez un terminal (PowerShell) pour installer le bucket :
        <code-block lang="Bash">
        scoop bucket add main
        </code-block>
        Installation de GIT
        <code-block lang="Bash">
        scoop install main/git
        </code-block>
    </tab>
    <tab title="MAC OS">
        Pour installation GIT, ouvrez un terminal
        <code-block lang="Bash">
        brew install git
        </code-block>
    </tab>
</tabs>