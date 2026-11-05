---
title: Analyse des causes premières avec Adobe Analytics et Customer Journey Analytics
description: Utilisez Adobe CX Enterprise Coworker pour étudier les modifications apportées aux mesures, identifier les dimensions et segments concernés et tester des hypothèses dans Adobe Analytics et CJA.
feature: AI Tools
role: User
level: Beginner
doc-type: Feature Video
duration: 186
last-substantial-update: 2026-08-10T00:00:00.000Z
jira: KT-22082
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: Coworker
source-git-commit: 7e096fc9cda2157c02501ee909a80bf4df9a2f32
workflow-type: tm+mt
source-wordcount: '716'
ht-degree: 0%
---

# Analyse des causes profondes avec [!DNL Adobe Analytics] et [!DNL Customer Journey Analytics]

Utilisez le Module de conversation Adobe CX Enterprise Coworker pour déterminer pourquoi une mesure a changé dans Adobe Analytics ou Customer Journey Analytics (CJA). Collègue analyse la modification que vous spécifiez, fait apparaître les dimensions et les segments qui y contribuent et vous aide à tester des hypothèses en utilisant le langage naturel.

## Utilisation des données Customer Journey Analytics pour l’analyse des causes premières

La vidéo suivante montre comment Coworker associe l’IA conversationnelle à Customer Journey Analytics. Découvrez comment poser des questions en langage naturel, visualiser les résultats, identifier les tendances significatives et découvrir les facteurs qui optimisent les performances sans créer de requêtes manuelles.

>[!VIDEO](https://video.tv.adobe.com/v/3496847/?learn=on&enablevpops)

### Conditions préalables

Avant de commencer :

1. **Avoir accès au Chat des collègues et connecter Customer Journey Analytics.** Vérifiez que votre entreprise a configuré l’intégration requise.
1. **Disposer d’un accès en affichage à la vue de données CJA que vous souhaitez analyser.** Coworker ne peut utiliser que les vues de données et les composants disponibles.
1. **Choisissez la vue de données qui contient la mesure et les dimensions appropriées.** Si vous pouvez accéder à plusieurs vues de données, nommez celle que vous souhaitez que Coworker utilise.
1. **Identifiez la modification que vous souhaitez étudier.** Spécifiez la mesure, la période et la période de comparaison. Vous pouvez également fournir des dimensions, des segments ou une hypothèse pour cibler l’analyse.

### Exemples d’invites pour Customer Journey Analytics

Remplacez le texte entre crochets par les noms de composant et les périodes de votre vue de données.

* Dans la vue de données **[nom de la vue de données]**, pourquoi **[mesure]** a-t-elle changé pendant **[période]** par rapport à **[période de comparaison]** ? Ventilez la modification par **[dimension]** et affichez les segments qui ont le plus contribué.
* Dans la vue de données **[nom de la vue de données]**, **[dimension ou segment]** a-t-il contribué à la diminution de **[mesure]** de **[période A]** à **[période B]** ? Comparez les valeurs des deux périodes et expliquez les modifications.
* Dans la vue de données **[nom de la vue de données]**, comparez **[mesure]** pour **[segment A]** et **[segment B]** pendant **[période]**. Quelles dimensions ont le plus contribué à la différence ?
* Dans la vue de données **[nom de la vue de données]**, testez cette hypothèse : **[énoncez votre hypothèse]**. Analysez la **[mesure]** pour la **[période]** et affichez les dimensions ou les segments qui la prennent en charge ou non.

## Utilisation des données d’Adobe Analytics pour l’analyse des causes premières

Un collègue peut examiner les raisons pour lesquelles une mesure a été modifiée dans une suite de rapports Adobe Analytics. Elle utilise les compétences `aa-root-cause-analysis` pour analyser une modification que vous spécifiez et identifier les dimensions et les segments qui y ont contribué.

### Conditions préalables

Avant de commencer :

1. **Avoir accès au Chat des collègues et connecter Adobe Analytics.** Dans Coworker, accédez à **Personnalisations > Intégrations** et confirmez que l’intégration `aa-mcp` est répertoriée et connectée. Si elle n’est pas disponible, demandez à votre administrateur de vérifier la configuration de votre organisation. Consultez [Commencer à analyser les données avec le Module de conversation des collègues](https://experienceleague.adobe.com/fr/docs/coworker/content/chat/use-cases/data-insights/analytics-chat) pour obtenir des conseils de configuration.
1. **disposer d’un accès en affichage à la suite de rapports Adobe Analytics que vous souhaitez analyser.** Coworker hérite de vos autorisations Adobe Analytics et ne peut utiliser que les suites de rapports et composants disponibles dans Analysis Workspace.
1. **Choisissez la suite de rapports qui contient les données pertinentes.** Si vous pouvez accéder à plusieurs suites de rapports, nommez la suite de rapports que vous souhaitez que Coworker utilise.
1. **Identifiez la modification que vous souhaitez étudier.** Spécifiez la mesure et la période. Pour une analyse plus ciblée, incluez une période de comparaison, les dimensions ou segments pertinents et toute hypothèse que vous souhaitez que Coworker teste.

### Exemples d’invites pour Adobe Analytics

Remplacez le texte entre crochets par les noms de composant et les périodes de votre suite de rapports.

* Dans la suite de rapports **[nom de la suite de rapports]** pourquoi **[mesure]** a-t-elle changé pendant **[période]** par rapport à **[période de comparaison]** ? Ventilez la modification par **[dimension]** et affichez les segments qui ont le plus contribué.
* Dans la suite de rapports **[nom de la suite de rapports]** la dimension **[ou le segment]** a-t-elle contribué à la diminution de **[mesure]** de **[période A]** à **[période B]** ? Comparez les valeurs des deux périodes et expliquez les modifications.
* Dans la suite de rapports **[nom de la suite de rapports]**, comparez **[mesure]** pour **[segment A]** et **[segment B]** pendant **[période]**. Quelles dimensions ont le plus contribué à la différence ?

## Ressources connexes

* [Analyse des données avec la conversation Adobe CX Enterprise Coworker](https://experienceleague.adobe.com/fr/docs/coworker/content/chat/use-cases/data-insights/analytics-overview)
* [Commencer à analyser les données avec le chat des collègues](https://experienceleague.adobe.com/fr/docs/coworker/content/chat/use-cases/data-insights/analytics-chat)
