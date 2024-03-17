# Comment faire un controller

Pour créer un controller, vous pouvez utiliser la commande "edu" à la racine de votre projet. \
Vous pouvez l'utiliser à la racine de votre projet en tapant la commande suivante :

```Shell
php bin/edu make:controller NOM_DU_CONTROLLER
```

Exemple :

```Shell
php bin/edu make:controller TestController
```

Cette commande va créer un fichier "TestController.php" dans le dossier "src/Controller". \
Et modifier le fichier des routes "config/routes.yaml" pour ajouter la route de votre controller.

```YAML
test-controller:
  uri: /test-controller
  controller: Controller\TestControllerController
  httpMethod: [GET]
```

Vous pouvez accéder à votre controller en tapant l'url suivante : http://localhost:8042/test