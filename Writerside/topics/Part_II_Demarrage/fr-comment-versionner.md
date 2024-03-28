# Comment versionner votre projet ?

Pour travailler en mode projet, il est important de versionner son travail. Même tout seul !
Les raisons sont simples :

- Revenir en arrière en cas de mauvaise manip et d'implémentation foireuse
- Avoir plusieurs versions de test, stable…
- Gestion des issues (taches)

## Pour versionner le projet :

1/ Créez un nouveau dépôt (repository) chez votre fournisseur GIT (Github, GitLab ...)


> Veuillez noter que le repository doit être VIDE au moment de la création.
> Si ce n'est pas le cas, vous aurez des problèmes pour envoyer vos fichiers.
{style="warning"}

2/ Ouvrez un terminal et allez dans à la racine du projet

3/ Tapez les lignes suivantes :

- Initialisation du projet

````Bash
git init
````

- Ajout de l'URL du dépôt (repository) GIT

> Remplacez **URL_GIT_SSH** par le URL du repository lors sa création \
> Copier URL SSH qui se trouve dans le service GIT (ex : GITHUB) du repository \
> Voici un exemple : \
> "git remote add origin git@github.com:bfoujols/Testing-Edu-Frame.git" \
{style="warning"}

````Bash
git remote add origin URL_GIT_SSH
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

# Erreur de push

Si vous avez des erreurs lors du push, voici quelques commandes pour vous aider :

Afficher les URL des dépôts (repository) GIT configurés dans votre projet :

````Bash
git remote show origin
````

Pour effacer URL de l'origine (origin) qui est déjà configurée dans votre GIT :
````Bash
git remote rm origin
````

