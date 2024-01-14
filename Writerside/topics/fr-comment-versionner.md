# Comment versionner votre projet ?

Pour travailler en mode projet, il est important de versionner son travail. Même tout seul !
Les raisons sont simples :

- Revenir en arrière en cas de mauvaise manip et d'implémentation foireuse
- Avoir plusieurs versions de test, stable…
- Gestion des issues (taches)

## Pour versionner le projet :

1/ Créez un nouveau dépôt (repository) chez votre fournisseur GIT (Github, GitLab ...)


> Veuillez noter que le repository doit être VIDE au moment de la création.
{style="warning"}

2/ Ouvrez un terminal et allez dans à la racine du projet

3/ Tapez les lignes suivantes :

- Initialisation du projet

````Bash
git init
````

- Ajout de l'URL du dépôt (repository) GIT

> Remplacez **\<URL GIT>** par le URL du repository lors sa création \
> Voici un exemple : \
> "git remote add origin git@github.com:bfoujols/Testing-Edu-Frame.git" \
> Cette URL se trouve dans le fourniseur du repository GIT
{style="warning"}

````Bash
git remote add origin <URL GIT>
````

- Ajout de la branche "main"

````Bash
git branch -M main
````

- Ajout des fichiers pour le commit

````Bash
git add * .gitignore .env.example
````

- Ajout du commit 'init project'

````Bash
git commit -m 'init project'
````

- Envoi des fichiers local sur le dépôt (repository) distant

````Bash
git push -u origin main
````
