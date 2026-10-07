---
title: Outils Customer Journey Analytics dans la passerelle CX Coworker
description: Découvrez les outils Adobe Customer Journey Analytics disponibles via la passerelle Adobe CX Coworker.
hide: true
source-git-commit: 6c126810936bea3e883d74e6ff685991cb40cd4a
workflow-type: tm+mt
source-wordcount: '673'
ht-degree: 4%
---

# Outils Customer Journey Analytics dans la passerelle Adobe CX Coworker {#cja-mcp}

Utilisez les outils du produit Customer Journey Analytics pour explorer les vues de données, découvrir les dimensions et les mesures, exécuter des rapports et gérer les composants d’analyse sélectionnés à partir d’un client compatible avec MCP. Ces outils sont disponibles via la passerelle [&#128279;](overview.md) lorsque votre compte dispose de la licence et des autorisations Customer Journey Analytics requises.

>[!AVAILABILITY]
>
>Les outils de Customer Journey Analytics sont disponibles pour les clients disposant d’une licence Customer Journey Analytics. L’accès est contrôlé par l’autorisation **Accès MCP** dans Adobe Admin Console. Voir [Accès aux outils de la passerelle CX Coworker](access.md).

## Fonctionnalités principales {#mcp-capabilities}

Les outils Customer Journey Analytics prennent en charge les workflows d’analyse gouvernés de votre client MCP. Vous pouvez ainsi :

* Découvrez les vues de données et examinez leur configuration.
* Recherchez des dimensions, des mesures, des mesures calculées, des segments, des périodes, des audiences et des projets.
* Exécutez les rapports de classement et de tendance avec des dimensions, des mesures, des périodes et des filtres de segment.
* Examinez les définitions de composant et l’utilisation du composant.
* Créer ou mettre à jour les composants Analytics et les projets Workspace sélectionnés.

>[!IMPORTANT]
>
>Contrairement aux outils de produit en lecture seule [&#128279;](rtcdp-mcp.md), [Experience Platform](aep-mcp.md) et [Journey Optimizer](ajo-mcp.md), les outils de Customer Journey Analytics incluent des opérations d’écriture. Ils peuvent créer et mettre à jour des segments, des mesures calculées, des périodes, des projets et des audiences. Examinez et validez toutes les modifications initiées par MCP avant de vous y fier.

## Outils disponibles {#mcp-tools}

| Zone | Outil | Description |
| --- | --- | --- |
| Configuration et guides | `describeCja` | Renvoie des guides de référence pour les outils, les dimensions, les mesures, les segments, les mesures calculées et les structures de projet. |
| Configuration et guides | `setDefaultSessionDataViewId` | Configure la vue de données par défaut au niveau de la session pour les appels d’outil suivants. |
| Découverte | `findDimensions` | Localise les dimensions disponibles, avec prise en charge de la recherche sémantique. |
| Découverte | `findMetrics` | Découvre les mesures standard et personnalisées, à l’exclusion des mesures calculées. |
| Découverte | `findCalculatedMetrics` | Parcourt les mesures calculées créées et partagées par l’utilisateur. |
| Découverte | `findSegments` | Répertorie les segments accessibles à l’utilisateur actuel. |
| Découverte | `findDateRanges` | Récupère les composants de période enregistrés. |
| Découverte | `findDataViews` | Découvre les vues de données disponibles. |
| Découverte | `findProjects` | Localise les projets Workspace. |
| Découverte | `findAudiences` | Répertorie les composants d’audience disponibles. |
| Reporting et analyse | `runReport` | Exécute des rapports classés avec des dimensions, des mesures, des périodes et des filtres de segment facultatifs. |
| Reporting et analyse | `searchDimensionItems` | Récupère les valeurs de dimension nécessaires pour les rapports de répartition. |
| Détails du composant | `describeDimension` | Affiche les métadonnées détaillées d’une dimension spécifique. |
| Détails du composant | `describeMetric` | Renvoie les métadonnées et les détails des mesures. |
| Détails du composant | `describeSegment` | Affiche les informations de définition et de compatibilité d’un segment. |
| Détails du composant | `describeCalculatedMetric` | Affiche la formule et les mesures de base utilisées. |
| Détails du composant | `describeProject` | Détails de la configuration d’un projet Workspace. |
| Détails du composant | `describeAudience` | Renvoie les métadonnées d’audience et le statut de publication. |
| Utilisation des composants | `listComponentUsage` | Classe les composants par fréquence d’utilisation. |
| Utilisation des composants | `listFrequentlyUsedWith` | Identifie les composants généralement associés. |
| Utilisation des composants | `listSimilarTo` | Recherche d’autres composants à des fins similaires. |
| Créer et mettre à jour | `upsertSegment` | Crée un segment ou en modifie un existant. |
| Créer et mettre à jour | `upsertCalculatedMetric` | Crée une mesure calculée ou modifie une mesure existante. |
| Créer et mettre à jour | `createDateRange` | Crée un composant de période réutilisable. |
| Créer et mettre à jour | `upsertProject` | Crée un projet d’espace de travail ou en modifie un existant. |
| Créer et mettre à jour | `upsertAudience` | Crée une définition d’audience ou en modifie une existante. |

## Exemples de prompts {#mcp-use-cases}

| Objectif | Exemple de prompt |
| --- | --- |
| Liste des vues de données | « Répertorier les vues de données disponibles dans Customer Journey Analytics. » |
| Découvrir les composants | « Recherche de mesures liées au chiffre d’affaires dans la vue de données `[data view name]`. » |
| Exécution d’un rapport | « Exécute un état de tendance des commandes par mois pour le dernier trimestre. » |
| Répartition d’une mesure | « Afficher les 10 principaux canaux marketing par visite, ventilés par type d’appareil. » |
| Inspection d’un composant | « Décrivez le `[segment name]` de segment et affichez-moi sa définition. » |
| Utilisation de l’audit | « Quelles dimensions sont utilisées le plus souvent dans mes projets ? » |
| Création d’un segment | « Créez un segment pour les utilisateurs qui ont consulté la page de tarification au cours des 30 derniers jours. » |

## Contexte et autorisations du produit {#mcp-context}

Votre compte doit appartenir à un profil de produit Customer Journey Analytics qui inclut l’élément d’autorisation **Accès MCP** accordé par un administrateur système ou produit dans Adobe Admin Console.

Les autorisations de produit s’appliquent toujours. Votre compte doit être en mesure d’afficher les vues de données, les composants, les projets et les audiences que vous interrogez, et doit disposer des autorisations de produit appropriées pour les opérations d’écriture, telles que la création ou la mise à jour de segments, de mesures calculées, de périodes, de projets ou d’audiences.

## Regardez-le en action {#mcp-videos}

**Vue d’ensemble**

>[!VIDEO](https://video.tv.adobe.com/v/3486313/?learn=on&enablevpops)

**En action**

>[!VIDEO](https://video.tv.adobe.com/v/3486314/?learn=on&enablevpops)

## Informations supplémentaires {#mcp-more}

Pour consulter la référence complète de l’outil et le guide de prise en main, consultez la [documentation du MCP &#x200B;](https://developer.adobe.com/analytics-mcp/docs/cja/){target="_blank"}.