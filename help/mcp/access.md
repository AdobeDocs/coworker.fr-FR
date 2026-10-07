---
title: Accès aux outils de la passerelle CX Coworker
description: Vérifiez la disponibilité du produit, l’activation de l’organisation et les autorisations avant d’utiliser les outils de la passerelle CX Coworker d’Adobe.
hide: true
source-git-commit: 6c126810936bea3e883d74e6ff685991cb40cd4a
workflow-type: tm+mt
source-wordcount: '584'
ht-degree: 4%
---
# Accès aux outils de la passerelle CX Coworker {#mcp-access}

Adobe CX Enterprise expose les outils de produit par le biais d’un MCP unique. L’accès est évalué par les outils de produit : votre organisation Adobe doit être activée pour les outils de produit appropriés, et votre compte utilisateur doit disposer des autorisations de produit requises pour afficher ou modifier les données de produit exposées par ces outils.

>[!IMPORTANT]
>
>Votre organisation Adobe doit être activée avant de pouvoir utiliser les outils de la passerelle CX Coworker. Si votre organisation n’y a pas encore accès, contactez l’équipe chargée de votre compte Adobe pour demander l’activation de votre organisation.

## Exigences d’accès {#mcp-requirements}


| Outils de produit | Disponibilité | Exigences d’accès |
| --- | --- | --- |
| Real-Time CDP | Beta | Licence Real-Time CDP active, activation de Beta pour votre organisation Adobe et autorisations d’affichage des audiences, des destinations, des sources, des identités et des ressources d’activation que vous interrogez. |
| Experience Platform | Beta | Licence Experience Platform active, activation de Beta pour votre organisation Adobe et autorisations d’affichage des schémas, des jeux de données, de la gouvernance, de Query Service, de l’audit et des ressources de sandbox que vous interrogez. |
| Journey Optimizer | Beta | Licence Journey Optimizer active, activation de Beta pour votre organisation Adobe et autorisations d’affichage des campagnes, des parcours et des configurations de canal. |
| Customer Journey Analytics | Disponible | Licence Customer Journey Analytics active et profil de produit comprenant l’élément d’autorisation **Accès MCP** dans Adobe Admin Console. Les autorisations de produit gouvernent toujours les vues de données, les composants, les rapports, les projets et les audiences auxquels vous pouvez accéder ou que vous pouvez modifier. |
| Adobe Analytics | Disponible | Licence Adobe Analytics active et profil de produit incluant l’élément d’autorisation **Accès MCP** dans Adobe Admin Console. Les autorisations de produit gouvernent toujours les suites de rapports, les composants, les rapports, les segments, les périodes et les projets auxquels vous pouvez accéder ou que vous pouvez modifier. |
| Workfront | Prévisualisation | Licence Workfront active et activation de Workfront MCP. Voir la documentation sur le MCP de Workfront [&#128279;](https://experienceleague.adobe.com/en/docs/workfront/using/basics/workfront-mcp-server/workfront-mcp-server-overview). |
| Cible | Beta | Licence Target active associée à une organisation Adobe Experience Platform. Voir la [documentation de Target MCP](https://experienceleague.adobe.com/en/docs/target/using/mcp/target-mcp-get-started). |



>[!NOTE]
>
>Le MCP affiche uniquement les outils que votre organisation et vos informations d’identification sont autorisées à utiliser. Si un outil de produit est manquant après votre connexion, confirmez les licences de produit, l’activation de l’organisation et les autorisations utilisateur.

## Demander l’accès {#mcp-request}

Pour les outils de produit Beta ou à version limitée, contactez votre représentant de compte Adobe et indiquez les outils de produit Adobe for CX Coworker Gateway que vous souhaitez utiliser. Votre représentant peut coordonner l’activation du produit et confirmer que votre organisation Adobe est prête.

Pour les outils de produit généralement disponibles qui utilisent l’élément d’autorisation **Accès MCP**, demandez à un administrateur système ou produit d’ajouter votre compte à un profil de produit qui inclut l’accès MCP.

## Activation intégrée au produit {#mcp-product-enablement}

Certains produits nécessitent une activation intégrée au produit ou des autorisations spécifiques au produit en plus de l’accès MCP. Par exemple :

- Adobe Analytics et Customer Journey Analytics nécessitent l’élément d’autorisation **Accès MCP** dans Adobe Admin Console.
- Les outils Workfront MCP sont activés à partir des paramètres de Workfront.
- Les outils de produit Beta nécessitent l’activation de l’organisation Adobe avant que leurs outils n’apparaissent via le MCP.

Consultez la page produit pour connaître l’outil de produit que vous prévoyez d’utiliser pour les autorisations, les exigences contextuelles et les limitations spécifiques aux produits.

## Avant l’installation {#mcp-prerequisites}

Avant de connecter votre client MCP, vérifiez les points suivants :

- Votre organisation Adobe est activée pour les outils de produit dont vous avez besoin.
- Votre compte utilisateur dispose des autorisations de produit requises pour les données et opérations que vous prévoyez d’utiliser.
- Vous avez accès à un client MCP pris en charge, tel que [!DNL Claude], [!DNL ChatGPT], [!DNL Cursor], [!DNL Claude Code], [!DNL Codex] ou [!DNL VS Code].
- Pour l’installation d’entreprise, vous ou un collègue pouvez gérer les connecteurs ou les applications personnalisées dans les paramètres d’organisation de votre client MCP.

Suite : [Installation de la passerelle CX Coworker Adobe](install.md).