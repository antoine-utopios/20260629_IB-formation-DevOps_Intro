# Récapitulatif des commandes Docker

* Vérifier l'installation et les versions du client et du serveur Docker

```bash
docker version
```

* Récupérer une image distante (par défaut depuis DockerHub / `docker.io`)

```bash
docker pull server/registry/image
docker pull registry/image # par défaut docker.io/registry/image
docker pull image # par défaut docker.io/library/image

```
* Déployer une image Docker sur notre machine

```bash
docker run server/registry/image

# Pour le mode intéractif (avec TTY)
docker run -it server/registry/image

# Pour le mode détaché
docker run -d server/registry/image

# Pour nommé le conteneur à la volée
docker run --name <container-name> server/registry/image

# Avec branchement de port (port-forwarding)
docker run -p <host>:<container> server/registry/image

# Avec variable d'environnement
docker run -e <variable-name>=<value> server/registry/image

# Avec volume (anonyme)
docker run -v /path/to/file/or/folder server/registry/image

# Avec volume (nommé)
docker run -v volume-name:/path/to/file/or/folder server/registry/image

# Avec volume (bind-mount bidirectionnel)
docker run -v /path/to/file/or/folder/on/host:/path/to/file/or/folder server/registry/image

# Avec volume (bind-mount en lecture seule)
docker run -v /path/to/file/or/folder/on/host:/path/to/file/or/folder:ro server/registry/image

# Avec réseau
docker run --network <network-name> server/registry/image
```

* Voir les conteneurs en cours d'exécution

```bash
docker ps

# Et ceux stoppés ou ayant crash
docker ps -a
```

* Voir les logs d'un conteneur

```bash
docker logs <id | name>

# En mode suivi
docker logs -f <id | name>
```

* Arrêter un conteneur

```bash
docker stop <id | name>
```

* Supprimer un conteneur

```bash
docker rm <id | name>

# Forcer l'arret en amont
docker rm -f <id | name>
```

* Créer un réseau virtuel Docker

```bash
docker network create <network-name>
```

* Créer une ressource Docker

```bash
docker <resource-type> create <resource-name> [options...]
```

