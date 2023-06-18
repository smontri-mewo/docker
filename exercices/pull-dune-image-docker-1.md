# 2. Premiers pas avec Docker

### Afficher les container

```bash
docker ps
```

### Exécuter un container NGINX

```bash
docker run nginx:latest
```

### Afficher tous les containers

```bash
docker ps -a
```

### Exécuter un container NGINX en mode detach

```bash
docker run -d nginx:latest
```

### Variantes

```bash
docker run -ti --name c1 debian:latest

docker run -ti --rm --name c1 debian:latest

docker run -ti --rm --name c1 --hostname host1 debian:latest

docker run -ti --rm --name c1 --hostname host1 --dns 8.8.8.8 debian:latest

docker stop c1

docker start c1

docker rm -f c1

docker rm -f $(docker ps -aq)
```

###
