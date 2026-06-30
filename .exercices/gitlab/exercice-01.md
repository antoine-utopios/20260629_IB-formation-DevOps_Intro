# Exercice GitLab CI #1

## Objectifs

Appréhender les pipelines Gitlab CI dans le cadre d'une application React.

## Sujets

Via l'archive fournie précédemment `.cours/gitlab/assets/application.zip`, réaliser un pipeline d'applicatif sur Gitlab qui réalise les actions suivantes:
* Test de la compilation de l'applicatif (génération d'un dossier `dist/`)
* Vérification de la compilation de l'applicatif (présence d'un fichier `dist/index.html` avec `<div id="root"></div>`)

Pour rappel, les commandes Node.js suivantes vont être nécessaires: 
* `npm install`: Installation des dépendances
* `npm run build`: Compilation de l'application et génération du dossier `dist/` 