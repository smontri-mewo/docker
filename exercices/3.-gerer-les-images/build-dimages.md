# Build d'images

## Dockerfile

```docker
FROM alpine:3.17.3

# CMD ["ping", "--help"]

# ENTRYPOINT ["ping", "--help"]

# ENTRYPOINT ["ping"]
# CMD ["--help"]

ENTRYPOINT ["sleep"]
CMD ["infinity"]
```

## Commande build

```bash
docker build -t <image:tag> -f <Dockerfile name> <working dir>
```

{% hint style="info" %}
Docker recherche le fichier Dockerfile dans le répertoire où la commande est utilisée et il est possible de préciser
{% endhint %}

## Créer une application Python conteneurisée

### Contenu

{% code title="app.py" %}
```python
from flask import Flask
app = Flask(__name__)
@app.route('/')
def home():
    return "Hello MEWO !!"
```
{% endcode %}

{% code title="requirements.txt" %}
```python
Flask==2.2.3
```
{% endcode %}

{% code title="Dockerfile" %}
```docker
FROM python

# Labels
LABEL version=v1.0.0
LABEL owner=smontri-app

# Env vars
ENV FLASK_APP=app.py
ENV FLASK_ENV=dev

ARG APP_USER=smontri

# Create a dedicated user

RUN adduser ${APP_USER}

# Directory
WORKDIR /app

# Copy & install requirements
RUN apt install -y curl

USER ${APP_USER}:${APP_USER}
COPY --chown=${APP_USER}  requirements.txt requirements.txt
RUN pip3 install --no-cache-dir -r requirements.txt

# Copy all files
COPY --chown=${APP_USER} . .

# Expose port
EXPOSE 5000

CMD ["python", "-m", "flask", "run", "--host=0.0.0.0"]
```
{% endcode %}

{% hint style="danger" %}
Adapter le digest en fonction de la plateforme
{% endhint %}

{% code title=".dockerignore" %}
```docker
Dockerfile
code.sh
*.md
.env
```
{% endcode %}

### Build de l'image

```bash
docker build -t myimg:v1.0.0 .
```

{% hint style="info" %}
Vérifiez la création de l'image en local
{% endhint %}
