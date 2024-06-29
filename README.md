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

## Installation et Déploiement

1. Clonez les repositories GitHub des microservices.
2. Configurez chaque microservice avec les paramètres appropriés.
3. Déployez les microservices sur votre environnement cloud préféré.

## Auteur

Ce projet a été réalisé par Souleymane Kodjo. Pour toute question, vous pouvez le contacter à l'adresse suivante : souleymanekodjo@gmail.com.

## Contribution

Les contributions sont les bienvenues ! Veuillez soumettre une pull request pour toute amélioration ou nouvelle fonctionnalité.

## Licence

Ce projet est sous licence MIT. Voir le fichier [LICENSE](LICENSE) pour plus de détails.
