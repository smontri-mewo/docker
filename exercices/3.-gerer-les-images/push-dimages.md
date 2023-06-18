# Push d'images

## Pousser une image dans une registry

### Connexion à la registry

```bash
# Se connecter à la registry (ici DockerHub)
docker login -u <docker username> <server>
```

{% hint style="info" %}
DockerHub est le serveur par défaut
{% endhint %}

### Tagger l'image

```bash
# Tagger l'image pour pointer vers la registry
docker tag <image:tag> <registry/repository/image:tag>

docker tag nginx:latest smontri/nginx:v1.0.0
```

### Push de l'image

```bash
# Push vers la registry
docker push <registry/repository/image:tag>

docker push smontri/nginx:v1.0.0
```

### Vérification

Connectez-vous au Hub Docker pour vérifier que l'image a été poussé.
