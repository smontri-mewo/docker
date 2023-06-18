# Démarrer avec les volumes

### Créer un volume

```bash
docker volume create mynginx
docker volume ls
```

### Lancement du container

```bash
docker run -d --hostname -v mynginx:/usr/share/nginx/html/ --name c1 debian:latest
```

```bash
docker exec -ti c1 bash
```

### Supprimer des volumes

```bash
docker volume rm mynginx
```
