# Microservice Sample : Products Manager [![Build Status](https://travis-ci.org/SonarSource/sonarqube.svg?branch=master)](https://travis-ci.org/SonarSource/sonarqube) [![Quality Gate Status](https://sonarcloud.io/api/project_badges/measure?project=org.sonarsource.sonarqube%3Asonarqube&metric=alert_status)](https://sonarcloud.io/dashboard?id=org.sonarsource.sonarqube%3Asonarqube)

## Description
Projet Sample pour bien commence avec les microservices, l'approche contract first, versionning de la base de données avec liquibase et les utilisations des outils (docker, postman, ...)

## Build
~~~~
mvn build
~~~~

## Run local
La classe à lancer est _com.nyxo.conf.product.Main_

### Urls locals
* Racine des services : http://localhost:8080/editors
* Api docs : http://localhost:8080/v3/api-docs ou en [yaml](http://localhost:8080/v3/api-docs.yaml)
* Interface utilisateur Swagger : http://localhost:8080/swagger-ui.html

## Release
![Build Status](https://travis-ci.org/SonarSource/sonarqube.svg?branch=master)

## Base de données

* Utilisation de [liquibase](https://www.liquibase.org/)
* les changes set dans src/main/liquibase

![picture](productscopeDatabaseDiagram.png)

Commande mise à jour direct de la base : 
~~~~
mvn liquibase:update -Dliquibase.password=secret
~~~~
Commande de génération du fichier sql :
~~~~
mvn liquibase:updateSQL -Dliquibase.password=secret
~~~~
## Test Postman
Cf. fichier product.postman_collection.json

## Docker
Créer instance docker

Copier les fichiers :
* le jar renommé en product-1.00.00.jar
* application-docker.yaml : la configuration de l'application pour docker
* Dockerfile : le build de l'image Docker de l'application
* docker-compose.yaml : le script de composition et de démarrage des images

Commande de lancement : docker-compose up 

Commande d'arrêt : docker-compose down

Commandes de nettoyage des images :
* docker images 
* docker rmi xx ou xx est le début de l'identifiant d'une image 
