---
title: Poser des questions sur votre contenu avec le chat de vos collègues
description: Demandez à vos collègues de discuter de votre contenu dans un langage simple, du général au spécifique, et obtenez des réponses Content Analytics précises sans l’expertise d’un analyste.
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: Coworker
source-git-commit: 1ec3a8bf6dff44df068529cf1f7ceb699a027d65
workflow-type: tm+mt
source-wordcount: '1076'
ht-degree: 3%
---

# Poser des questions sur votre contenu

<!-- FLAG: Confirm with the PM: (1) availability (GA, beta, or experimental) and whether this page needs an AVAILABILITY note or `hide: true` until launch, and (2) any required Coworker entitlement. Content Analytics itself has no separate permission: users get access through data views that are configured for Content Analytics (Access control section of analytics-platform.en/help/content-analytics/config/configuration.md). -->

>[!AVAILABILITY]
>
>La fonctionnalité décrite dans cet article se trouve dans la phase de test limité de la publication et peut ne pas encore être disponible dans votre environnement. Cette note sera supprimée lorsque la fonctionnalité sera disponible.

Utilisez la discussion Adobe CX Enterprise Coworker pour obtenir des réponses précises sur votre contenu à partir d’Adobe Content Analytics. Posez une question spécifique, par exemple « Quelles images ont généré le plus de chiffre d’affaires au dernier trimestre ? », ou une question générale, par exemple « Quel type de contenu dois-je privilégier ? ». Coworker transforme votre question en une analyse solide.

Il comprend la structure des données Content Analytics et applique les règles de création de rapports d’un analyste expérimenté, de sorte que les spécialistes marketing et les autres utilisateurs professionnels obtiennent des résultats fiables sans expertise approfondie de Content Analytics.

Pour d’autres cas d’utilisation de performances du contenu, voir [Présentation des performances du contenu](/help/chat/use-cases/data-insights/content-performance.md).

**Idéal pour :** utilisateur professionnel, Analyste

## Conditions préalables

<!-- FLAG: Confidence: High. The first two bullets match the other data insights pages. The third bullet follows the Content Analytics docs in analytics-platform.en: Content Analytics components are available only in data views that are configured for Content Analytics (report/report.md), and there's no separate Content Analytics permission (config/configuration.md). -->

Pour poser des questions sur votre contenu, vous avez besoin de :

* La conversation avec un collègue est connectée à vos vues de données Customer Journey Analytics. Voir [Commencer à analyser les données avec la discussion entre collègues](/help/chat/use-cases/data-insights/analytics-chat.md).
* Accès en affichage aux vues de données à analyser. La discussion avec un collègue hérite de vos autorisations de Customer Journey Analytics.
* Une vue de données configurée pour Content Analytics. Voir [Configuration de Content Analytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/content-analytics/configuration/configuration) dans le guide de Customer Journey Analytics.

## Poser une question sur le contenu

1. Connectez-vous à un collègue.

1. Sélectionnez **[!UICONTROL Nouvelle conversation]**.

1. Dans le champ de texte, posez une question sur votre contenu. Par exemple :

   **Invite**

   > Quel type de contenu dois-je privilégier ?

   <!-- FLAG: The skill includes activation words and phrases, but they weren't provided. Confirm with the PM whether customers need to use specific words to trigger the skill, or whether any content question routes to it automatically. If specific words are needed, list them here. -->

   Un collègue utilise les compétences `analyze-content` pour répondre aux questions sur le contenu.

1. (Sous condition) Si votre question peut faire l’objet de plusieurs interprétations, répondez aux questions de clarification posées par vos collègues, telles que le type de contenu, le canal ou la période auxquels vous faites référence.

1. Passez en revue les résultats.

1. (Facultatif) Posez des questions de suivi au cours de la même conversation pour approfondir votre question, ou ouvrez une visualisation dans Analysis Workspace pour un contrôle plus manuel. Voir [Ouvrir une visualisation dans Analysis Workspace](/help/chat/use-cases/data-insights/analytics-chat.md#open-a-visualization-in-analysis-workspace).

## Exemples de prompts

Le tableau suivant présente des exemples d’invites pour différents types de questions sur le contenu. Utilisez-les comme point de départ et adaptez-les à votre propre contenu.

| Type de question | Exemples de prompts |
| --- | --- |
| Large ou exploratoire | <ul><li>« Quel type de contenu dois-je privilégier ? »</li><li>« Comment se portent nos contenus ? »</li></ul> |
| Niveau d’attribut | <ul><li>« Qu’ont en commun nos images les plus performantes ? »</li><li>« Quels attributs de contenu génèrent le plus d’engagement ? »</li></ul> |
| Chiffre d’affaires et conversions | <ul><li>« Quelles images ont généré le chiffre d’affaires le plus important au dernier trimestre ? »</li><li>« Quel est le chiffre d’affaires lié à l’image sur https://www.example.com/images/spring-sale.jpg ? »</li></ul> |
| Canaux et audiences | <ul><li>« Quels thèmes créatifs gagnent dans notre application mobile et sur notre site ? »</li><li>« Quelles images fonctionnent pour les nouveaux visiteurs ? »</li></ul> |

## Comment Coworker répond aux questions sur le contenu

<!-- FLAG: Confidence: High for the list of what the skill includes, metric matching, filtering pages by Experience ID, and choosing an attribution model per question (sourced from the PM's skill description and feature summary). Medium for the remaining details, which combine the skill description with the Content Analytics component reference in the Customer Journey Analytics guide. The skill's specific query defaults, attribution models, and visualization rules weren't provided. Confirm with the PM before adding them. -->

Un collègue répond aux questions de contenu avec la compétence `analyze-content`, qui comprend le contexte et les mécanismes de sécurisation suivants. La compétence s’associe à la compétence `cja` et exécute toutes les requêtes sur vos vues de données Customer Journey Analytics via les mêmes outils Customer Journey Analytics.

### Interroger les valeurs par défaut et clarifier les questions

Si votre question omet un détail, la compétence applique une valeur par défaut raisonnable. Si la compétence n’est pas certaine de ce que vous voulez dire, elle pose une question de clarification au lieu de deviner.

### Correspondance des mesures pour les ressources et les expériences

<!-- FLAG: The SME confirmed (October 2026) that the skill doesn't support paid media yet. Support is planned, either in this skill or in a separate add-on skill (not decided). When it ships, add paid media here: paid media content uses separate summary metrics, such as Impressions, Clicks, and Spend with a reporting-level suffix (for example, Clicks | Asset Summary), that can't be combined with event metrics such as Asset Views (config/paid-media.md in analytics-platform.en). -->

Content Analytics effectue le suivi de deux types de contenu : ressources et expériences. Chaque comporte ses propres mesures. La compétence associe toujours la mesure au type de contenu sur lequel vous posez des questions.

| Type de contenu | Description | Mesures utilisées par la compétence |
| --- | --- | --- |
| Ressources | Un élément de contenu individuel, comme une image | Vues des ressources, clics sur les ressources, taux de clic publicitaire des ressources |
| Expériences | Conteneur de contenu qui comprend du texte et des ressources, sur une page web ou dans une application mobile | Vues d’expérience, clics d’expérience, taux de clics publicitaires d’expérience (CTR) |

### Architecture des données Content Analytics

La compétence comprend la structure des données Content Analytics. Par exemple :

* **ID d’expérience :** lorsque vous posez des questions sur une page spécifique, les compétences sont filtrées par l’ID d’expérience de contenu qui identifie cette page.
* **Attributs générés par l’IA :** chaque ressource et expérience est décrite par des attributs tels que le style, les couleurs, le ton et la stratégie de persuasion de la photographie. La compétence utilise ces attributs pour expliquer pourquoi le contenu fonctionne bien, et pas seulement quel contenu fonctionne bien.

Pour obtenir la liste complète des composants, voir [Composants ](https://experienceleague.adobe.com/en/docs/analytics-platform/using/content-analytics/report/components) dans le guide de Customer Journey Analytics.

### Attribution

La compétence choisit le modèle d’attribution qui correspond à votre question. Par exemple, la réponse à une question sur les clics sur une image est différente de celle sur le chiffre d’affaires généré par cette image. Pour plus d’informations, voir [Modèles d’attribution](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/attribution/models#attribution-models) dans le guide de Customer Journey Analytics.

### Analyses et workflows courants

La compétence inclut des instructions pour les analyses de contenu courantes, telles que :

* Recherche des attributs communs aux ressources ou expériences les plus performantes.
* lier l’exposition du contenu aux conversions et au chiffre d’affaires ;
* Comparaison du contenu sur les canaux web et mobiles.
* Comparer le contenu qui fonctionne pour différentes audiences et différents segments.
* Identifier le contenu surutilisé ou sous-utilisé.

### Visualisations

Les compétences sélectionnent les visualisations qui correspondent à votre question et aux données, de sorte que les résultats soient faciles à lire et à partager.

## Conseils pour de meilleurs résultats

* Commencez à l&#39;étranger si vous n&#39;êtes pas sûr de savoir quoi demander. Un collègue peut transformer une question générale en une analyse ciblée, que vous pouvez affiner à partir de là.
* Indiquez si vous voulez parler de ressources individuelles, telles que des images, ou d’expériences entières, telles que des pages, lorsque vous savez lesquelles vous voulez.
* Lorsque vous posez des questions sur une image spécifique, incluez son URL ou son identifiant de ressource. Un collègue ne peut pas identifier une image en fonction de son rôle sur la page, par exemple une image de héros ou une bannière.
* Nommez la mesure et la période à analyser, par exemple le chiffre d’affaires du dernier trimestre.
* Spécifiez les segments, audiences ou canaux que vous souhaitez comparer.
* Renseignez-vous sur les attributs de contenu, tels que les images, les thèmes ou les messages, plutôt que sur les fichiers individuels lorsque vous souhaitez savoir pourquoi le contenu fonctionne bien.
* Ajoutez la vue de données de votre choix à la mémoire du Chat de vos collègues si vous analysez toujours la même vue. Voir [Ajouter une préférence de vue de données ou de suite de rapports en mémoire](/help/chat/use-cases/data-insights/analytics-chat.md#add-a-data-view-or-report-suite-preference-in-memory).

## Étapes suivantes

* Pour d’autres cas d’utilisation de performances de contenu, voir [Présentation des performances du contenu](/help/chat/use-cases/data-insights/content-performance.md).
* Pour en savoir plus sur Content Analytics, consultez la présentation de Content Analytics [](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/content-analytics/content-analytics) dans le guide de Customer Journey Analytics.
* Pour obtenir un aperçu de l’analyse des données avec le Chat des collègues, y compris des bonnes pratiques, consultez [Analyse des données avec le Chat des collègues](/help/chat/use-cases/data-insights/analytics-overview.md).
