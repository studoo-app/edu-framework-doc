# Release Notes

Présentation des versions du framework.

## v2.0 (2024)
- ajout de la commande `php bin/edu make:api` pour générer un controller de type API
- ajout de la commande `php bin/edu make:command` pour générer une commande console
- ajout d'une page par défaut sur la route /
- Barre de debug
- Refonte des configurations Docker
- Correction de bugs mineurs
- Documentation
  - Nouvelle interface et organisation par chapitre
  - new [Request : La gestion des requêtes HTTP](fr-resquet.md)
  - new [Liste des releases note](fr-release-edu.md)
  - update [Comment installer EduFrame](fr-comment-installer-edu.md) : Nouvelle installation par version
  - update [Comment installer les services](fr-comment-installer-services.md) : Refactoring Docker
  - update [Arborescence](fr-arborescence.md) : Nouvelle arbo v2.0
  - update [Comment faire un controller](fr-controller-edu.md) : Plus de detail
  - update [Comment faire un post dans un controller](fr-controller-post-edu.md) : Plus de detail

## v1.2 (03/2024)
- ajout de la commande `php bin/edu start` pour démarrer le serveur de développement
- ajout de la commande `php bin/edu check:config` pour vérifier la configuration du framework

## v1.1 (03/2024)
Version beta de la bar de debug avec les fonctionnalités suivantes :
- Mise en place de la bar de debug en beta sur environnement de développement
- Refonte de docker pour l'installation des services
- Correction de bugs mineurs
  - Docker : correction sur le reseau des services Mydql et PhpMyAdmin

## v1.0 (2024)
Version définitive du framework avec les fonctionnalités suivantes :
- Création de controller via la commande `php bin/edu make:controller`

## v0.6 (2023)
Version stable du framework avec les fonctionnalités suivantes :
- Création de controller
- Création de template
- Création de route
- Mise en place de la base de données

## v0.1 à v0.5 (2022-2023)
Versions de développement du framework avec les fonctionnalités suivantes :
- Mise en place et conception de l'architecture du framework (MVC)
- plusieurs POC des couches du MVC
- Tests unitaires
- Mise en place de la documentation du framework (Writerside)
- Gestion de la configuration du framework (DotEnv)
- Gestion de dépendances (Composer)
- Gestion des services (Docker)
