---
title: Comparer les audiences et les segments de clients avec la conversation des collègues
description: Utilisez le Module de conversation des collègues pour comparer des groupes de clients, trouver des opportunités de croissance négligées, suivre les tendances d’audience et transformer les informations en audiences que vous pouvez créer.
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: Coworker
source-git-commit: 1ec3a8bf6dff44df068529cf1f7ceb699a027d65
workflow-type: tm+mt
source-wordcount: '662'
ht-degree: 2%
---

# Présentation de l’analyse des audiences et des segments

<!-- FLAG: Confidence: High for the first sentence and "Best for" (carried over from analytics-overview.md). Medium for the second sentence, which summarizes the row descriptions. -->

Utilisez le Module de conversation Adobe CX Enterprise Coworker pour savoir quels groupes de clients se comportent différemment et comment, afin que vous puissiez vous concentrer sur ceux qui comptent le plus. Comparez les canaux, les périodes et les segments côte à côte, suivez l’évolution des audiences au fil du temps et transformez ce que vous trouvez en une audience que vous pouvez créer.

L’analyse des audiences et des segments est l’un des nombreux domaines d’analyse dans le chat des collègues. Pour afficher tous les domaines, voir [Commencer à analyser dans le chat des collègues](/help/chat/use-cases/data-insights/analytics-overview.md#start-analyzing-in-coworker-chat) dans Analyser les données avec le chat des collègues.

**Idéal pour :** Analyste, Utilisateur professionnel

## Conditions préalables

<!-- FLAG: Confidence: High for the shared bullets (sourced from the Skills and limitations table and analytics-chat.md). Medium for the "Additional prerequisite" notes on the operational trends rows in the Use cases table: workflows.md lists the operational time-series skill as available for "All Eligible Applications" but doesn't state required permissions. Mapping Track audience size trends to the same requirement is inferred. Low for the "Additional prerequisite" note on the Take an insight into an audience row: inferred from the Audiences section of workflows.md, which lists Real-Time CDP as the application for audience creation. Confirm with the PM. -->

Pour utiliser les cas pratiques de cette page, vous avez besoin des éléments suivants :

* La conversation avec un collègue est connectée à vos vues de données Customer Journey Analytics ou suites de rapports Adobe Analytics. Voir [Commencer à analyser les données avec la discussion entre collègues](/help/chat/use-cases/data-insights/analytics-chat.md).
* Accès en affichage aux vues de données ou aux suites de rapports à analyser. La discussion avec les collègues hérite de vos autorisations de Customer Journey Analytics ou d’Adobe Analytics.

## Cas d’utilisation

| Cas d’utilisation | Fonction |
| --- | --- |
| [Comparer les performances](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations) | Comparez les mesures entre les canaux, les périodes ou les segments côte à côte.<p>**Exemple d’invite :** « Comparer les recettes par canal, mois après mois »</p><p>Pour plus d’informations, voir [Compétences et limitations](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations).</p> |
| [Comparer des groupes de clients](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations) | Indique quels groupes se comportent différemment, sans qu’il soit nécessaire d’écrire une logique de segment.<p>**Idéal pour :** utilisateur professionnel</p><p>**Exemples d’invites :**</p><ul><li>« Les visiteurs sur les réseaux sociaux payants convertissent-ils différemment des e-mails ? »</li><li>« Comparer les nouveaux visiteurs et les visiteurs récurrents sur le chiffre d’affaires »</li></ul><p>Pour plus d’informations, voir [Compétences et limitations](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations).</p> |
| Trouver des opportunités de croissance négligées | Explore les audiences, les parcours et les canaux pour identifier les opportunités que les chiffres globaux des performances peuvent masquer.<p>**Exemples d’invites :**</p><ul><li>« Quelles audiences convertissent au-dessus de la moyenne mais obtiennent peu de trafic ? »</li><li>« Quels canaux sont sous-utilisés pour leur taux de conversion ? »</li></ul> |
| [Analyser les tendances opérationnelles et les causes](/help/chat/use-cases/workflows.md#data-insights) | Interrogez les données historiques de série temporelle des audiences, des jeux de données et des parcours et identifiez ce qui a provoqué une modification.<p>**Idéal pour :** administrateur, analyste</p><p>**Exemple d’invite :** « Afficher les tendances de taille d’audience au cours des 90 derniers jours »</p><p>**Condition préalable supplémentaire :** en plus des [conditions préalables générales](#prerequisites), ce cas d’utilisation nécessite également l’accès aux audiences, aux jeux de données ou aux parcours que vous souhaitez analyser.</p><p>Pour plus d’informations, voir [Informations sur les données](/help/chat/use-cases/workflows.md#data-insights) dans les cas d’utilisation du chat des collègues.</p> |
| Tracking des tendances de la taille des audiences | Repère les audiences qui augmentent ou diminuent et recherche la cause.<p>**Idéal pour :** administrateur, analyste</p><p>**Exemple d’invite :** « Quelles audiences ont connu la croissance la plus rapide ce trimestre ? »</p><p>**Condition préalable supplémentaire :** en plus des [conditions préalables générales](#prerequisites), ce cas d’utilisation nécessite également l’accès aux audiences que vous souhaitez suivre.</p> |
| Transformer une audience en insight | Passe d’un insight à une audience que vous pouvez créer, sans recommencer.<p>**Exemples d’invites :**</p><ul><li>« Ouvrir cette comparaison dans Analysis Workspace »</li><li>« Aidez-moi à créer une audience à partir de ce groupe »</li></ul><p>**Condition préalable supplémentaire :** en plus des [conditions préalables générales](#prerequisites), ce cas d’utilisation nécessite également l’accès à Real-Time Customer Data Platform et l’autorisation de créer des audiences.</p> |

## Compétences utilisées

<!-- FLAG: Confidence: High for Compare performance and Analyze operational trends and causes (skills listed for "Comparative analysis" and "Operational time-series & causal analysis" in workflows.md). Medium for Compare customer groups and Track audience size trends, which are mapped to the same skills based on their descriptions. Low for `audience-creation-flow`: inferred from the Audiences section of workflows.md. No skill is listed for Find overlooked growth opportunities because no source names one. Only `cja`, `aa`, and the root cause analysis skills currently appear in the Skills and limitations table on analytics-overview.md. -->

Mon collègue utilise les compétences suivantes pour les cas d’utilisation décrits dans cet article. Pour obtenir la liste de toutes les compétences en analyse, y compris les autorisations dont ils ont besoin et ce qu’ils ne couvrent pas, voir [Compétences et limites](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations) dans la section Analyser les données avec le chat d’un collègue.

| Compétence | Utilisé pour |
| --- | --- |
| `cja`, `aa` | Comparer les performances<br>Comparer les groupes de clients |
| `cja-root-cause-analysis`, `aa-root-cause-analysis` | Comparer les performances |
| `operational-stats-causal-analysis` | Analyse des tendances et causes opérationnelles<br>suivi des tendances de la taille des audiences |
| `audience-creation-flow` | Transformer une audience en insight |

## Conseils pour de meilleurs résultats

* Spécifiez les segments, audiences, canaux ou appareils que vous souhaitez inclure, exclure ou comparer.
* Référencez les segments et d’autres composants en fonction de leur nom exact.
* Nommez la mesure et la période pour lesquelles effectuer la comparaison, par exemple le chiffre d’affaires, mois après mois.
* Demandez les dimensions de contribution si vous souhaitez savoir pourquoi un groupe se comporte différemment d’un autre.

## Étapes suivantes

* Pour obtenir un aperçu de l’analyse des données avec le Module de conversation des collègues, y compris les autres domaines d’analyse et les bonnes pratiques, consultez [Analyse des données avec le Module de conversation des collègues](/help/chat/use-cases/data-insights/analytics-overview.md).
* Pour créer des audiences directement dans le chat avec un collègue, consultez [Évaluation de l’intégrité d’Experience Platform et création d’audiences en langage naturel avec un collègue](/help/chat/use-cases/audiences/create-audience-from-natural-language.md).
