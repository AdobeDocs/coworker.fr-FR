---
description: Coworker for Teams vous permet de connecter votre compte Shopify pour extraire des clients et des segments.
title: Se connecter à Shopify
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: Coworker
source-git-commit: 312450e09d9252f17cb2b5d471ee33e1a22b9a05
workflow-type: tm+mt
source-wordcount: '241'
ht-degree: 0%
---
# Se connecter à Shopify {#shopify}

Coworker for Teams vous permet de connecter votre compte Shopify pour extraire des clients et des segments.

>[!PREREQUISITES]
>
>Pour utiliser ce connecteur, vous devez d’abord disposer des éléments suivants :
>
>* Un compte Shopify actif
>* L’autorisation suivante dans Shopify : `read_customers`
>* L’URL de votre boutique Shopify et le jeton d’accès [API d’administration](https://shopify.dev/docs/apps/build/authentication-authorization){target="_blank"} sont pratiques

## Comment se connecter

1. Sur la page d’accueil [Collègue pour les équipes](https://coworker-campaigns.experience.adobe.com/){target="_blank"}, cliquez sur **Contexte** et sélectionnez **Connecteurs**.

   ![Volet de navigation de gauche Coworker for Teams avec le champ Contexte développé et les Connecteurs mis en surbrillance](./assets/shopify-1.png)

1. Cliquez sur **Ajouter une intégration**.

   ![Bouton Ajouter une intégration dans l’écran Connecteurs](./assets/shopify-2.png)

   >[!NOTE]
   >
   >S’il ne s’agit pas de votre première intégration, le bouton indique « Ajouter un connecteur ».

1. Dans la ligne Shopify, cliquez sur **Connecter**.

   ![Vignette du connecteur Shopify avec le bouton Se connecter](./assets/shopify-3.png)

1. Vérifiez l’autorisation requise, puis cliquez sur **Continuer**.

   ![Écran de révision des autorisations requises Shopify avec le bouton Continuer](./assets/shopify-4.png)

1. Saisissez votre **URL de magasin** Shopify et **Jeton d’accès de l’API d’administration**. Cliquez sur **Connecter**.

>[!NOTE]
>
>Dans Shopify, obtenez votre jeton d’accès à l’API d’administration via **Paramètres** › **Applications** › **Développement d’applications** › **Création d’une application personnalisée héritée** › **Configuration de l’API d’administration** › **Ajout des portées requises**.

![Boîte de dialogue Connecter Shopify aux champs pour URL de magasin et Jeton d’accès de l’API d’administration](./assets/shopify-5.png)

Après la connexion, Shopify apparaît dans la liste Connecteurs .

**Pour vous déconnecter :**

1. Dans l’écran Connecteurs, recherchez la mosaïque Shopify et cliquez sur **Gérer**.

1. Cliquez sur **Déconnecter** (il n’est pas nécessaire de saisir à nouveau votre jeton d’accès à l’API d’administration pour le moment).

1. Cliquez de nouveau sur **Déconnecter** pour confirmer.
