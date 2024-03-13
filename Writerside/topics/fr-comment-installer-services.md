# Comment installer les services ?
Edu Framework utilise plusieurs services pour fonctionner. Pour les installer, vous avez deux possibilités :
- Utiliser Docker pour émuler les services 
- Installer les services directement sur votre machine

## Utiliser Docker pour émuler les services

> Démarrer Docker Desktop sur votre machine
{style="note"}

Pour utiliser Docker pour émuler les services, vous pouvez suivre les instructions suivantes :

````Shell
composer edu:init
````

Puis taper la commande suivante pour démarrer les services :

```Shell
composer edu:docker:db-service:start SERVICE
```
> Remplacer **SERVICE** par le nom du service que vous souhaitez démarrer. mysql ou mariadb
{style="info"}


## Installer les services sur votre machine

> Nous vous recommandons d'utiliser Docker pour émuler les services. Cela vous permettra de gagner du temps et de simplifier le processus de développement.
> Installer les services directement sur votre machine peut être plus complexe et plus long. Il fige également les versions des services installés.
> Ce qui peut poser des problèmes de compatibilité avec les versions utilisées par le framework.
{style="warning"}

Pour installer les services sur votre machine, vous pouvez installer les services suivants :
- MAMP (MAC OS)
- WAMP (WINDOWS)
- LAMP (LINUX)
- XAMPP (MAC OS, WINDOWS, LINUX)

> Cette liste n'est pas exhaustive et peut être amenée à évoluer.
{style="note"}





