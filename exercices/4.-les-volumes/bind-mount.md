# Bind Mount

## Créer un montage depuis un chemin sur le host qui exécute Docker

```bash
# Avec utilisation -v
docker run -d -it --name devtest -v "$(pwd)"/target:/app nginx:latest

# Avec utilisation --mount
docker run -d \
  -it \
  --name devtest \
  --mount type=bind,source="$(pwd)"/target,target=/app \
  nginx:latest
```

## Vérification du mount dans le container avec commande inspect

```bash
docker container inspect devtest
```

{% hint style="info" %}
Bind Mount est plutôt utilisé quand les modifications se font sur le host
{% endhint %}
