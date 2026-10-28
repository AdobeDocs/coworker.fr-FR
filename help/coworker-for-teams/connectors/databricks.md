---
description: Collègue pour les équipes vous permet de connecter et d’interroger les tables du catalogue Unity dans votre espace de travail des briques de données pour créer et activer des audiences de campagne.
title: Connexion aux briques de données
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: Coworker
source-git-commit: 312450e09d9252f17cb2b5d471ee33e1a22b9a05
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 0%
---
# Connexion aux briques de données {#databricks}

Collègue pour les équipes vous permet de connecter et d’interroger les tables du catalogue Unity dans votre espace de travail des briques de données pour créer et activer des audiences de campagne.

>[!PREREQUISITES]
>
>Pour utiliser ce connecteur, vous devez d’abord disposer des éléments suivants :
>
>* Un compte Databricks actif
>* Votre hôte Workspace Databricks, [chemin d’accès de l’entrepôt de données SQL](https://docs.databricks.com/aws/en/compute/sql-warehouse/create){target="_blank"}, [Jeton d’accès personnel](https://learn.microsoft.com/en-us/azure/databricks/dev-tools/auth/pat){target="_blank"} et [Catalogues Unity](https://learn.microsoft.com/en-us/azure/databricks/discover/database-objects){target="_blank"} est pratique.

## Comment se connecter

1. Sur la page d’accueil [Collègue pour les équipes](https://coworker-campaigns.experience.adobe.com/){target="_blank"}, cliquez sur **Contexte** et sélectionnez **Connecteurs**.

   ![Volet de navigation de gauche Coworker for Teams avec le champ Contexte développé et les Connecteurs mis en surbrillance](./assets/databricks-1.png)

1. Cliquez sur **Ajouter une intégration**.

   ![Bouton Ajouter une intégration dans l’écran Connecteurs](./assets/databricks-2.png)

   >[!NOTE]
   >
   >S’il ne s’agit pas de votre première intégration, le bouton indique « Ajouter un connecteur ».

1. Sur la ligne Databricks, cliquez sur **Connexion**.

   ![Mosaïque du connecteur Databricks avec le bouton Connexion](./assets/databricks-3.png)

1. Saisissez votre hôte Workspace **&#x200B;**, **chemin d’accès de l’entrepôt de données SQL**, **Jeton d’accès personnel** et **Catalogues Unity**. Cliquez sur **Connecter**.

   >[!NOTE]
   >
   >Sur la page d’accueil de Databricks, l’hôte Workspace se trouve directement dans la barre d’adresse de votre navigateur. Pour localiser toutes les autres informations d’identification, consultez les liens dans **Conditions préalables** au début de cet article.

   ![Boîte de dialogue Connecter les briques de données avec les champs pour l’hôte Workspace, le chemin d’accès de l’entrepôt de données SQL, le jeton d’accès personnel et les catalogues Unity](./assets/databricks-4.png)

Après la connexion, les briques de données apparaissent dans la liste Connecteurs.

**Pour vous déconnecter :**

1. Dans l’écran Connecteurs, recherchez la mosaïque Briques de données et cliquez sur **Gérer**.

1. Cliquez sur **Déconnecter** (il n’est pas nécessaire de saisir à nouveau votre jeton d’accès personnel pour le moment).

1. Cliquez de nouveau sur **Déconnecter** pour confirmer.
