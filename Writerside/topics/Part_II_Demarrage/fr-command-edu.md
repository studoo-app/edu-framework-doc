# La commande edu 

Nous avons mise en place une commande pour faciliter les taches. Cette commande est appelée "edu".
Vous pouvez l'utiliser à la racine de votre projet en tapant la commande suivante :

```Shell
php bin/edu 
```

Pour voir les commandes disponibles, vous pouvez taper la commande suivante :

```Shell
php bin/edu list
``` 

## Command no found

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