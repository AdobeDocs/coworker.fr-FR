---
description: Découvrez comment connecter votre compte Marketo Engage à des campagnes collègues afin de synchroniser les listes dynamiques et statiques Marketo.
title: Connexion à Marketo Engage
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
feature_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: dbee38135a5491fd21b65fdbb70ba60d949d7560
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 0%
---
# Connexion à Marketo Engage {#marketo}

Les campagnes Adobe Coworker vous permettent de connecter votre compte Marketo Engage pour extraire des listes dynamiques et statiques.

>[!PREREQUISITES]
>
>Pour utiliser ce connecteur, vous devez d’abord disposer des éléments suivants :
>
>* Un compte Marketo Engage actif
>* Votre Marketo **URL d’instance**
>* Un [service personnalisé](https://experienceleague.adobe.com/en/docs/marketo-developer/marketo/rest/custom-services#custom-services-1) créé pour les campagnes de collègues dans Marketo, avec son [identifiant client et secret client](https://experienceleague.adobe.com/en/docs/marketo-developer/marketo/rest/authentication#creating-an-access-token) disponible

## Comment se connecter

1. Sur la [page d’accueil des campagnes de collègues](https://coworker-campaigns.experience.adobe.com/), cliquez sur **Personnaliser** et sélectionnez **Connecteurs**.

   ![Volet de navigation de gauche des campagnes des collègues avec Personnaliser développé et Connecteurs mis en surbrillance](./assets/marketo-1.png)

1. Cliquez sur **Ajouter une intégration**.

   ![Bouton Ajouter une intégration dans l’écran Connecteurs](./assets/marketo-2.png)

   >[!NOTE]
   >
   >S’il ne s’agit pas de votre première intégration, le bouton indique « Ajouter un connecteur ».

1. Dans la ligne Marketo, cliquez sur **Connexion**.

   ![Vignette du connecteur Marketo avec le bouton Connexion](./assets/marketo-3.png)

1. Saisissez votre Marketo **URL de l’instance**, **ID client** et **Secret client**. Cliquez sur **Connecter**.

   >[!NOTE]
   >
   >Vous trouverez l’URL de votre instance Marketo dans la barre d’adresse de votre navigateur lors de l’affichage de votre page My Marketo.

   ![Boîte de dialogue Connecter Marketo à l’aide de champs tels que l’URL, l’ID client et le secret client](./assets/marketo-4.png)

Après la connexion, Marketo apparaît dans la liste Connecteurs et peut être sélectionné lors de la liaison d’une liste de contacts à synchroniser à partir de Marketo.

**Pour vous déconnecter :**

1. Dans l’écran Connecteurs, recherchez la mosaïque Marketo et cliquez sur **Gérer**.

   ![Écran Connecteurs avec la mosaïque Marketo affichant un statut Connecté et le bouton Gérer](./assets/marketo-5.png)

1. Cliquez sur **Déconnecter** (il n’est pas nécessaire de saisir à nouveau votre secret client pour le moment).

   ![Boîte de dialogue Gérer Marketo avec les champs URL de l’instance et ID du client et un bouton Déconnecter](./assets/marketo-6.png)

   >[!NOTE]
   >
   >Une fois l’URL d’instance ajoutée pour la première fois, elle est définie par défaut sur l’URL du point d’entrée REST, se terminant par `*.mktorest.com`.

1. Cliquez de nouveau sur **Déconnecter** pour confirmer.

   ![Boîte de dialogue de confirmation de déconnexion](./assets/marketo-7.png)
