---
title: Outils de contexte de session dans la passerelle CX Coworker
description: Découvrez les outils principaux qui définissent le contexte de l’organisation, du sandbox et de la vue de données pour tous les appels à l’outil Passerelle CX Coworker.
hide: true
source-git-commit: 6c126810936bea3e883d74e6ff685991cb40cd4a
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 1%
---
# Outils de contexte de session dans la passerelle CX Coworker Adobe {#mcp-core}

La passerelle CX Coworker Adobe comprend un ensemble d’outils de contexte de session qui définissent l’organisation Adobe, le sandbox Adobe Experience Platform et la vue de données Customer Journey Analytics dans laquelle tous les autres outils de produit fonctionnent. Aucune licence ou activation supplémentaire n&#39;est requise ; ces outils sont disponibles pour chaque utilisateur authentifié après la connexion au serveur de passerelle [&#128279;](overview.md).

## Fonctionnement du contexte {#mcp-core-how}

La passerelle CX Coworker couvre chaque appel d’outil auprès d’une organisation Adobe active. En outre, les exigences de contexte dépendent du produit :

- **produits basés sur Experience Platform** — les outils [Real-Time CDP](rtcdp-mcp.md), [Experience Platform](aep-mcp.md) et [Journey Optimizer](ajo-mcp.md) fonctionnent dans un sandbox Experience Platform. Définissez le sandbox une fois par session avec `core-set_sandbox` ; les trois le partagent.
- **Autres produits** — Les produits non créés sur Experience Platform n’utilisent pas le contexte sandbox. Par exemple, les outils [&#128279;](cja-mcp.md) sont résolus par rapport à une vue de données et les outils [Adobe Analytics](analytics-mcp.md) sont résolus par rapport aux suites de rapports.

Définition du contexte une fois au début d’une session : les outils de produit individuels ne changent pas d’organisation, de sandbox ou de vues de données en milieu de session.

## Outils disponibles {#mcp-core-tools}

| Outil | Description |
| --- | --- |
| `core-list_orgs` | Répertorie les organisations Adobe accessibles à l’utilisateur authentifié. Renvoie le nom d’affichage et l’identifiant de `@AdobeOrg` de chaque organisation. Utilisez ceci pour rechercher l’ID d’organisation avant d’appeler `core-switch_org`. |
| `core-switch_org` | Définit l’organisation Adobe active pour la session. Tous les appels d’outils suivants sont inclus dans cette organisation jusqu’à la fin de la session ou jusqu’à ce que l’organisation soit de nouveau changée. |
| `core-list_sandboxes` | Répertorie les sandbox Experience Platform disponibles dans l’organisation principale. Renvoie le nom, le titre, le type (production ou développement) et l’état de chaque sandbox. Utilisez ceci pour rechercher un nom de sandbox avant d’appeler `core-set_sandbox`. |
| `core-set_sandbox` | Définit le sandbox Experience Platform actif pour la session. Les outils Real-Time CDP, Experience Platform et Journey Optimizer étendent leurs données à ce sandbox. |
| `core-list_dataviews` | Répertorie les vues de données Customer Journey Analytics disponibles pour l’utilisateur authentifié dans le contexte actuel. Renvoie les identifiants des vues de données et les noms d’affichage. Utilisez ceci pour rechercher une vue de données avant d’appeler `core-set_dataview`. |
| `core-set_dataview` | Définit la vue de données Customer Journey Analytics par défaut pour la session. Lorsqu’elle est définie, les outils CJA qui nécessitent une vue de données, tels que `findDimensions`, `findMetrics` et `runReport`, utilisent automatiquement cette valeur, sauf si une autre vue de données est spécifiée dans l’appel d’outil individuel. |

## Configuration de session standard {#mcp-core-setup}

Définissez le contexte au début d’une session avant d’appeler les outils du produit :

1. **Organisation** — Appelez `core-list_orgs` pour répertorier vos organisations accessibles, puis `core-switch_org` avec l’ID d’organisation cible.
2. **Sandbox** — Si vous prévoyez d’utiliser les outils Real-Time CDP, Experience Platform ou Journey Optimizer, appelez `core-list_sandboxes` pour répertorier les sandbox disponibles, puis `core-set_sandbox` avec le nom du sandbox cible.
3. **Vue de données** (CJA uniquement) : si vous prévoyez d’utiliser les outils Customer Journey Analytics, appelez `core-list_dataviews` pour répertorier les vues de données disponibles, puis `core-set_dataview` la vue de données de votre choix.

Vous pouvez demander à votre client MCP de terminer cette configuration dans une seule requête en langage naturel :

> « Utilisez des `1234ABCD@AdobeOrg` d’organisation, des `prod` de sandbox et des `My Company — Global` de vue de données pour cette session. »

Le client appelle les outils appropriés et confirme une fois le contexte défini.

>[!TIP]
>
>Si vos informations d’identification Adobe appartiennent à une seule organisation, `core-list_orgs` et `core-switch_org` fonctionnent toujours, mais l’organisation effective sera la même quoi qu’il arrive. Vous devez encore appeler `core-set_sandbox` si vous prévoyez d’utiliser les outils Real-Time CDP, Experience Platform ou Journey Optimizer, et `core-set_dataview` si vous prévoyez d’utiliser les outils Customer Journey Analytics.

## Exemples de prompts {#mcp-core-examples}

| Objectif | Exemple de prompt |
| --- | --- |
| Découvrir les organisations disponibles | « À quelles organisations Adobe ai-je accès ? » |
| Définir le contexte de l’organisation | « Basculer vers le `My Org (1234ABCD@AdobeOrg)` d’organisation. » |
| Découvrir les sandbox disponibles | « Répertorier les sandbox disponibles dans mon organisation actuelle. » |
| Définir le contexte du sandbox | « Utilisez le sandbox `prod` pour cette session. » |
| Découvrir les vues de données disponibles | « À quelles vues de données Customer Journey Analytics puis-je accéder ? » |
| Définir le contexte de la vue de données | « Définissez `My Company — Global` comme vue de données par défaut. » |
| Configuration complète de la session | « Configurez une session à l’aide des `1234ABCD@AdobeOrg` d’organisation, des `prod` de sandbox et des `My Company — Global` de vue de données. » |

## Pages associées {#mcp-core-related}

- [Installation de la passerelle Adobe CX Coworker](install.md) — Découvrez comment connecter votre client MCP, y compris la section de configuration du contexte du produit.
- [Accéder aux outils de la passerelle CX Coworker](access.md) — Conditions d’accès par produit.