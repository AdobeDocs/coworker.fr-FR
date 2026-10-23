---
title: Analyse des performances du contenu et de Creative avec le chat des collègues
description: Utilisez le Chat entre collègues pour trouver ce que le contenu gagnant a en commun, attribuer le chiffre d’affaires aux images que les clients voient et comparer les contenus créatifs sur plusieurs canaux et audiences.
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: b54085a497ca4bbf0003d5837d816206a4d40396
workflow-type: tm+mt
source-wordcount: '566'
ht-degree: 2%
---

# Performances du contenu - Aperçu

<!-- FLAG: Confidence: High for the first sentence and "Best for" (carried over from analytics-overview.md). Medium for the second sentence, which summarizes the row descriptions from the slides. -->

Utilisez le Module de conversation Adobe CX Enterprise Coworker pour identifier le contenu qui l’emporte et pourquoi, jusqu’aux attributs de chaque ressource, afin que vous puissiez investir dans ce qui fonctionne. Allez au-delà des fichiers pour lesquels des clics ont été effectués et découvrez les images, messages et thèmes qui génèrent de l’engagement et du chiffre d’affaires sur les canaux et les audiences.

La performance du contenu est l’un des nombreux domaines d’analyse dans le chat des collègues. Pour afficher tous les domaines, voir [Commencer à analyser dans le chat des collègues](/help/chat/use-cases/data-insights/analytics-overview.md#start-analyzing-in-coworker-chat) dans Analyser les données avec le chat des collègues.

**Idéal pour :** utilisateur professionnel

## Conditions préalables

<!-- FLAG: Confidence: High for the first two bullets (sourced from analytics-chat.md and the Skills and limitations table). High for the third bullet: attribute-level and asset analysis needs Content Analytics components, which are available only in data views that are configured for Content Analytics (report/report.md in analytics-platform.en). This applies whichever skill runs the analysis. It's a shared bullet rather than a table row because it applies to every use case on this page. The paid channel row ("Compare Meta ad creative to our web banners") also needs the Paid Media channel enabled in Content Analytics through an Experience Platform paid media source connector, such as Meta Ads or Google Ads. Comparing paid creative with on-site revenue needs custom tracking-key mapping, because enabling paid media doesn't connect paid media data to site orders or revenue (config/paid-media.md). Add an "Additional prerequisite" note on that row after the PM confirms. -->

Pour utiliser les cas pratiques de cette page, vous avez besoin des éléments suivants :

* La conversation avec un collègue est connectée à vos vues de données Customer Journey Analytics ou suites de rapports Adobe Analytics. Voir [Commencer à analyser les données avec la discussion entre collègues](/help/chat/use-cases/data-insights/analytics-chat.md).
* Accès en affichage aux vues de données ou aux suites de rapports à analyser. La discussion avec les collègues hérite de vos autorisations de Customer Journey Analytics ou d’Adobe Analytics.
* Une vue de données configurée pour Content Analytics. Voir [Configuration de Content Analytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/content-analytics/configuration/configuration) dans le guide de Customer Journey Analytics.

## Cas d’utilisation

| Cas d’utilisation | Fonction |
| --- | --- |
| Trouvez ce que le contenu gagnant a en commun<p>![Trouvez ce que le contenu gagnant a en commun](assets/content-performance.png)</p> | Indique quelles images et messages fonctionnent au niveau de l’attribut, et pas seulement quels fichiers ont reçu des clics.<p>**Exemples d’invites :**</p><ul><li>« Qu’ont en commun nos images les plus performantes ? »</li><li>« Quels attributs de contenu génèrent le plus d’engagement ? »</li></ul> |
| Attribuer le chiffre d’affaires au contenu que voit la clientèle | Associe l’exposition des images au chiffre d’affaires, aux conversions et à l’engagement avec l’attribution algorithmique.<p>**Idéal pour :** Analyste, Utilisateur professionnel</p><p>**Exemples d’invites :**</p><ul><li>« Quelles images incontournables ont généré le chiffre d’affaires le plus important au dernier trimestre ? »</li><li>« Quel est le chiffre d’affaires associé à cette bannière ? »</li></ul> |
| Comparer les contenus créatifs sur les canaux payants et propriétaires | Indique les visuels et thèmes qui gagnent sur les canaux web, mobiles et payants en une seule vue.<p>**Exemples d’invites :**</p><ul><li>« Quels thèmes créatifs gagnent en prix et sur notre site ? »</li><li>« Comparer les publicités Meta aux bannières web »</li></ul> |
| Identifiez les visuels qui déplacent chaque audience | Indique les visuels qui fonctionnent pour chaque audience afin de guider la personnalisation et les résumés créatifs.<p>**Exemples d’invites :**</p><ul><li>« Quels visuels sont les plus performants pour chaque segment ? »</li><li>« Quelles images fonctionnent pour les nouveaux visiteurs ? »</li></ul> |

## Compétences utilisées

<!-- FLAG: Confidence: Medium. The `analyze-content` skill is a foundational skill for content questions, so it's listed for every use case on this page. Confirm with the PM that it covers all four. -->

Mon collègue utilise les compétences suivantes pour les cas d’utilisation décrits dans cet article. Pour obtenir la liste de toutes les compétences en analyse, y compris les autorisations dont ils ont besoin et ce qu’ils ne couvrent pas, voir [Compétences et limites](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations) dans la section Analyser les données avec le chat d’un collègue.

| Compétence | Utilisé pour |
| --- | --- |
| `analyze-content`, `cja` | Identifiez le contenu gagnant en commun<br>Attribuez le chiffre d’affaires aux contenus que les clients voient<br>Comparez les contenus créatifs sur les canaux achetés et détenus<br>Identifiez les visuels qui déplacent chaque audience<p>Pour plus d’informations, voir [Poser des questions sur votre contenu](/help/chat/use-cases/data-insights/ask-content-questions.md).</p> |

## Conseils pour de meilleurs résultats

<!-- FLAG: Confidence: Medium. The first two bullets are adapted from the best practices in analytics-overview.md. The third bullet is inferred from the row descriptions. -->

* Nommez la mesure et la période à analyser, par exemple le chiffre d’affaires du dernier trimestre.
* Spécifiez les segments, audiences ou canaux que vous souhaitez comparer.
* Renseignez-vous sur les attributs de contenu, tels que les images, les thèmes ou les messages, plutôt que sur les fichiers individuels lorsque vous souhaitez savoir pourquoi le contenu fonctionne bien.

## Étapes suivantes

* Pour savoir comment Coworker répond aux questions sur le contenu, voir [Poser des questions sur votre contenu](/help/chat/use-cases/data-insights/ask-content-questions.md).
* Pour obtenir un aperçu de l’analyse des données avec le Module de conversation des collègues, y compris les autres domaines d’analyse et les bonnes pratiques, consultez [Analyse des données avec le Module de conversation des collègues](/help/chat/use-cases/data-insights/analytics-overview.md).
* Pour configurer le Chat Coworker et parcourir un exemple pratique, consultez [Commencer à analyser les données avec le Chat Coworker](/help/chat/use-cases/data-insights/analytics-chat.md).
