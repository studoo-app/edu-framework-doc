# DatabaseService : La gestion des datas

DatabaseService est une classe qui permet de gérer les données de la base de données. Elle permet de faire des requêtes SQL, de récupérer des données, d'insérer, de mettre à jour et de supprimer des données.

Cette classe est de type Singleton, ce qui signifie qu'il n'y a qu'une seule instance de cette classe dans l'application.
Elle est instanciée automatiquement dans le framework et est accessible dans les controllers.

DatabaseService implémente l'interface de [PHP Data Objects (PDO)](https://www.php.net/manual/fr/book.pdo.php) pour autoriser l'accès de PHP aux bases de données


## Utilisation

Pour utiliser la classe DatabaseService, voici un exemple simple :

```php
// Recupere l'object PHP PDO
$comBase = DatabaseService::getConnect();
// Requete SQL
$statementPDO = $comBase->query("SELECT * FROM user");
// Recuperation des résultats de la requete
$users = $statementPDO->fetchAll();
```

$commBase est un objet de type PDO qui permet de faire des requêtes SQL sur la base de données.
$commBase->query() permet de faire une requête SQL sur la base de données.
$statementPDO est un objet de type PDOStatement qui contient les résultats de la requête.
$statementPDO->fetchAll() permet de récupérer les résultats de la requête.
