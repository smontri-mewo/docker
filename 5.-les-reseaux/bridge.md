# Bridge

### Afficher les informations de réseau (depuis le host)

```bash
ip a ou ifconfig
```

<figure><img src="../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

**On trouve le réseau bridge :**

* docker0
* range d'IP : 172.17.0.1/16

### Test de communication

* Créer un container

```bash
docker run --name c1 -d debian sleep infinity
```

* Exec du container

```bash
docker exec -it c1
```

* Installer les outils réseaux dans le container

```bash
apt install

apt install  iputils-ping net-tools
```

* Récupérer l'IP du container
* Ping vers l'IP du bridge
* Ping vers l'exérieur (ex : DNS Google)
