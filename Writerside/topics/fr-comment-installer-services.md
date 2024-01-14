# Comment installer les services ?
Edu Framework utilise plusieurs services pour fonctionner. Pour les installer, vous avez deux possibilités :
- Utiliser Docker pour émuler les services 
- Installer les services directement sur votre machine

## Utiliser Docker pour émuler les services
Pour utiliser Docker pour émuler les services, vous pouvez suivre les instructions suivantes :

> Démarrer Docker Desktop sur votre machine
{style="note"}

````Shell
composer edu:init
````

Puis taper la commande suivante pour démarrer les services :

```Shell
composer edu:docker:db-service:start
```


## Installer les services sur votre machine

Pour installer les services sur votre machine, vous pouvez installer les services suivants :
- MAMP (MAC OS)
- WAMP (WINDOWS)
- LAMP (LINUX)
- XAMPP (MAC OS, WINDOWS, LINUX)

> Cette liste n'est pas exhaustive et peut être amenée à évoluer.
{style="warning"}

