---
title: Analyse des performances du contenu et de Creative avec le chat des collègues
description: Utilisez le Chat entre collègues pour trouver ce que le contenu gagnant a en commun, attribuer le chiffre d’affaires aux images que les clients voient et comparer les contenus créatifs sur plusieurs canaux et audiences.
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
feature_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: e3d485f7cd1c45bf3fd1217ffcceeccfd4242c7b
workflow-type: tm+mt
source-wordcount: '474'
ht-degree: 1%
---

# Performances du contenu - Aperçu

<!-- FLAG: Confidence: High for the first sentence and "Best for" (carried over from analytics-overview.md). Medium for the second sentence, which summarizes the row descriptions from the slides. -->

Utilisez le Module de conversation Adobe CX Enterprise Coworker pour identifier le contenu qui l’emporte et pourquoi, jusqu’aux attributs de chaque ressource, afin que vous puissiez investir dans ce qui fonctionne. Allez au-delà des fichiers pour lesquels des clics ont été effectués et découvrez les images, messages et thèmes qui génèrent de l’engagement et du chiffre d’affaires sur les canaux et les audiences.

La performance du contenu est l’un des nombreux domaines d’analyse dans le chat des collègues. Pour afficher tous les domaines, voir [Commencer à analyser dans le chat des collègues](/help/chat/use-cases/data-insights/analytics-overview.md#start-analyzing-in-coworker-chat) dans Analyser les données avec le chat des collègues.

**Idéal pour :** utilisateur professionnel

## Conditions préalables

<!-- FLAG: Confidence: High for the first two bullets (sourced from analytics-chat.md and the Skills and limitations table). Low for the third bullet: the attribute-level and image exposure descriptions suggest that these use cases rely on Content Analytics data in Customer Journey Analytics, and implementation-guide.md lists Content Analytics as an implementation path, but no source confirms this. It's a shared bullet rather than a table row because it would apply to every use case on this page. The paid channel row ("Compare Meta ad creative to our web banners") may need an additional data source, which would become an "Additional prerequisite" note on that row in the Use cases table. Confirm with the PM. -->

Pour utiliser les cas pratiques de cette page, vous avez besoin des éléments suivants :

* La conversation avec un collègue est connectée à vos vues de données Customer Journey Analytics ou suites de rapports Adobe Analytics. Voir [Commencer à analyser les données avec la discussion entre collègues](/help/chat/use-cases/data-insights/analytics-chat.md).
* Accès en affichage aux vues de données ou aux suites de rapports à analyser. La discussion avec les collègues hérite de vos autorisations de Customer Journey Analytics ou d’Adobe Analytics.
* Content Analytics configuré dans Customer Journey Analytics, de sorte que le Chat des collègues puisse analyser les attributs de contenu et l’exposition des images. Pour planifier une implémentation de Content Analytics, voir [Planifier votre implémentation avec un collègue](/help/chat/use-cases/data-insights/implementation-guide.md).

## Cas d’utilisation

| Cas d’utilisation | Fonction |
| --- | --- |
| Trouvez ce que le contenu gagnant a en commun<p>![Trouvez ce que le contenu gagnant a en commun](assets/content-performance.png)</p> | Indique quelles images et messages fonctionnent au niveau de l’attribut, et pas seulement quels fichiers ont reçu des clics.<p>**Exemples d’invites :**</p><ul><li>« Qu’ont en commun nos images les plus performantes ? »</li><li>« Quels attributs de contenu génèrent le plus d’engagement ? »</li></ul> |
| Attribuer le chiffre d’affaires au contenu que voit la clientèle | Associe l’exposition des images au chiffre d’affaires, aux conversions et à l’engagement avec l’attribution algorithmique.<p>**Idéal pour :** Analyste, Utilisateur professionnel</p><p>**Exemples d’invites :**</p><ul><li>« Quelles images incontournables ont généré le chiffre d’affaires le plus important au dernier trimestre ? »</li><li>« Quel est le chiffre d’affaires associé à cette bannière ? »</li></ul> |
| Comparer les contenus créatifs sur les canaux payants et propriétaires | Indique les visuels et thèmes qui gagnent sur les canaux web, mobiles et payants en une seule vue.<p>**Exemples d’invites :**</p><ul><li>« Quels thèmes créatifs gagnent en prix et sur notre site ? »</li><li>« Comparer les publicités Meta aux bannières web »</li></ul> |
| Identifiez les visuels qui déplacent chaque audience | Indique les visuels qui fonctionnent pour chaque audience afin de guider la personnalisation et les résumés créatifs.<p>**Exemples d’invites :**</p><ul><li>« Quels visuels sont les plus performants pour chaque segment ? »</li><li>« Quelles images fonctionnent pour les nouveaux visiteurs ? »</li></ul> |

<!--
HIDDEN until the skills are confirmed. To publish, remove this comment wrapper.

## Skills used

FLAG: Confidence: Low. No source in the repo (workflows.md, the Skills and limitations table, or any data insights article) names the skills behind these use cases. Get the skill IDs from the PM, replace the placeholder rows, and add the skills to the Skills and limitations table on analytics-overview.md so that the link above the table covers them. When you unhide this section, wrap this FLAG note in its own HTML comment.

Coworker uses the following skills for the use cases described in this article. For a list of all analytics skills, including the permissions they require and what they don't cover, see [Skills and limitations](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations) in Analyze data with Coworker Chat.

| Skill | Used for |
| --- | --- |
| *[Skill to be confirmed]* | Find what winning content has in common<br>Attribute revenue to the content customers see<br>Compare creative across paid and owned channels<br>Know which visuals move each audience |

-->

## Conseils pour de meilleurs résultats

<!-- FLAG: Confidence: Medium. The first two bullets are adapted from the best practices in analytics-overview.md. The third bullet is inferred from the row descriptions. -->

* Nommez la mesure et la période à analyser, par exemple le chiffre d’affaires du dernier trimestre.
* Spécifiez les segments, audiences ou canaux que vous souhaitez comparer.
* Renseignez-vous sur les attributs de contenu, tels que les images, les thèmes ou les messages, plutôt que sur les fichiers individuels lorsque vous souhaitez savoir pourquoi le contenu fonctionne bien.

## Étapes suivantes

* Pour obtenir un aperçu de l’analyse des données avec le Module de conversation des collègues, y compris les autres domaines d’analyse et les bonnes pratiques, consultez [Analyse des données avec le Module de conversation des collègues](/help/chat/use-cases/data-insights/analytics-overview.md).
* Pour configurer le Chat Coworker et parcourir un exemple pratique, consultez [Commencer à analyser les données avec le Chat Coworker](/help/chat/use-cases/data-insights/analytics-chat.md).
