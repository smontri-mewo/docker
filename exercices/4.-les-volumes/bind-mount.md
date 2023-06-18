# Bind Mount

Créer un montage depuis un chemin sur le host qui exécute Docker

```bash
docker run -d -it --name devtest -v "$(pwd)"/target:/app nginx:latest
```

Vérification du mount dans le container avec commande inspect

```bash
docker container inspect devtest
```
