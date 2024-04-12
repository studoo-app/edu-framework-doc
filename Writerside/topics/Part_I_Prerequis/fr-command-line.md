# Installer en ligne de commande

Un poste de développeur (ou toute personne qui travaille dans l'informatique), se doit de bien maitriser son poste de travail. (appelé aussi "setup")

Pour faciliter les installations et la maintenance de votre setup, nous vous recommandons d'utiliser un "command-line installer" (installation par ligne de commande)

**"command-line installer"** installe les programmes que vous connaissez et aimez à partir de la ligne de commande avec un minimum de friction. Il :

- Élimine les fenêtres contextuelles de permission
- Masque les installations de type assistant GUI
- Évite la pollution PATH de l'installation de nombreux programmes
- Évite les effets secondaires inattendus de l'installation et de la désinstallation de programmes
- Trouve et installe automatiquement les dépendances
- Effectue toutes les étapes de configuration supplémentaires pour obtenir un programme fonctionnel

## Installation

<tabs>
    <tab title="WINDOWS">
        <warning>
            <p>
                Ne pas ouvrir le PowerShell en mode administrateur
            </p>
        </warning>
        Pour installer "Scoop", suivre les instructions dans le "Quickstart" :
        <a href="https://scoop.sh/">https://scoop.sh</a>
    </tab>
    <tab title="MAC OS">
        Pour installer "Brew", suivre les instructions dans le "Installer Homebrew" :
        <tip>
            <p>
                L'installation de Xcode Command Line tools d'Apple peut être nécessaire <br/>
                Tapez la commande dans un terminal "xcode-select --install"
            </p>
        </tip>
        <a href="https://brew.sh/">https://brew.sh</a>
    </tab>
</tabs>