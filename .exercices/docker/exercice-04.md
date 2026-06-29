# Exercice Docker #8

Réaliser le déploiement d'une API en Java (via Spring Boot) conteneurisée. 

Cette API permet la réalisation d'un CRUD de base sur des chiens.

Elle offre plusieurs endpoints qu'il faudra appeller avec un client HTTP de type Postman (software) ou Thunderclient (extension VS Code), de type: 
* `GET /api/v1/dogs`: Listing des chiens
* `GET /api/v1/dogs/{dogId}`: Récupération d'un chien et de ses détails
* `POST /api/v1/dogs`: Ajout d'un nouveau chien à notre base de données
* `PUT /api/v1/dogs/{dogId}`: Edition d'un chien via son ID
* `DELETE /api/v1/dogs/{dogId}`: Suppression d'un chien via son ID

Pour fonctionner, l'API en version production utilise Hibernate et est connectée à une base de données de type MySQL. Elle va piocher dans des variables d'environnement pour se lier à celle-ci:
* `DATABASE_HOST`: L'url du serveur de base de données 
* `DATABASE_PORT`: Le port du serveur de base de données
* `DATABASE_NAME`: Le nom de la base de données 
* `DATABASE_USER`: L'username permettant d'accéder au serveur de Base de données
* `DATABASE_PASSWORD`: Le mot de passe servant à se connecter à la base de données

La base de données sera également conteneurisée, de sorte à ne pas avoir à installer le moindre SGBD en local.

Pour activer la version production de l'applicatif Java, il est nécessaire de passer par la variable d'environnement `SPRING_PROFILES_ACTIVE` qui doit avoir pour valeur `prod` (le fichier de profil Spring Boot).

Pour réaliser une dockerization d'un applicatif Java, il est nécessaire de connaître les détails suivants: 
* `pom.xml`: Le fichier de dépendance permettant à Maven de rassembler et compiler les dépendances de notre applicatif métier
* `mvn dependency:go-offline -B`: La commande servant à Maven pour installer lesdites dépendances
* `mvn clean package -DskipTests` Commande servant à la création d'une archive au format `.jar` servant à Java pour lancer l'applicatif par la suite. Cette archive va se créer dans le dossier `target` du projet.
* `java -jar archive.jar`: Permet, via le Runtime Java, de demander le lancement d'un applicatif Java précédemment packagé et archivé au format `.jar`.
