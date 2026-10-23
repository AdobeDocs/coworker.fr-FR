---
title: Conversation sur l’analyse des données Analytics avec Adobe CX Enterprise Coworker
description: Utilisez le Module de conversation Adobe CX Enterprise Coworker pour analyser les données Customer Journey Analytics et Adobe Analytics, rechercher les causes premières et ouvrir les résultats dans Analysis Workspace.
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: f1ffc050071fc0ca48ae36c7aea8bc66eff2a147
workflow-type: tm+mt
source-wordcount: '1358'
ht-degree: 1%
---

# Analyse des données avec le chat des collègues

Les informations de cette page donnent un aperçu du Module de conversation Adobe CX Enterprise Coworker et de la manière dont il peut vous aider à analyser les données pour votre organisation.

La discussion entre collègues permet aux équipes d’automatiser les tâches des produits Adobe en langage naturel, transformant rapidement les idées en actions grâce à une planification flexible, des compétences personnalisables et une exécution intelligente. Pour plus d&#39;informations générales sur Coworker, voir Présentation de [](/help/home.md).

## Fonctionnement de l’analyse des données

La discussion avec les collègues peut effectuer une analyse avancée des données, ce qui était auparavant possible uniquement dans Analysis Workspace. Le Chat Coworker accède aux données de vos vues de données Customer Journey Analytics ou suites de rapports Adobe Analytics, ce qui vous permet d’explorer les données et d’obtenir des réponses avec des invites en langage naturel.

La discussion avec les collègues hérite des autorisations de Customer Journey Analytics ou d’Adobe Analytics. Vous pouvez accéder uniquement aux vues de données, suites de rapports, dimensions, mesures et segments disponibles dans Analysis Workspace.

Lorsque vous créez une visualisation dans le chat de vos collègues, vous pouvez l’ouvrir dans Analysis Workspace à tout moment pour une commande plus manuelle. Voir [Ouvrir une visualisation dans Analysis Workspace](/help/chat/use-cases/data-insights/analytics-chat.md#open-a-visualization-in-analysis-workspace).

## Des réponses rapides et un travail approfondi

Vous pouvez utiliser le Module de conversation des collègues de deux manières, selon le niveau d’analyse dont vous avez besoin :

* **Réponses rapides** - Posez une question directe en langage simple et obtenez une réponse immédiate. Les utilisateurs professionnels utilisent souvent le Module de conversation des collaborateurs de cette manière, et les analystes l’utilisent également lorsqu’ils ont besoin d’une réponse rapide pour une partie prenante.
* **Réflexion approfondie** - Discutez longuement et à plusieurs reprises avec vos collègues dans le cadre du Module de conversation pour examiner un problème d’entreprise, en exclure les causes et formuler une recommandation. Les analystes utilisent généralement cette approche pour explorer les données en profondeur avant de formuler une recommandation.

## Commencer l’analyse dans le Chat des collègues

Commencez par décrire ce que vous souhaitez savoir en langage clair. La discussion avec les collaborateurs planifie l’analyse, interroge vos vues de données ou suites de rapports et crée des visualisations et des résumés.

Les cas d&#39;utilisation suivants sont regroupés par domaine d&#39;analyse. Chaque domaine possède sa propre page avec des cas d’utilisation, des exemples d’invites, des prérequis et les compétences qu’il utilise.

| Domaine | Ce que vous pouvez faire | Idéal pour |
| --- | --- | --- |
| [Implémentation et administration intelligentes](/help/chat/use-cases/data-insights/data-governance-and-validation.md) | Configurez, migrez et gérez votre implémentation , et assurez-vous que vous pouvez faire confiance aux données derrière chaque réponse. | Administration |
| [analyse de Parcours ](/help/chat/use-cases/data-insights/journey-analysis.md) | Recherchez où les clients quittent le parcours pour la conversion et pourquoi, sur l’ensemble des canaux, des appareils et des segments. | Analyste, Utilisateur professionnel |
| [Analyse des audiences et des segments](/help/chat/use-cases/data-insights/audience-and-segment-analysis.md) | Identifiez les groupes de clients qui se comportent différemment et comment ils se comportent, afin de pouvoir vous concentrer sur ceux qui comptent le plus. | Analyste, Utilisateur professionnel |
| [Performance commerciale](/help/chat/use-cases/data-insights/business-performance.md) | Découvrez comment se porte l’entreprise, pourquoi une mesure a été déplacée, où elle se dirige et ce qu’il faut faire ensuite. | Analyste, Utilisateur professionnel |
| [ Performances du contenu ](/help/chat/use-cases/data-insights/content-performance.md) | Identifiez le contenu gagnant et pourquoi, en fonction des attributs de chaque ressource, afin de pouvoir investir dans ce qui fonctionne. | Utilisateur professionnel |
| [Mesure et attribution marketing](/help/chat/use-cases/data-insights/marketing-measurement-and-attribution.md) | Découvrez l’impact incrémentiel de chaque canal marketing et campagne afin de pouvoir allouer des dépenses pour optimiser le retour sur investissement. | Analyste, Utilisateur professionnel |

## Compétences et limitations

Les compétences suivantes sont disponibles pour analyser les données Customer Journey Analytics ou Adobe Analytics.

| Compétence | Cas d’usage | Autorisations nécessaires | Hors de portée |
| --- | --- | --- | --- |
| `cja`, `aa` | Vues de données Query Customer Journey Analytics (`cja`) ou suites de rapports Adobe Analytics (`aa`) en temps réel :<ul><li>Mesures d’extraction, dimensions, segments, vues de données et suites de rapports</li><li>Comparaison de canaux, de périodes ou de segments côte à côte</li><li>Exécution d’une analyse des abandons et du funnel en plusieurs étapes</li><li>Prévision des mesures en fonction des tendances historiques</li></ul> | Accès en affichage à la vue de données ou à la suite de rapports sur laquelle vous souhaitez effectuer une requête | <ul><li>Créer ou modifier des composants de vue de données ou de suite de rapports</li><li>Données en dehors des vues de données ou des suites de rapports auxquelles vous avez accès</li><li>Modélisation prédictive au-delà des prévisions métriques</li></ul> |
| `cja-root-cause-analysis`, `aa-root-cause-analysis` | Découvrez pourquoi une mesure a été modifiée au lieu de simplement signaler qu’elle a été modifiée :<ul><li>Examiner une modification dans une mesure connue sur une période connue</li><li>Afficher les dimensions et les segments qui ont contribué à la modification</li></ul> | Accès en affichage à la vue de données ou à la suite de rapports en cours d’analyse | <ul><li>Détection des anomalies dont vous n’avez pas parlé (aucune alerte automatisée ou en temps réel)</li><li>Analyse de la cause première pour les mesures en dehors d’une vue de données ou d’une suite de rapports à laquelle vous avez accès</li></ul> |
| `cja-executive-summary` | Produisez des résumés de vos données prêts pour les parties prenantes :<ul><li>Résumer les performances sur une période spécifiée</li><li>Générer des recommandations prescriptives en fonction des données</li><li>Contenu hiérarchique pour un diaporama ou une lecture aux parties prenantes</li></ul> | Accès en affichage aux vues de données ou aux suites de rapports couvertes par le résumé | <ul><li>Création de la présentation ou du fichier de présentation final</li><li>Résumés qui couvrent des vues de données ou des suites de rapports auxquelles vous n’avez pas accès</li></ul> |
| `analyze-content`<!-- FLAG: Confirm the Out of scope items with the PM. --> | Répondez à des questions générales ou spécifiques sur votre contenu à l’aide des données Content Analytics dans Customer Journey Analytics :<ul><li>Découvrez les ressources et expériences les plus performantes qui ont en commun</li><li>Lier l’exposition du contenu aux conversions et aux recettes</li><li>Comparer le contenu sur plusieurs canaux et audiences</li></ul>Pour plus d’informations, voir [Poser des questions sur votre contenu](/help/chat/use-cases/data-insights/ask-content-questions.md). | Accès en affichage à une vue de données configurée pour Content Analytics | <ul><li>Installation ou configuration de Content Analytics</li><li>Contenu non collecté par Content Analytics</li></ul> |
| `aa-cja-validation` | Comparez, auditez et réconciliez les données entre [!DNL Adobe Analytics] et Customer Journey Analytics :<ul><li>Comparaison des valeurs de mesure entre une suite de rapports et une vue de données</li><li>Signaler les incohérences entre les deux sources de données</li></ul> | Accès en affichage à la suite de rapports [!DNL Adobe Analytics] et à la vue de données Customer Journey Analytics comparée | <ul><li>Résolution de la cause sous-jacente d’une incohérence des données</li><li>Validation de sources de données autres que [!DNL Adobe Analytics] et Customer Journey Analytics</li></ul> |
| `cja-skill-creator` | Transformer une analyse que vous avez déjà exécutée en une compétence réutilisable :<ul><li>Convertir une analyse terminée en une compétence nommée et réutilisable</li><li>Rendez une compétence enregistrée disponible lors de vos futures sessions de conversation</li></ul> | Gestion des compétences | <ul><li>Partager automatiquement une compétence enregistrée avec d’autres utilisateurs (les bibliothèques de compétences au niveau de l’organisation nécessitent une configuration administrateur)</li><li>La modification de la vue de données ou des composants de suite de rapports comme référence de compétence</li></ul> |

## Bonnes pratiques lors de l’analyse des données avec le chat des collègues

### Bonnes pratiques au niveau de l’organisation

* Désignez un analyste de votre entreprise comme champion Collègue.

* Créez une bibliothèque d’invites et de compétences validées en corrélation avec les données et les composants disponibles pour les utilisateurs.

* Créez une ou plusieurs compétences qui demandent au Module de conversation des collaborateurs de n’utiliser que les composants que vous souhaitez utiliser dans les analyses. Cela permet au Chat des collègues de fournir aux utilisateurs de votre organisation les données les plus pertinentes.

* Éduquez les utilisateurs sur quand demander une réponse rapide au Chat des collègues et quand l’utiliser pour un travail de réflexion approfondie.

### Bonnes pratiques au niveau de l’utilisateur

* Utilisez le mode Plan.

  Ce mode est particulièrement utile pour les tâches complexes, mais peut également donner de meilleurs résultats pour les tâches simples, car il permet à Coworker de poser des questions de suivi avant d&#39;agir. Pour plus d’informations, voir [Mode Plan](/help/chat/ui-guide.md#plan-mode).

* Lors de la création d’une invite, soyez aussi précis que possible :

  * Nommez les dimensions, mesures et périodes à analyser.
  * Référencez les composants en fonction de leur nom exact.
  * Spécifiez les segments, audiences, canaux ou appareils que vous souhaitez inclure, exclure ou comparer.
  * Indiquez si vous souhaitez un type de visualisation spécifique, tel qu’un funnel, un tableau de tendance ou un tableau de cohortes.
  * Demandez les étapes suivantes recommandées si vous souhaitez que le Chat des collègues vous suggère des questions de suivi.
  * Demandez un horizon de prévision, tel que « 30 prochains jours », lors de la projection des mesures.
  * Mentionnez toute hypothèse que vous avez déjà, afin que le Chat des collègues puisse la valider ou l’exclure.
  * Demandez les dimensions correspondantes si vous souhaitez obtenir la répartition d’une modification de mesure.
  * Spécifiez l’audience pour un résumé, tel que la direction ou l’équipe marketing, et demandez une présentation de diaporama si vous prévoyez de présenter les résultats.
  * Nommez la suite de rapports et la vue de données spécifiques que vous souhaitez comparer lors de la validation des données.
  * Commencez par effectuer une analyse, puis demandez à Chat de vos collègues de l’enregistrer en tant que compétence, en lui donnant un nom clair et descriptif et en notant la fréquence à laquelle vous prévoyez de le réutiliser.

* Ajoutez des instructions standard à la mémoire du Chat de vos collègues. Par exemple, si vous utilisez toujours des données provenant des mêmes vues de données ou suites de rapports, ajoutez-les à la mémoire. Pour plus d’informations, voir [Ajouter une préférence de vue de données ou de suite de rapports en mémoire](/help/chat/use-cases/data-insights/analytics-chat.md#add-a-data-view-or-report-suite-preference-in-memory) dans Prise en main de l’analyse des données avec le chat d’un collègue.

## Étapes suivantes

* Pour configurer le Chat Coworker et parcourir un exemple pratique, consultez [Commencer à analyser les données avec le Chat Coworker](/help/chat/use-cases/data-insights/analytics-chat.md).
* Pour voir chaque workflow de conversation avec un collègue ainsi que les compétences qui le sous-tendent, reportez-vous à la section [Workflows de conversation avec un collègue](/help/chat/use-cases/workflows.md).


