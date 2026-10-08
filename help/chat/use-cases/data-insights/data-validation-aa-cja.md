---
title: Validation d’Adobe Analytics en données Customer Journey Analytics
description: Découvrez comment les administrateurs et administratrices d’Analytics utilisent les compétences de validation des données de CX Enterprise Coworker pour comparer les données d’Adobe Analytics et de Customer Journey Analytics pendant la mise à niveau.
feature: AI Tools
role: User
level: Intermediate
doc-type: Feature Video
duration:
last-substantial-update: 2026-08-10T00:00:00.000Z
jira: KT-22083
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
feature_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: 2bf31c1348054a16ba7e7c0c26c0ff913634aa27
workflow-type: tm+mt
source-wordcount: '1530'
ht-degree: 0%
---
# Valider les données avec un collègue lors de la mise à niveau d’Adobe Analytics vers Customer Journey Analytics

>[!NOTE]
> 
>Suivez les étapes de cette page uniquement après avoir effectué toutes les étapes de mise à niveau précédentes. Vous pouvez suivre les étapes de mise à niveau recommandées (recommandées pour la plupart des organisations) ou suivre les étapes générées dynamiquement pour votre organisation à l’aide du Guide de mise à niveau de Customer Journey Analytics. <ul><li>**Étapes de mise à niveau recommandées** (recommandée pour la plupart des entreprises)<p>Un ensemble d’étapes qui conduisent à une implémentation Customer Journey Analytics idéale.</p><p>Pour plus d’informations, voir [&#x200B; Mise à niveau d’Adobe Analytics vers Customer Journey Analytics &#x200B;](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/cja-upgrade-recommendations).</p></li><li>**Guide de mise à niveau de Customer Journey Analytics** (étapes personnalisées adaptées aux besoins spécifiques de votre entreprise)<p>Un nouveau guide de mise à niveau est disponible pour générer dynamiquement des étapes de mise à niveau adaptées à votre entreprise et à vos circonstances uniques.</p><p>Pour accéder au guide à partir de Customer Journey Analytics, sélectionnez l’onglet **[!UICONTROL Workspace]**, puis sélectionnez **[!UICONTROL Mettre à niveau vers Customer Journey Analytics]** dans le panneau de gauche. Suivez les instructions à l’écran.</p></li></ul>

Adobe CX Enterprise Coworker comprend des compétences de validation qui vous permettent de valider les données lors de la mise à niveau d’Adobe Analytics vers Customer Journey Analytics. La validation des données s’effectue dans une seule conversation.

Cette compétence compare automatiquement :

* Chaque dimension, mesure et tendance individuellement dans toutes les implémentations.

* Toutes les suites de rapports Adobe Analytics par rapport à toutes les vues de données Customer Journey Analytics.

Après avoir effectué ces comparaisons, les compétences génèrent des informations et des recommandations pilotées par l’IA que vous pouvez implémenter pour faciliter votre mise à niveau vers Customer Journey Analytics.

## Avant de commencer

Pour valider les données dans le cadre de la mise à niveau, vous avez besoin des éléments suivants :

* La suite de rapports Adobe Analytics que vous souhaitez valider.

* La vue de données Customer Journey Analytics qui contient les mêmes données.

Vous n’avez pas besoin de savoir comment votre implémentation est conçue. La compétence détecte automatiquement si votre mise en œuvre de Customer Journey Analytics utilise le connecteur Source Analytics ou une nouvelle mise en œuvre de la SDK web Experience Platform.

>[!VIDEO](https://video.tv.adobe.com/v/3496846/?learn=on&enablevpops)

## Démarrer une session de validation

1. Connectez-vous à un collègue.

1. Sélectionnez [!UICONTROL **Nouvelle conversation**].

1. Dans le champ de texte, demandez à l’agent de valider votre mise à niveau d’Adobe Analytics vers Customer Journey Analytics :

   **Invite**

   > M&#39;aider à valider la mise à niveau de mon entreprise d&#39;Adobe Analytics vers Customer Journey Analytics.

   Votre requête est acheminée vers la compétence de validation des données, qui lance un processus de configuration interactif.

1. Pour chaque question du processus de configuration, sélectionnez une réponse, puis cliquez sur [!UICONTROL **Envoyer**].

   Le processus de configuration comprend les questions du tableau ci-dessous.

   >[!NOTE]
   >
   >Vous pouvez modifier l’une de ces sélections ultérieurement au cours de la même conversation. Par exemple, demandez à l’agent de modifier votre suite de rapports ou votre vue de données et l’agent ne répétera que les étapes nécessaires pour mettre à jour cette sélection, sans redémarrer l’ensemble du processus de configuration.

   | Question | Contexte supplémentaire |
   |---------|----------|
   | [!UICONTROL **Sélectionnez votre société Analytics**] | Il s’agit de votre société de connexion Adobe Analytics. |
   | [!UICONTROL **Sélectionnez votre suite de rapports**] <!--In the UI, recommend change to "Select your Adobe Analytics report suite"--> | Il s’agit de la suite de rapports dans Adobe Analytics qui contient les données que vous souhaitez valider par rapport aux données Customer Journey Analytics. |
   | [!UICONTROL **Sélectionner la vue de données Customer Journey Analytics**] | Il s’agit de la vue de données dans Customer Journey Analytics qui contient les mêmes données que la suite de rapports Adobe Analytics que vous avez sélectionnée. |

1. Consultez le résumé de la configuration pour confirmer que vous validez les données appropriées avant de continuer.

   Le résumé comprend la société, la suite de rapports et la vue de données que vous avez sélectionnées, ainsi qu’un aperçu des principales mesures et dimensions de chaque système.

1. Passez à la section suivante, [Choisir les données à valider](#choose-the-data-to-validate).

## Choisir les données à valider

Vous pouvez valider des mesures ou des dimensions individuelles, ou valider toutes les mesures et dimensions incluses dans la suite de rapports et la vue de données.

1. Faites votre choix parmi les options suivantes :

   | Option de validation | Description |
   |---------|----------|
   | [!UICONTROL **Comparaison de mesures uniques**] | Comparez la tendance d’une mesure entre Adobe Analytics et Customer Journey Analytics. Utilisez cette option pour vérifier rapidement une mesure spécifique, telle que les pages vues ou les visites. |
   | [!UICONTROL **Comparaison à une seule dimension**] | Comparez la répartition d’une seule dimension entre Adobe Analytics et Customer Journey Analytics. Utilisez cette option lorsque vous suspectez une différence de mappage ou de classification pour une dimension spécifique. |
   | [!UICONTROL **Suite de rapports complète et audit des vues de données**] | Comparez jusqu’à 40 mesures et 20 dimensions Adobe Analytics à leurs homologues Customer Journey Analytics en une seule exécution. Utilisez cette option pour obtenir une vue d’ensemble de l’intégrité globale de votre mise à niveau. |

1. Passez à la section suivante, [Examiner l’analyse](#review-the-analysis).

## Vérifier l’analyse

1. Sélectionnez l’onglet [!UICONTROL **Taux de correspondance globale**] pour afficher un pourcentage qui indique dans quelle mesure les données de la suite de rapports Adobe Analytics correspondent à celles de la vue de données Customer Journey Analytics.

   Ce score apparaît toujours en premier, avant tout autre résultat. Il pèse chaque mesure et dimension comparées de manière égale afin de s’assurer que les mesures de volume élevé, telles que les pages vues, ne biaisent pas le score.

   Utilisez l’échelle suivante pour interpréter le score :

   | Score | Évaluation | Signification |
   |---------|----------|----------|
   | 97 %-100 % | ![Carré vert](../../assets/data-validation-aa-cja/excellent-square.svg) [!UICONTROL Excellent] | Toutes les propriétés sont fortement alignées. Aucune action requise. |
   | 90 %-96 % | ![Cercle jaune](../../assets/data-validation-aa-cja/good-circle.svg) [!UICONTROL Bon] | Des lacunes mineures sont présentes. Surveillez les tendances et déterminez si elles diminuent. |
   | 75 %-89 % | ![Cercle orange](../../assets/data-validation-aa-cja/review-circle.svg) [!UICONTROL Révision] | Il existe des lacunes importantes. Examinez les causes premières avant de vous fier aux données de Customer Journey Analytics. |
   | Moins de 75 % | ![Cercle rouge](../../assets/data-validation-aa-cja/critical-circle.svg) [!UICONTROL Pauvre] | Désalignement important. Agissez immédiatement avant d’utiliser les données Customer Journey Analytics. |

1. Sélectionnez l’onglet [!UICONTROL **Informations clés**] pour afficher deux à quatre cases de légendes courtes, chacune résumant un résultat de l’analyse en une seule phrase.

   Les légendes sont codées par couleur selon la gravité afin que vous puissiez identifier les résultats les plus importants en premier.

1. Sélectionnez l&#39;onglet [!UICONTROL **Résumé**] pour visualiser les informations suivantes :

   * Totaux Adobe Analytics

   * Totaux Customer Journey Analytics

   * Variance totale

   * Jours passant

     Indique le nombre de jours de la période qui entrent dans le statut d’écart [!UICONTROL **Pass**] décrit ci-dessous.

   * Nombre de jours critiques

     Indique le nombre de jours de la période dont le statut de variance [!UICONTROL **Critique**] décrit ci-dessous.

1. (Conditionnel) Lors d’une comparaison à une seule dimension ou à une seule mesure, sélectionnez l’onglet [!UICONTROL **Tendance quotidienne**] pour afficher une comparaison côte à côte des données Adobe Analytics et des données Customer Journey Analytics.

   Pour les mesures, il s’agit d’un graphique linéaire qui compare la tendance quotidienne.

   ![Onglet Tendance quotidienne affichant un graphique linéaire](../../assets/data-validation-aa-cja/trend-line.png)

   Pour les dimensions, il s’agit d’un graphique à barres qui compare les principales valeurs.

   ![Onglet Tendance quotidienne affichant un graphique à barres horizontales](../../assets/data-validation-aa-cja/trend-bar.png)

1. (Conditionnel) Lors d’une comparaison à une seule dimension ou à une seule mesure, sélectionnez l’onglet [!UICONTROL **Détail de la date**] pour afficher les informations suivantes pour chaque mesure ou valeur de dimension comparée :

   * Date

   * Valeur Adobe Analytics

   * Valeur Customer Journey Analytics

   * Pourcentage d&#39;écart

   * Badge de statut

   ![Onglet Détails de la date affichant un tableau des pourcentages d’écart et des badges de statut](../../assets/data-validation-aa-cja/date-detail.png)

   Les colonnes Variance et Statut utilisent l&#39;échelle suivante :

   | Variance | Statut | Signification |
   |---------|----------|----------|
   | Moins de 3 % | ![Coche verte](../../assets/data-validation-aa-cja/pass-check.svg) [!UICONTROL Réussite] | Les données sont bien alignées. Aucune action requise. |
   | 3 %-10 % | ![Triangle d’avertissement jaune](../../assets/data-validation-aa-cja/flagged-warning.svg) [!UICONTROL Indicateur] | Surveillez la différence et déterminez si elle persiste ou s’aggrave. |
   | Supérieur à 10 % | ![cercle rouge](../../assets/data-validation-aa-cja/critical-circle.svg) [!UICONTROL critique] | Enquêtez immédiatement. Cela pointe généralement vers un problème de schéma, d’ingestion ou de mappage. |

1. (Conditionnel) Lors de l’exécution d’une suite de rapports complète et d’un audit des vues de données, sélectionnez l’onglet [!UICONTROL **Carte de performance**] pour afficher les informations suivantes :

   * Nombre de réussites

   * Nombre marqués

   * Nombre critique

   * Tableaux répertoriant les cinq mesures et dimensions les mieux correspondantes et les cinq mesures et dimensions les moins correspondantes

1. Faites défiler l’analyse vers le bas pour afficher les modèles et les problèmes supplémentaires découverts au cours de l’analyse, les causes probables de ces modèles et les actions suggérées pour résoudre les incohérences de données.

   >[!NOTE]
   >
   >Une variation est attendue et n’indique pas de problème lors de la mise à niveau vers Customer Journey Analytics.

   Les problèmes courants sont les suivants :

   * Adobe Analytics comptabilise les visiteurs basés sur un appareil, tandis que Customer Journey Analytics comptabilise les personnes, à l’aide du groupement d’identités entre appareils.
   * Adobe Analytics traite les données au moment de la collecte, tandis que Customer Journey Analytics les traite au moment du rapport.
   * Les définitions de session diffèrent : les visites Adobe Analytics utilisent un délai d’expiration fixe, tandis que les sessions Customer Journey Analytics sont configurables.
   * Adobe Analytics filtre les robots par défaut, tandis que le filtrage des robots Customer Journey Analytics est activé.
   * Adobe Analytics signale les valeurs manquantes comme « Non spécifié » ou « Aucune », tandis que Customer Journey Analytics les signale comme « Aucune valeur ».
   * Les différences de canal marketing peuvent résulter de règles de traitement Adobe Analytics par rapport aux champs dérivés de Customer Journey Analytics appliqués rétroactivement.
   * Si les valeurs de Customer Journey Analytics sont systématiquement environ le double des valeurs d’Adobe Analytics pour toutes les mesures, cela indique généralement des données en double dans la vue de données plutôt qu’un effet de combinaison d’identités.

1. Vérifiez que les actions suggérées sont valides, puis résolvez-les dans Adobe Experience Platform ou Adobe Analytics.

1. (Facultatif) Poursuivez votre analyse en analysant une autre mesure ou une autre dimension, ou en exécutant un autre rapport contenant jusqu’à 40 mesures et 20 dimensions, comme décrit dans la section [Choisir les données à valider](#choose-the-data-to-validate).

   Vous n’avez pas besoin de répéter le processus de configuration pour ce faire ; les sélections de votre entreprise, de la suite de rapports et de la vue de données sont reportées tout au long de la conversation.

1. Continuez à suivre les [étapes de mise à niveau recommandées](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/cja-upgrade-recommendations#recommended-upgrade-steps-for-most-organizations) ou les étapes de mise à niveau générées dynamiquement dans le Guide de mise à niveau de Customer Journey Analytics.

   Pour accéder au Guide de mise à niveau de Customer Journey Analytics depuis Customer Journey Analytics, sélectionnez l’onglet **[!UICONTROL Workspace]**, puis sélectionnez **[!UICONTROL Mettre à niveau vers Customer Journey Analytics]** dans le panneau de gauche. Suivez les instructions à l’écran.

