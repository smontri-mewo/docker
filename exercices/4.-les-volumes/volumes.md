# Volumes

### Créer un volume

```bash
docker volume create myvol

docker volume ls
```

### Inspect du volume

```bash
docker volume inspect myvol
[
    {
        "Driver": "local",
        "Labels": {},
        "Mountpoint": "/var/lib/docker/volumes/myvol/_data",
        "Name": "my-vol",
        "Options": {},
        "Scope": "local"
    }
]
```

### Utiliser le volume avec un container

```bash
# Avec l'option --mount
docker run -d \
  --name devtest \
  --mount source=myvol,target=/app \
  nginx:latest
  
# Avec l'option -v
docker run -d \
  --name devtest \
  -v myvol:/app \
  nginx:latest
```

### Détails du volume dans le container

```bash
docker inspect devtest
```

### Supprimer des volumes

```bash
docker container stop devtest

docker container rm devtest

docker volume rm myvol
```

{% hint style="danger" %}
Un volume ne peut être supprimé si il est attaché à un container
{% endhint %}
