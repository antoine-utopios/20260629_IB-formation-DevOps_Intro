# Exercice Docker #2

Via Docker, réaliser le déploiement de deux conteneurs servant à la manipulation de mysql: 

* L'un servira de serveur MySQL,
* L'autre sera utilisé pour se connecter au serveur dans le cadre de l'exercice

Pour cela, vous pouvez très bien utiliser deux fois le même conteneur basé sur une version de mysql, qui possède déjà à la fois le serveur et le client. 

Il faudra également s'assurer que le conteneur du serveur de base de données soit:
* Résilient aux redémarrages
* Résilient à un arret prématuré
* Compatible avec le mécanisme d'auto-scaling

## BONUS

Créer un conteneur ne disposant que du client MySQL et en faire une image pour une utilisation future