# Comment installer et gérer les services ?
Edu Framework utilise plusieurs services pour fonctionner. Pour les installer, vous avez deux possibilités :
- Utiliser Docker pour émuler les services 
- Installer les services directement sur votre machine

## Utiliser Docker pour émuler les services

> Démarrer Docker Desktop sur votre machine
{style="note"}

<tabs>
    <tab title="à partir v2.0">
        Pour installation et démarrer des services, vous pouvez suivre les instructions suivantes :
        <code-block lang="Bash">
        docker compose up -d
        </code-block>
        Pour arrêter les services, vous pouvez suivre les instructions suivantes :
        <code-block lang="Bash">
        docker compose down
        </code-block>
    </tab>
    <tab title="Jusqu'en v1.2">
        Pour utiliser Docker pour émuler les services, vous pouvez suivre les instructions suivantes :
        <code-block lang="Bash">
        composer edu:init
        </code-block>
        Puis taper la commande suivante pour démarrer les services :
        <code-block lang="Bash">
        composer edu:docker:db-service:start mysql
        </code-block>
        Pour arrêter les services, vous pouvez suivre les instructions suivantes :
        <code-block lang="Bash">
        composer edu:docker:db-service:stop mysql
        </code-block>
    </tab>
</tabs>

## (ou) Installer les services sur votre machine (non recommandé

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