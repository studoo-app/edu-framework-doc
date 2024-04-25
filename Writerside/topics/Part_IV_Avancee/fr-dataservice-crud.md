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
$statementPDO = $comBase->select("SELECT * FROM user");
// Recuperation des résultats de la requete
$users = $statementPDO->fetchAll();
```

### Update

Pour mettre à jour un enregistrement dans la base de données, vous devez utiliser la méthode `update` de la classe `DatabaseService`.

```php
// Recupere l'object PHP PDO
$comBase = DatabaseService::getConnect();
// Requete SQL
$statementPDO = $comBase->update("UPDATE user SET name='Jane Doe' WHERE id=1");
```

### Delete

Pour supprimer un enregistrement de la base de données, vous devez utiliser la méthode `delete` de la classe `DatabaseService`.

```php
// Recupere l'object PHP PDO
$comBase = DatabaseService::getConnect();
// Requete SQL
$statementPDO = $comBase->delete("DELETE FROM user WHERE id=1");
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

