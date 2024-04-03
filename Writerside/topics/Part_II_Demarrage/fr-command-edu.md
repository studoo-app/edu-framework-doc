# La commande bin/edu 

Nous avons mise en place une commande pour faciliter les taches. Cette commande est appelée "edu".
Vous pouvez l'utiliser à la racine de votre projet en tapant la commande suivante :

```Shell
php bin/edu 
```

Pour voir les commandes disponibles, vous pouvez taper la commande suivante :

```Shell
php bin/edu list
``` 

Autre exemple, pour démarrer l'application, vous pouvez taper la commande suivante

```Shell
php bin/edu start
```

Voici les commandes disponibles par version :

> La version est disponible en tapant la commande suivante :
> ```Shell
> php bin/edu
> ```
> Remarque : La version est affichée en bas "EduFrame" (en jaune selon le terminal utilisé)
{style="info"}

| Composants      | Description                                   | A partir de la version |
|-----------------|-----------------------------------------------|------------------------|
| start           | pour démarrer l'application                   | v1.2                   |
| list            | pour lister les commandes disponibles         | v1.2                   |
| check:config    | check la configuration de votre environnement | v1.2                   |
| make:controller | génération d'un controller                    | v1.0                   |
| make:api        | génération d'un controller type json API      | v2.0                   |
| make:command    | génération d'un commande line                 | v2.0                   |


## Si vous rencontrez une erreur

### Command no found

Si vous avez une erreur pour utiliser la commande "edu", vous pouvez installer avec les commandes suivantes :
(exemple d'erreur : Could not open input file)

<tabs>
    <tab title="WINDOWS">
        Pour installer command "edu", suivre les instructions :
        <warning>
            <p>
                Ouvrir un terminal git bash à la racine de votre projet
            </p>
        </warning>
        <code-block lang="Bash">
        scoop bucket add main
        </code-block>
        Installation de CURL
        <code-block lang="Bash">
        scoop install main/curl
        </code-block>
        Quitter le terminal et ouvrir un nouveau terminal à la racine de votre projet
        <code-block lang="Bash">
        mkdir bin &amp;&amp; curl -o bin/edu https://raw.githubusercontent.com/studoo-app/edu-framework/main/bin/edu
        </code-block>
        Si vous rencontrez une erreur `curl: (35) schannel: next InitializeSecurityContext failed: Unknown error (0x80092012) - The revocation function was unable to check revocation for the certificate.`
        <code-block lang="Bash">
        curl --ssl-no-revoke -o bin/edu https://raw.githubusercontent.com/studoo-app/edu-framework/main/bin/edu
        </code-block>
    </tab>
    <tab title="MAC OS">
        Pour installer command "edu", suivre les instructions :
        <warning>
            <p>
                Ouvrir un terminal git bash à la racine de votre projet
            </p>
        </warning>
        <code-block lang="Bash">
        mkdir bin &amp;&amp; curl -sS https://raw.githubusercontent.com/studoo-app/edu-framework/main/bin/edu -o bin/edu
        </code-block>
    </tab>
</tabs>