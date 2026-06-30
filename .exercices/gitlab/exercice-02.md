# Exercice GitLab CI #1

## Objectifs

Utiliser les pipelines Gitlab CI dans le cadre d'une application Java.

## Sujets

Via l'archive fournie précédemment `.cours/gitlab/assets/api-java.zip`, réaliser un pipeline d'applicatif sur Gitlab qui réalise les actions suivantes:
* Test de la compilation de l'applicatif
* Réalisation des tests unitaires et publication des rapports de tests ainsi que de couverture de tests de l'applicatif (génération d'un dossier `target/site/jacoco/` pour la couverture et `target/surefire-reports/` pour les résultats de tests). Publier les rapports de tests au bon format pour les utiliser dans Gitlab CI par la suite
* Vérification des vulnérabilités de l'applicatif (pensez à utiliser l'image `aquasec/trivy`)
* Vérification de la qualité du code de l'application (via branchement à SonarKube Cloud `https://sonarcloud.io/`)
* Packaging de l'application en tant qu'image de conteneur Docker et publication de celle-ci dans le registre d'images de conteneurs de Gitlab (pensez au versionning)

Pour rappel, les commandes Maven suivantes vont être nécessaires: 
* `mvn -B -Dmaven.repo.local=.m2/repository -Dmaven.test.failure.ignore=false clean install -DskipTests`: Pour compiler l'applicatif
* `mvn -B -Dmaven.repo.local=.m2/repository -Dmaven.test.failure.ignore=false verify`: Pour lancer les tests et faire les rapports
* `mvn -B -Dmaven.repo.local=.m2/repository -Dmaven.test.failure.ignore=false verify sonar:sonar -Dsonar.projectKey=$PROJECT_KEY`: Pour lancer la vérification avec Sonar Scanner

Deux emplacements devraient être utilisés pour réaliser le cache des dépendances:
  - `.m2/repository`
  - `target/`