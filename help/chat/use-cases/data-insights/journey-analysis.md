---
title: Analyse des Parcours clients et du taux de déperdition avec le chat des collègues
description: Utilisez le Module de conversation des collaborateurs pour créer des entonnoirs, déterminer où les clients reviennent, diagnostiquer les baisses de conversion et comparer les parcours entre les périodes dans vos données Analytics.
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: b54085a497ca4bbf0003d5837d816206a4d40396
workflow-type: tm+mt
source-wordcount: '689'
ht-degree: 2%
---

# Présentation de l’analyse de parcours

<!-- FLAG: Confidence: High for the first sentence and "Best for" (carried over from analytics-overview.md). Medium for the second sentence, which summarizes the row descriptions from the slides. -->

Utilisez le Module de conversation Adobe CX Enterprise Coworker pour déterminer où les clients quittent le parcours pour la conversion et pourquoi, sur plusieurs canaux, appareils et segments. Décrivez le parcours en langage clair, et le Module de conversation des collègues crée le funnel, montre le taux de déperdition à chaque étape et vous aide à en rechercher la cause.

L’analyse de parcours est l’un des nombreux domaines d’analyse dans le chat Coworker. Pour afficher tous les domaines, voir [Commencer à analyser dans le chat des collègues](/help/chat/use-cases/data-insights/analytics-overview.md#start-analyzing-in-coworker-chat) dans Analyser les données avec le chat des collègues.

**Idéal pour :** Analyste, Utilisateur professionnel

## Conditions préalables

Pour utiliser les cas pratiques de cette page, vous avez besoin des éléments suivants :

* La conversation avec un collègue est connectée à vos vues de données Customer Journey Analytics ou suites de rapports Adobe Analytics. Voir [Commencer à analyser les données avec la discussion entre collègues](/help/chat/use-cases/data-insights/analytics-chat.md).
* Accès en affichage aux vues de données ou aux suites de rapports à analyser. La discussion avec les collègues hérite de vos autorisations de Customer Journey Analytics ou d’Adobe Analytics.

## Cas d’utilisation

| Cas d’utilisation | Fonction |
| --- | --- |
| [Analyse des données Customer Journey Analytics et Adobe Analytics](/help/chat/use-cases/data-insights/analytics-chat.md)<p>![Analyse des données Customer Journey Analytics et Adobe Analytics](../../assets/coworker-funnel-response-card.png)</p> | Répond aux questions en langage naturel sur vos vues de données ou suites de rapports, crée des entonnoirs et d’autres visualisations et trouve où les clients reviennent. Vous pouvez ouvrir n’importe quelle visualisation dans Analysis Workspace pour une analyse plus approfondie.<p>**Exemple d’invite :** « Afficher les pages vues au cours des 30 derniers jours »</p><p>Pour plus d’informations, voir [Commencer à analyser les données avec la discussion avec un collègue](/help/chat/use-cases/data-insights/analytics-chat.md).</p> |
| [Rechercher l’endroit où les clients reviennent](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations) | Construit un funnel à partir d’une question posée en langage clair, classe les fuites les plus importantes et suggère les étapes suivantes.<p>**Idéal pour :** utilisateur professionnel</p><p>**Exemples d’invites :**</p><ul><li>« Où perdons-nous des gens sur le chemin de l&#39;achat ? »</li><li>« Me guider dans le funnel de passage en caisse »</li></ul><p>Pour plus d’informations, voir [Compétences et limitations](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations).</p> |
| Diagnostiquer les baisses de conversion | Détermine où les clients abandonnent et évalue ce qui a contribué à la modification.<p>**Exemples d’invites :**</p><ul><li>« Pourquoi les conversions ont-elles diminué la semaine dernière ? »</li><li>« Où les clients ont-ils abandonné après le changement de site ? »</li></ul> |
| Isoler la cause d’un abandon | En excluant cette option, une par une isole le canal, l’appareil ou le segment à l’origine du problème.<p>**Exemples d’invites :**</p><ul><li>« L’abandon de panier est-il pire sur mobile ou poste de travail ? »</li><li>« Quels canaux présentent le plus de fuites entre le panier et l’achat ? »</li></ul> |
| Comparer les parcours entre les périodes | Indique, étape par étape, si les modifications que vous avez envoyées ont déplacé le funnel.<p>**Idéal pour :** utilisateur professionnel</p><p>**Exemples d’invites :**</p><ul><li>« Comparer la conversion de passage en caisse de ce trimestre au dernier »</li><li>« Comment mon funnel a-t-il changé après la refonte ? »</li></ul> |

## Exemple : Rechercher l’endroit où les clients repartent

Pour obtenir un exemple complet de conversation, de la première question à une recommandation, consultez [Exemple : trouver l’endroit où les clients reviennent](/help/chat/use-cases/data-insights/analytics-chat.md#example-find-where-customers-drop-off) dans Prise en main de l’analyse des données avec le chat d’un collègue.

## Compétences utilisées

<!-- FLAG: Confidence: High for `cja` and `aa` (the Skills and limitations table lists funnel and fallout analysis and side-by-side comparison of time periods). Medium for the root cause analysis skills: workflows.md maps the prompt "Why did conversions drop last week?" to them, but the mapping to the slide rows "Diagnose conversion declines" and "Isolate the cause of a drop-off" is inferred. Confirm with the PM. -->

Mon collègue utilise les compétences suivantes pour les cas d’utilisation décrits dans cet article. Pour obtenir la liste de toutes les compétences en analyse, y compris les autorisations dont ils ont besoin et ce qu’ils ne couvrent pas, voir [Compétences et limites](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations) dans la section Analyser les données avec le chat d’un collègue.

| Compétence | Utilisé pour |
| --- | --- |
| `cja`, `aa` | Analyse des données Customer Journey Analytics et Adobe Analytics <br>identification de l’endroit où les clients déposent<br>comparent les parcours entre les périodes |
| `cja-root-cause-analysis`, `aa-root-cause-analysis` | Diagnostiquer les baisses de conversion<br>Isoler la cause d’une chute |

## Conseils pour de meilleurs résultats

<!-- FLAG: Confidence: High, except the first bullet (Medium), which moved here from Prerequisites and is inferred from how funnel prompts work. The rest are adapted from the best practices in analytics-overview.md. -->

* Nommez les étapes de parcours à analyser, telles que la page du produit, le panier, le passage en caisse et l’achat.
* Nommez les dimensions, mesures et périodes à analyser, puis référencez les composants par leur nom exact.
* Demandez une visualisation funnel ou Abandon si c’est ce que vous souhaitez voir.
* Spécifiez les segments, canaux ou appareils que vous souhaitez inclure, exclure ou comparer.
* Mentionnez toute hypothèse que vous avez déjà, telle qu’un changement de site récent, afin que le Chat des collègues puisse la valider ou l’exclure.
* Demandez les étapes suivantes recommandées si vous souhaitez que le Chat des collègues vous suggère des questions de suivi.
* Ouvrez n’importe quelle visualisation dans Analysis Workspace lorsque vous souhaitez un meilleur contrôle manuel. Voir [ Analyser dans Customer Journey Analytics](/help/chat/use-cases/data-insights/analytics-chat.md#analyze-in-customer-journey-analytics).

## Étapes suivantes

* Pour obtenir un aperçu de l’analyse des données avec le Module de conversation des collègues, y compris les autres domaines d’analyse et les bonnes pratiques, consultez [Analyse des données avec le Module de conversation des collègues](/help/chat/use-cases/data-insights/analytics-overview.md).
* Pour configurer le Chat Coworker et parcourir un exemple pratique, consultez [Commencer à analyser les données avec le Chat Coworker](/help/chat/use-cases/data-insights/analytics-chat.md).
