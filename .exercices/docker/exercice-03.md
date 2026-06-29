# Exercice Docker #7

Via Docker, créer via les commandes `docker build` une image de conteneur de base de données (de type MySQL) possédant déjà plusieurs tables et données à son lancement. Tester ensuite son déploiement via les commandes `docker run`.
* Ce conteneur devra être initialisé via un script de type sql contenant l'initialisation de la base de données
* Ce conteneur devra être instancié via une image construite par vos soins

Concernant le contenu de la base de données, celle-ci devra se nommer kennelDB et comporter:
* Des clients (nom, prénom, date de naissance, pseudonymme)
* Des adresses (numéro, rue, code postal, commune)
* Des associations clients-adresses
* Des chiens (nom, date de naissance, race, statut de stérilisation)
* Des chats (nom, date de naissance, race, statut de stérilisation)

--- 

## Correction

```dockerfile
# Dockerfile

FROM mysql:9

COPY init.sql /docker-entrypoint-initdb.d/

ENV MYSQL_ROOT_PASSWORD password
# ou
ENV MYSQL_ROOT_PASSWORD=password

# docker build -t exo-03-database . => Pour build l'image

# docker run -d -p 3306:3306 --name exo-03-db -v exo-03-data:/var/lib/ mysql exo-03-database 
```