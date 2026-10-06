---
description: Connectez votre compte HubSpot aux campagnes Collègues à l’aide d’une clé de service pour synchroniser les listes de contacts, puis gérez ou déconnectez l’intégration à tout moment.
title: Se connecter à HubSpot
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
feature_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: dbee38135a5491fd21b65fdbb70ba60d949d7560
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 0%
---
# Se connecter à HubSpot {#hubspot}

Les campagnes Adobe Coworker vous permettent de connecter votre compte HubSpot pour extraire des listes de contacts.

>[!PREREQUISITES]
>
>Pour utiliser ce connecteur, vous devez d’abord disposer des éléments suivants :
>
>* Un compte HubSpot actif
>* Une [clé de service](https://developers.hubspot.com/docs/apps/developer-platform/build-apps/authentication/account-service-keys#create-a-service-key) créée avec les portées suivantes ajoutées : `crm.objects.contacts.read`, `crm.objects.leads.read`, `crm.schemas.contacts.read`, `crm.lists.read`, `crm.export`

## Comment se connecter

1. Sur la [page d’accueil des campagnes de collègues](https://coworker-campaigns.experience.adobe.com/), cliquez sur **Personnaliser** et sélectionnez **Connecteurs**.

   ![Menu Personnaliser développé dans la barre latérale avec l’option Connecteurs sélectionnée](./assets/hubspot-1.png)

1. Cliquez sur **Ajouter une intégration**.

   ![Bouton Ajouter une intégration sur l’écran Connecteurs](./assets/hubspot-2.png)

   >[!NOTE]
   >
   >S’il ne s’agit pas de votre première intégration, le bouton indique « Ajouter un connecteur ».

1. Dans la ligne HubSpot, cliquez sur **Connecter**.

   ![Mosaïque HubSpot avec le bouton Se connecter en surbrillance](./assets/hubspot-3.png)

1. Une boîte de dialogue modale s’affiche avec les autorisations nécessaires (répertoriées dans la section Conditions préalables au début de cet article). Cliquez sur **Continuer**.

1. Saisissez votre HubSpot **clé de service**, puis cliquez sur **Connecter**.

   ![Boîte de dialogue Connect HubSpot avec le champ Clé de service et le bouton Connect](./assets/hubspot-4.png)

Après la connexion, HubSpot apparaît dans la liste Connecteurs et peut être sélectionné lors de la liaison d’une liste de contacts à synchroniser à partir de HubSpot.

**Pour vous déconnecter :**

1. Dans l’écran Connecteurs, recherchez la mosaïque HubSpot et cliquez sur **Gérer**.

   ![Écran Connecteurs affichant HubSpot connecté avec le bouton Gérer en surbrillance](./assets/hubspot-5.png)

1. Cliquez sur **Déconnecter** (il n’est pas nécessaire de saisir à nouveau votre clé de service pour le moment).

   ![Boîte de dialogue Gérer HubSpot avec le bouton Déconnecter en surbrillance](./assets/hubspot-6.png)

1. Cliquez de nouveau sur **Déconnecter** pour confirmer.

   ![Boîte de dialogue de confirmation de déconnexion avec le bouton Déconnecter en surbrillance](./assets/hubspot-7.png)
