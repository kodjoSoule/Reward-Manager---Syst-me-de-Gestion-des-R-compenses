# Reward-Manager - Système de Gestion des Récompenses

## Introduction

Le projet "Reward-Manager - Système de Gestion des Récompenses" est une application de microservices développée avec le framework Spring et Spring Cloud. Cette application permet aux clients d'économiser de l'argent à chaque fois qu'ils mangent dans l'un des restaurants participant au programme "Frequent Flyer Network". Les contributions économisées sont versées sur les comptes des clients et partagées entre leurs bénéficiaires.

## Objectifs

- Découvrir les concepts clés des microservices avec le framework Spring.
- Développer une application réelle pouvant être déployée sur le cloud.
- Gérer un réseau de restaurants participant au programme de récompenses.
- Calculer et distribuer les récompenses aux comptes des clients et leurs bénéficiaires.

## Fonctionnement du Plan Épargne Restaurant

1. Les membres dînent dans les restaurants du réseau en utilisant leurs cartes de crédit habituelles.
2. Un fichier contenant les transactions par carte de crédit est généré toutes les deux semaines.
3. Une application autonome "Dining Batch Processor" lit ce fichier et soumet chaque enregistrement de repas à l'application de récompenses "Rewards Dining" pour traitement.
4. L'application "Rewards Dining" calcule et distribue les récompenses sur les comptes des clients.

## Architecture de l'Application

L'application "Rewards Dining" est composée de quatre microservices principaux :

### 1. Benefit Restaurant Service

- **Fonctionnalités :**
  1. Lecture du taux de rémunération d'un restaurant.
  2. Ajout d'un restaurant dans le réseau.
  3. Lecture des restaurants du réseau.
  4. Suspension/Rétablissement de la participation d'un restaurant au programme "Reward Dining".

- **Lien GitHub :** [Benefit Restaurant Service](https://github.com/kodjoSoule/rm-benefits-restaurant-service)

### 2. Benefit Calculation Service

- **Fonctionnalités :**
  1. Calcul de la récompense offerte par un restaurant particulier pour un dîner précis.

- **Lien GitHub :** [Benefit Calculation Service](https://github.com/kodjoSoule/rm-benefit-calculation-service)

### 3. Reward Manager Service

- **Fonctionnalités :**
  1. Lecture des informations concernant une récompense précise.
  2. Création d’une récompense.

- **Lien GitHub :** [Reward Manager Service](https://github.com/kodjoSoule/rm-reward-manager-service)

### 4. Account Contribution Service

- **Fonctionnalités :**
  1. Création des comptes client.
  2. Création et ajout d'un bénéficiaire dans un compte spécifique.
  3. Lecture des comptes.
  4. Lecture d'un compte client spécifique.
  5. Lecture des bénéficiaires d'un compte spécifique.
  6. Lecture d'un bénéficiaire dans d'un compte spécifique.
  7. Partage de la récompense entre les bénéficiaires d'un compte spécifique.
  8. Mise à jour du pourcentage d’allocation d'un bénéficiaire dans un compte spécifique.

- **Lien GitHub :** [Account Contribution Service](https://github.com/kodjoSoule/rm-account-contribution-service)

### Client Frontend

Le client frontend de l'application est développé avec Angular 17 et Bootstrap, offrant une interface utilisateur moderne et réactive pour les utilisateurs finaux.

- **Fonctionnalités :**
  1. Inscription et connexion des utilisateurs.
  2. Consultation des restaurants participants.
  3. Suivi des transactions et des récompenses.
  4. Gestion des comptes et des bénéficiaires.

- **Lien GitHub :** [Client Frontend](https://github.com/kodjoSoule/reward-manager-front-end)

## Installation et Déploiement

### Pré-requis

- Java 17 ou version supérieure
- Maven 3.8 ou version supérieure
- Node.js 16 ou version supérieure
- Angular CLI 12 ou version supérieure
- Docker (optionnel)

### Étapes

1. Clonez les repositories GitHub des microservices et du client frontend.
    ```bash
    git clone https://github.com/kodjoSoule/rm-benefits-restaurant-service
    git clone https://github.com/kodjoSoule/rm-benefit-calculation-service
    git clone https://github.com/kodjoSoule/rm-reward-manager-service
    git clone https://github.com/kodjoSoule/rm-account-contribution-service
    git clone https://github.com/kodjoSoule/reward-manager-front-end
    ```

2. Construisez les microservices :
    ```bash
    cd rm-benefits-restaurant-service
    mvn clean install
    cd ../rm-benefit-calculation-service
    mvn clean install
    cd ../rm-reward-manager-service
    mvn clean install
    cd ../rm-account-contribution-service
    mvn clean install
    ```

3. Lancez les microservices :
    ```bash
    java -jar rm-benefits-restaurant-service/target/benefit-restaurant-service.jar
    java -jar rm-benefit-calculation-service/target/benefit-calculation-service.jar
    java -jar rm-reward-manager-service/target/reward-manager-service.jar
    java -jar rm-account-contribution-service/target/account-contribution-service.jar
    ```

4. Configurez et lancez le client frontend :
    ```bash
    cd reward-manager-front-end
    npm install
    ng serve
    ```

5. Accédez à l'application frontend via `http://localhost:4200`.

## Auteur

Ce projet a été réalisé par Souleymane Kodjo. Pour toute question, vous pouvez le contacter à l'adresse suivante : souleymanekodjo@gmail.com.

## Contribution

Les contributions sont les bienvenues ! Veuillez soumettre une pull request pour toute amélioration ou nouvelle fonctionnalité.

## Licence

Ce projet est sous licence MIT. Voir le fichier [LICENSE](LICENSE) pour plus de détails.
