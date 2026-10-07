---
title: Outils Adobe Analytics dans la passerelle CX Coworker
description: Découvrez les outils Adobe Analytics disponibles via la passerelle Adobe CX Coworker.
hide: true
source-git-commit: 6c126810936bea3e883d74e6ff685991cb40cd4a
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 5%
---
# Outils Adobe Analytics dans la passerelle Adobe CX Coworker {#aa-mcp}

Vous pouvez utiliser les outils Adobe Analytics pour explorer les suites de rapports, découvrir les dimensions et les mesures, exécuter des rapports et gérer les composants d’analyse sélectionnés à partir d’un client compatible avec MCP. Ces outils sont disponibles via la passerelle Adobe CX Coworker [unifiée](overview.md) lorsque votre compte dispose de la licence et des autorisations Adobe Analytics requises.

>[!AVAILABILITY]
>
>Les outils Analytics sont disponibles pour les clients disposant d’une licence Adobe Analytics. L’accès est contrôlé par l’autorisation **Accès MCP** dans Adobe Admin Console. Lisez le [Accéder aux outils de passerelle CX Coworker](access.md) pour plus d’informations.

## Fonctionnalités principales {#mcp-capabilities}

Les outils Adobe Analytics prennent en charge les workflows de découverte et de création de rapports d’analyse de votre client MCP. Vous pouvez ainsi :

- Découvrez les suites de rapports et examinez leur configuration.
- Rechercher des dimensions, des mesures, des mesures calculées, des segments, des périodes et des projets d’espace de travail.
- Exécutez les rapports de classement et de tendance avec des dimensions, des mesures, des périodes et des filtres de segment.
- Créer et mettre à jour les composants réutilisables sélectionnés, tels que les segments et les périodes.
- Générez des informations à partir des données Adobe Analytics à l’aide du langage naturel.

>[!IMPORTANT]
>
>Certains outils Adobe Analytics peuvent créer ou mettre à jour des composants d’analyse. Examinez et validez toutes les modifications initiées par MCP avant de vous y fier.

## Couverture de l’outil {#mcp-tools}

| Zone | Ce que vous pouvez faire |
| --- | --- |
| Suites de rapports | Découvrez les suites de rapports disponibles pour votre compte et examinez les détails de la configuration. |
| Composants | Recherchez et décrivez les dimensions, mesures, mesures calculées, segments et périodes. |
| Création de rapports | Exécutez les rapports de classement et de tendances à l’aide des dimensions, mesures, périodes et filtres de segment sélectionnés. |
| Segments et périodes | Créez et mettez à jour des segments et des périodes réutilisables là où les autorisations de votre produit le permettent. |
| Projets Workspace | Découvrez et décrivez les projets Analysis Workspace. |

Pour obtenir la liste complète et actuelle des outils, consultez la référence [Outil Adobe Analytics MCP](https://developer.adobe.com/analytics-mcp/docs/aa/reference){target="_blank"}.

## Exemples de prompts {#mcp-use-cases}

| Objectif | Exemple de prompt |
| --- | --- |
| Découverte de suites de rapports | « Répertorier les suites de rapports auxquelles je peux accéder. » |
| Rechercher des composants | « Rechercher des mesures liées au chiffre d’affaires. » |
| Exécution d’un rapport | « Exécute un rapport avec classement des pages vues par page pour les 7 derniers jours. » |
| Inspection d’un segment | « Décrivez le `[segment name]` de segment et affichez-moi sa définition. » |
| Explorer les projets | « Répertorier mes projets Analysis Workspace liés à l’acquisition. » |

## Contexte et autorisations du produit {#mcp-context}

Votre compte doit appartenir à un profil de produit Adobe Analytics qui inclut l’élément d’autorisation **Accès MCP** accordé par un administrateur système ou de produit dans Adobe Admin Console.

Les autorisations de produit s’appliquent toujours. Votre compte doit pouvoir afficher les suites de rapports, les composants, les rapports et les projets que vous interrogez, et doit disposer des autorisations de produit appropriées pour les opérations d’écriture, telles que la création ou la mise à jour de composants réutilisables.

## Informations supplémentaires {#mcp-more}

Pour consulter la référence complète de l’outil et le guide de prise en main, consultez la [documentation Adobe Analytics MCP](https://developer.adobe.com/analytics-mcp/docs/aa/){target="_blank"}.