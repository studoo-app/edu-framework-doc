# L'arborescence du projet

L'arborescence du projet est la structure de votre projet. Elle est composée de dossiers et de fichiers. Cette structure est importante pour le bon fonctionnement du projet.

## Arborescence

Voici l'arborescence du projet :

```
├── app
│   ├── Config
│   │   └── route.yaml
│   ├── Controller
│   │   ├── DataBaseTestController.php
│   │   └── HomeController.php
│   └── Template
│       ├── base.html.twig
│       ├── home
│       │   ├── db.html.twig
│       │   └── home.html.twig
│       └── error
│           ├── http-404.html.twig
│           ├── http-405.html.twig
│           └── http-Default.html.twig
├── docker
│   └── [...] (Docker files)
├── public
│   └── index.php
├── vendor
│   └── [...] (Librairies)
├── .env
├── .env.example
├── .gitignore
├── composer.json
├── README.md
└── LICENSE
```

