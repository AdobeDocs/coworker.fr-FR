---
title: Contrôle d’accès pour un collègue
description: Découvrez le contrôle d’accès pour Adobe CX Enterprise Coworker et les autorisations dans les produits Adobe compatibles. Recherchez des contrôles administrateur et obtenez de l’aide sur l’accès.
last-substantial-update: 2026-11-04
level: beginner
role: Admin
jira: KT-22980
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: Coworker
source-git-commit: 756748b585685de6cd0544a46014bc44a4cddc63
workflow-type: tm+mt
source-wordcount: '520'
ht-degree: 0%
---
# Contrôle d’accès pour Coworker {#access-control}

Utilisez le contrôle d’accès Adobe CX Enterprise Coworker pour gérer qui peut utiliser Coworker et quelles fonctionnalités ils peuvent utiliser.

>[!NOTE]
>
>Le contrôle d’accès est progressivement déployé auprès de tous les clients ayant un accès de collègue. Il se peut que le contrôle d’accès [!UICONTROL 1&rbrace; ne soit pas encore visible dans votre organisation. &#x200B;]Pour plus d&#39;informations, consultez l&#39;aperçu de la discussion avec un collègue [1&rbrace;.](/help/chat/overview.md)

## Comment l’accès est déterminé {#how-access-is-determined}

L’accès des collaborateurs est contrôlé par un paramètre à l’échelle de l’organisation et des remplacements facultatifs d’utilisateurs ou de groupes. Le paramètre à l’échelle de l’organisation active ou désactive l’accès Collègue pour les utilisateurs de votre entreprise. Par défaut, l’accès est activé pour tout le monde.

| Paramètre | Impact sur l’accès |
| --- | --- |
| Paramètre à l’échelle de l’organisation | Activez l’accès collaborateur pour tout le monde ou désactivez-le pour votre entreprise. |
| Remplacement d’utilisateur ou de groupe d’utilisateurs | Les remplacements permettent aux administrateurs de contrôler l’accès des collaborateurs pour des utilisateurs ou groupes d’utilisateurs spécifiques. |
| Autorisations d’application compatibles | Les contrôles d’accès des collaborateurs déterminent si vous pouvez accéder à des fonctionnalités des collaborateurs généralement disponibles. Coworker hérite de vos autorisations utilisateur des applications CX Enterprise compatibles avec Coworker et respecte les autorisations que chaque application applique déjà. |


## Administrateurs de collègues {#add-coworker-admins}

Un administrateur de collègues est un utilisateur affecté en tant qu’**[!UICONTROL administrateur système]** pour l’organisation ou en tant qu’**[!UICONTROL administrateur de produit]** sur [!DNL Adobe Experience Platform] dans [!DNL Adobe Admin Console].

## Gérer l’accès utilisateur {#manage-user-access}

1. Ouvrez l’expérience Collègue . Pour obtenir des instructions, voir [Connexion à un collègue](/help/chat/ui-guide.md#sign-in).
2. Ouvrez le menu du profil et sélectionnez **[!UICONTROL Paramètres d’administration]**.

   ![Page de départ Collègue avec le contrôle du menu de profil mis en surbrillance.](./assets/access-control/coworker-home.png)

   ![Menu de profil de collègue avec paramètres d&#39;administration mis en surbrillance.](./assets/access-control/admin-settings.png)

3. Sélectionnez **[!UICONTROL Contrôle d’accès]**.

   ![Paramètres d’administration avec la carte Contrôle d’accès mise en surbrillance.](./assets/access-control/access-control.png)

   Utilisez cette vidéo pour apprendre à gérer les utilisateurs de Coworker.

   >[!VIDEO](https://video.tv.adobe.com/v/3507151?learn=on){transcript=true}

4. Dans Coworker, utilisez **[!UICONTROL Utilisateurs]** pour gérer l’accès pour les individus, ou **[!UICONTROL Groupes d’utilisateurs]** pour gérer l’accès Coworker pour les groupes d’utilisateurs. Un paramètre de groupe d’utilisateurs s’applique à ses membres.

   Les groupes d’utilisateurs de collègues sont distincts des groupes [!DNL Adobe Admin Console]. La synchronisation des groupes d&#39;utilisateurs de [!DNL Adobe Admin Console] avec un collègue sera bientôt disponible.

   La liste des utilisateurs inclut des utilisateurs de votre organisation. L’accès collaborateur est activé par défaut pour ces utilisateurs.

   * **Activé :** L&#39;utilisateur ou le groupe d&#39;utilisateurs est actif.
   * **Désactivé :** l&#39;utilisateur ou le groupe d&#39;utilisateurs est inactif.

   Lorsque l’accès pour tous est désactivé, activez **[!UICONTROL Autoriser les remplacements]** et sélectionnez **[!UICONTROL Ajouter un remplacement]** pour ajouter des utilisateurs ou des groupes qui doivent toujours avoir accès.

## Autorisations dans les applications CX Enterprise compatibles avec Coworker {#permissions-in-compatible-applications}

Les applications CX Enterprise compatibles avec les collaborateurs continuent d’appliquer leurs propres autorisations.

Coworker respecte les autorisations dans les applications compatibles. Par exemple, si vous ne pouvez pas accéder à un jeu de données dans [!DNL Adobe Experience Platform], Coworker ne peut pas récupérer ce jeu de données ni agir sur celui-ci pour vous.

## Obtenir de l’aide sur l’accès {#get-help-with-access}

Si vous ne voyez pas [!UICONTROL Contrôle d’accès], contactez votre administrateur Adobe ou votre représentant Adobe. Ils peuvent confirmer si la fonctionnalité est activée pour votre organisation et si vous avez accès à ses paramètres.

Si l’accès vous est refusé, demandez à votre administrateur de vérifier les paramètres par défaut à l’échelle de l’organisation ainsi que les paramètres des utilisateurs, des utilisatrices et des groupes. Dans le cas d’une application CX Enterprise compatible avec Coworker, demandez-lui de vérifier les autorisations gérées séparément pour cette application.

## Plus d’aide sur cette rubrique {#more-help}

Utilisez ces ressources pour plus d’informations sur Coworker et l’administration.

* [Présentation de la conversation avec un collègue](/help/chat/overview.md)
* [Prise en main du chat des collègues](/help/chat/ui-guide.md)
* [Gestion des plug-ins et des places de marché](/help/customizations/plugins/manage-plugins-for-your-org.md)
