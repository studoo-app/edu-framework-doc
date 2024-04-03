# Développer en PHP

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

## Activation des extensions

### Ou se trouve votre fichier php.ini
Pour savoir ou se trouve votre fichier php.ini, vous pouvez utiliser la commande suivante :

````Bash
php --ini
````
Vous aurez un résultat similaire à celui-ci :

````Bash
Configuration File (php.ini) Path: /usr/local/etc/php/8.1
Loaded Configuration File:         /usr/local/etc/php/8.1/php.ini
Scan for additional .ini files in: /usr/local/etc/php/8.1/conf.d
Additional .ini files parsed:      /usr/local/etc/php/8.1/conf.d/ext-opcache.ini
````
Dans cet exemple, le fichier php.ini se trouve dans le dossier "/usr/local/etc/php/8.1". \

### OpenSSL extension
Pour cela, vous devez ouvrir votre fichier php.ini et décommenter la ligne suivante :

````Bash
;extension=openssl
````
Enlever le point-virgule pour activer l'extension.

### mbstring extension
Pour cela, vous devez ouvrir votre fichier php.ini et décommenter la ligne suivante :

````Bash
;extension=mbstring
````
Enlever le point-virgule pour activer l'extension.

### pdo_mysql extension
Pour cela, vous devez ouvrir votre fichier php.ini et décommenter la ligne suivante :

````Bash
;extension=pdo_mysql
````
Enlever le point-virgule pour activer l'extension.