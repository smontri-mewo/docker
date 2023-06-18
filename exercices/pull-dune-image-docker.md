---
description: Installation sur une VM Ubuntu
---

# 1. Installation de Docker

### &#x20;Suppression de version précédente de Docker

```bash
sudo apt remove docker docker-engine docker.io containerd runc
```

### Mise en place du dépot Docker

```bash
sudo apt install ca-certificates curl gnupg lsb-release
sudo mkdir -m 0755 -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
```



```bash
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/debian \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

### &#x20;Installation de Docker

```bash
sudo apt update
sudo apt install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

{% hint style="info" %}
Ajoutez également les packages d'utilitaires réseaux `iputils-ping` et `net-tools`&#x20;
{% endhint %}
