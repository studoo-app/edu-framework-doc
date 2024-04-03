# Démarrer l'application

Pour démarrer l'application, il suffit de lancer la commande suivante :

<tabs>
    <tab title="à partir v1.2">
        <code-block lang="Bash">
        php bin/edu start
        </code-block>
    </tab>
    <tab title="Jusqu'en v1.1">
        Si vous avez la version v1.1 et inférieur, le démarrage se passe avec la commande suivante :
        <code-block lang="Bash">
        composer edu:start
        </code-block>
    </tab>
</tabs>

Cette commande va démarrer le serveur de développement à l'adresse [http://localhost:8042](http://localhost:8042).

## Erreur de démarrage

### Failed to listen on localhost:8042 (reason: Address already in use)
Cette erreur vient que le port d'écoute (socket) 8042 est déjà utilisé (ou mal fermé)
Pour résoudre cette erreur, vous pouvez "killer" le processus attaché au port d'écoute.

La commande pour tuer le processus lié au port 8042 sur macOS est la suivante :

```bash
lsof -i :8042 | awk 'NR!=1 {print $2}' | xargs kill -9
```

Cette commande fonctionne en trois parties :

1. `lsof -i :8042` : Cette commande liste tous les processus utilisant le port 8042.
2. `awk 'NR!=1 {print $2}'` : Cette commande extrait le numéro de processus (PID) de la sortie de la commande précédente.
3. `xargs kill -9` : Cette commande utilise le PID extrait pour tuer le processus.

Sous Windows, la commande pour tuer le processus lié au port 8042 est légèrement différente. Voici comment vous pouvez le faire :

```bash
FOR /F "tokens=5" %P IN ('netstat -a -n -o ^| findstr :8042') DO TaskKill.exe /F /PID %P
```

Cette commande fonctionne en deux parties :

1. `netstat -a -n -o ^| findstr :8042` : Cette commande liste tous les processus utilisant le port 8042.
2. `TaskKill.exe /F /PID %P` : Cette commande utilise le PID extrait pour tuer le processus.
