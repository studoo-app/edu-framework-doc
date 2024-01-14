# PHP

Ce framework utilise le langage PHP.
( <a href="https://www.php.net/">https://www.php.net</a> )

Pour savoir si PHP est installé sur votre machine, ouvrez un terminal et saisir cette commande : 

````Bash
php -v
````

> Ce résultat est un exemple et il ne sera probablement pas le vôtre.
{style="tip"}

Voici le résultat :

````Bash
PHP 8.1.21 (cli) (built: Jul  6 2023 16:08:36) (NTS)
Copyright (c) The PHP Group
Zend Engine v4.1.21, Copyright (c) Zend Technologies
    with Zend OPcache v8.1.21, Copyright (c), by Zend Technologies
````

## Installation

> Nous vous recommendons d'installer la version 8.1
> {style="tip"}

<tabs>
    <tab title="WINDOWS">
        Pour installation PHP, ouvrez un terminal (PowerShell) pour installer le bucket :
        <code-block lang="Bash">
        scoop bucket add versions
        </code-block>
        Installation de PHP
        <code-block lang="Bash">
        scoop install versions/php81
        </code-block>
    </tab>
    <tab title="MAC OS">
        Pour installation PHP, ouvrez un terminal
        <code-block lang="Bash">
        brew install php@8.1
        </code-block>
    </tab>
</tabs>