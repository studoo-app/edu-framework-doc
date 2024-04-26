# DatabaseService : le crud

## Introduction

Le service DatabaseService permet de gérer les requêtes SQL sur la base de données. \
Il est basé sur l'objet PDO de PHP.

> Pour plus d'informations sur l'objet PDO, vous pouvez consulter la [documentation officielle](https://www.php.net/manual/fr/book.pdo.php).
> {style="info"}

Vous devez avoir lu la documentation sur la [DatabaseService : La gestion des datas](fr-dataservice.md) avant de continuer sur le CRUD

## CRUD

Le CRUD (Create, Read, Update, Delete) est un ensemble d'opérations de base pour la gestion des données dans une base de données.

### Create

Pour créer un nouvel enregistrement dans la base de données, vous devez utiliser la méthode `insert` de la classe `DatabaseService`.

```php
// Recupere l'object PHP PDO
$comBase = DatabaseService::getConnect();
// Requete SQL
$statementPDO = $comBase->insert("INSERT INTO user (name, email) VALUES ('John Doe', 'ben@toto.fr')");
```

### Read

Pour lire les enregistrements de la base de données, vous devez utiliser la méthode `select` de la classe `DatabaseService`.

```php
// Recupere l'object PHP PDO
$comBase = DatabaseService::getConnect();
// Requete SQL
$statementPDO = $comBase->query("SELECT * FROM user");
// Recuperation des résultats de la requete
$users = $statementPDO->fetchAll();
```

### Update

Pour mettre à jour un enregistrement dans la base de données, vous devez utiliser la méthode `update` de la classe `DatabaseService`.

```php
// Recupere l'object PHP PDO
$comBase = DatabaseService::getConnect();
// Requete SQL
$statementPDO = $comBase->query("UPDATE user SET name='Jane Doe' WHERE id=1");
```

### Delete

Pour supprimer un enregistrement de la base de données, vous devez utiliser la méthode `delete` de la classe `DatabaseService`.

```php
// Recupere l'object PHP PDO
$comBase = DatabaseService::getConnect();
// Requete SQL
$statementPDO = $comBase->query("DELETE FROM user WHERE id=1");
```

## Utilisation avancée

Pour une utilisation plus avancée et sécurisée du CRUD, vous pouvez utiliser les méthodes `prepare`, `execute`, `bindParam` de la classe `DatabaseService`.

```php
// Recupere l'object PHP PDO
$comBase = DatabaseService::getConnect();
// Requete SQL
$statementPDO = $comBase->prepare("SELECT * FROM user WHERE id = :id");
$statementPDO->execute(['id' => 1]);
// Recuperation des résultats de la requete
$users = $statementPDO->fetchAll();
```

# User Case Ville

Nous allons créer un CRUD pour la gestion des villes.

## Création de la table

```sql
CREATE TABLE ville (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nom VARCHAR(255) NOT NULL,
    code_postal VARCHAR(10) NOT NULL,
    nombre_habitant INT NOT NULL
);
INSERT INTO ville (nom, code_postal, nombre_habitant) VALUES ('Paris', '75000', 2200000);
INSERT INTO ville (nom, code_postal, nombre_habitant) VALUES ('Marseille', '13000', 800000);
INSERT INTO ville (nom, code_postal, nombre_habitant) VALUES ('Lyon', '69000', 500000);
```

## Création du CRUD

### Liste des Villes (Read)

```shell
php bin/edu make:controller villeRead
```

Cette commande va créer un fichier `VilleReadController.php` dans le dossier `app/Controller`, ajouter des lignes dans le fichier `config/routes.yaml` et créer un fichier `villeread.html.twig` dans le dossier `app/Template/villeread`.

Voici l'arborecence du projet :

```
├── app
│   ├── Config
│   │   └── routes.yaml
│   ├── Controller
│   │   └── VilleReadController.php
│   └── Template
│       ├── base.html.twig
│       └── villeread
│           └── villeread.html.twig
```

Dans le fichier VillereadController.php, vous devez ajouter :

```
<?php

namespace Controller;

use Studoo\EduFramework\Core\Controller\ControllerInterface;
use Studoo\EduFramework\Core\Controller\Request;
use Studoo\EduFramework\Core\Service\DatabaseService;
use Studoo\EduFramework\Core\View\TwigCore;

class VilleReadController implements ControllerInterface
{
	public function execute(Request $request): string|null
	{
+        // Recupere l'object PHP PDO
+        $comBase = DatabaseService::getConnect();
+        // Requete SQL
+        $statementPDO = $comBase->query("SELECT * FROM ville");
+        // Recuperation des résultats de la requete
+        $villes = $statementPDO->fetchAll();


		return TwigCore::getEnvironment()->render('villeread/villeread.html.twig',
		    [
		        "titre"   => 'VilleReadController',
		        "request" => $request,
 +               "villes" => $villes
		    ]
		);
	}
}
```

Dans le fichier `villeread.html.twig`, vous devez ajouter :

```
{% extends "base.html.twig" %}

{% block title %}{{ titre }}{% endblock %}

{% block content %}
    <h1>{{ titre }}</h1>
+    <table class="table">
+        <thead>
+            <tr>
+                <th scope="col">ID</th>
+                <th scope="col">Nom</th>
+                <th scope="col">Code Postal</th>
+                <th scope="col">Nombre d'habitants</th>
+            </tr>
+        </thead>
+        <tbody>
+            {% for ville in villes %}
+                <tr>
+                    <td>{{ ville.id }}</td>
+                    <td>{{ ville.nom }}</td>
+                    <td>{{ ville.code_postal }}</td>
+                    <td>{{ ville.nombre_habitant }}</td>
+                </tr>
+            {% endfor %}
+        </tbody>
+    </table>
{% endblock %}
```

### Ajouter des Villes (Create)

```shell
php bin/edu make:controller villeCreate
```

Cette commande va créer un fichier `VilleCreateController.php` dans le dossier `app/Controller`, ajouter des lignes dans le fichier `config/routes.yaml` et créer un fichier `villecreate.html.twig` dans le dossier `app/Template/villecreate`.

Voici l'arborecence du projet :

```
├── app
│   ├── Config
│   │   └── routes.yaml
│   ├── Controller
│   │   ├── VilleCreateController.php
│   │   └── VilleReadController.php
│   └── Template
│       ├── base.html.twig
│       ├── villecreate
│       │   └── villecreate.html.twig
│       └── villeread
│           └── villeread.html.twig
```

Comming soon...