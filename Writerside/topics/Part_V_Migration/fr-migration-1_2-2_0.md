# Migrer de la version 1.2 à la version 2.0

## Introduction
La version 2.0 du framework apporte de nombreuses améliorations et corrections de bugs. \
Je vous invite à lire attentivement les changements apportés pour migrer votre projet de la version 1.2 à la version 2.0.
Lien sur la release note : [Release note 2.0](fr-release-edu.md)

## Comment migrer ?
Pour migrer de la version 1.2 à la version 2.0, vous devez suivre les étapes suivantes :

1. **Analyser les changements** : Analysez les changements apportés par la nouvelle version pour comprendre leur impact sur votre projet.
2. **Sauvegarder vos données** : Assurez-vous de sauvegarder vos données avant de procéder à la migration pour éviter toute perte.
3. Faire les actions suivantes : 

3.1 **Mettre à jour le fichier composer** :
```
  "require": {
    "php": ">=8.1",
    "ext-mbstring": "*",
--    "studoo/edu-framework": "1.2.x-dev"
++    "studoo/edu-framework": "2.0.x-dev"
  },
```

3.2 **Mettre à jour le framework** :
```Bash
composer update studoo/edu-framework
```

Résultat :
```
[...]
Package operations: 0 installs, 1 update, 0 removals
  - Downloading studoo/edu-framework (2.0.x-dev xxxxx)
  - Upgrading studoo/edu-framework (1.2.x-dev ef385b8 => 2.0.x-dev xxxxx): Extracting archive
[...]
```

3.3 **Version le framework** :
```Bash
 php bin/edu --version
```

Résultat :
```
EduFramework v2.0.x-xxxx
```

## Les changements
Les changements sont nombreux entre la version 1.2 et la version 2.0. \
Voici les principaux changements à prendre en compte :

- **Docker** : 
Dans la version 1.2, les services était démarré avec la commande `composer edu:docker:db-service:start mysql`. \
En version 2.0, les services sont démarrés avec la commande `docker compose up -d`.

Voici les actions à réaliser pour migrer de la version 1.2 à la version 2.0 :

1. **Arrêter les services** : (si sont démarrés)
```Bash
composer edu:docker:db-service:stop mysql
```

2. **Téléchargement du nouveau fichier Docker** :

<tabs>
    <tab title="WINDOWS">
        <warning>
            <p>
                Ouvrir un terminal git bash à la racine de votre projet
            </p>
        </warning>
        Pour télécharger le fichier compose, suivre les instructions :
        <code-block lang="Bash">
        curl -o compose.yaml https://raw.githubusercontent.com/studoo-app/edu-framework/2.0/compose.yaml
        </code-block>
        Si vous rencontrez une erreur `curl: (35) schannel: next InitializeSecurityContext failed: Unknown error (0x80092012) - The revocation function was unable to check revocation for the certificate.`
        <code-block lang="Bash">
        curl --ssl-no-revoke -o compose.yaml https://raw.githubusercontent.com/studoo-app/edu-framework/2.0/compose.yaml
        </code-block>
    </tab>
    <tab title="MAC OS">
        <warning>
            <p>
                Ouvrir un terminal à la racine de votre projet
            </p>
        </warning>
        Pour télécharger le fichier compose, suivre les instructions :
        <code-block lang="Bash">
        curl -sS https://raw.githubusercontent.com/studoo-app/edu-framework/2.0/compose.yaml -o compose.yaml
        </code-block>
    </tab>
</tabs>

