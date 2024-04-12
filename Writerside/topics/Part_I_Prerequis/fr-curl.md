# Commande CURL

Souvent utilisé pour les requêtes HTTP, CURL est un outil en ligne de commande pour transférer des données avec des URL.\
Il est souvent utilisé pour tester des API, des scripts ou télécharger des fichiers.

( <a href="https://curl.se/">https://curl.se/</a> )

<tabs>
    <tab title="WINDOWS">
        <warning>
            <p>
                Ouvrir un terminal git bash
            </p>
        </warning>
        Pour installer la commande "curl", suivre les instructions :
        <code-block lang="Bash">
        scoop bucket add main
        </code-block>
        Installation de CURL
        <code-block lang="Bash">
        scoop install main/curl
        </code-block>
        Quitter le terminal et ouvrir un nouveau terminal à la racine de votre projet
        Pour tester la commande "curl", vous pouvez taper la commande suivante :
        <code-block lang="Bash">
        curl --version
        </code-block>
    </tab>
    <tab title="MAC OS">
        <warning>
            <p>
                Ouvrir un terminal
            </p>
        </warning>
        Pour installer la commande "curl", suivre les instructions :
        <code-block lang="Bash">
        curl --version
        </code-block>
        Si "command not found", pour installer command "curl", suivre les instructions :
        <code-block lang="Bash">
        brew install curl
        </code-block>
    </tab>
</tabs>