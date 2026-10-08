---
title: Analyse des données Customer Journey Analytics avec la conversation des collègues
description: Découvrez comment utiliser le Module de conversation Adobe CX Enterprise Coworker pour analyser les données de Customer Journey Analytics, créer des entonnoirs et déterminer où les clients chutent dans le parcours.
hold: true
product_v2:
  internal-label: CX Enterprise Coworker
feature_v2:
  internal-label: CX Enterprise Coworker
source-git-commit: 2bf31c1348054a16ba7e7c0c26c0ff913634aa27
workflow-type: tm+mt
source-wordcount: '2354'
ht-degree: 0%
---

Le Module de conversation Adobe CX Enterprise Coworker permet aux équipes d’automatiser les tâches des produits Adobe en langage naturel, en transformant rapidement les idées en actions grâce à une planification flexible, des compétences personnalisables et une exécution intelligente. Pour plus d&#39;informations générales sur Coworker, voir Présentation de [](/help/home.md).

## Analyse des données avec le chat des collègues

La discussion avec les collègues peut effectuer une analyse avancée des données, ce qui était auparavant possible uniquement dans Analysis Workspace. Le Module de conversation avec un collègue accède aux données de vos vues de données Customer Journey Analytics ou suites de rapports Adobe Analytics, ce qui vous permet d’explorer ces données et d’obtenir des réponses aux invites en langage naturel.

Lorsque vous créez une visualisation dans le chat de vos collègues, vous pouvez l’ouvrir dans Analysis Workspace à tout moment pour une commande plus manuelle.

Les informations suivantes donnent un aperçu de la manière dont vous pouvez analyser les données dans le Module de conversation des collègues.

## Commencer l’analyse dans le Chat des collègues

Commencez par décrire ce que vous souhaitez savoir en langage clair. La discussion avec les collaborateurs planifie l’analyse, interroge vos vues de données ou suites de rapports et crée des visualisations et des résumés.

Les cas d’utilisation ci-dessous sont des exemples. Vous pouvez poser des questions sur toutes les données auxquelles vous êtes autorisé à accéder

### Cas d’utilisation clés

<!-- The following cards link to each of the stand-alone articles in this folder -->

<!--
CARDS

* https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/analytics-chat
  {title = Analyze Customer Journey Analytics and Adobe Analytics data}
  {description = Answers natural-language questions about your data views or report suites, builds funnels and other visualizations, and finds where customers drop off. You can open any visualization in Analysis Workspace for further analysis.}
  {cta = Read}
  {image = ../../assets/coworker-funnel-response-card.png}

* https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/root-cause-analysis
  {title = Explore trends and root causes}
  {description = Identifies trends in your Customer Journey Analytics and Adobe Analytics data and the factors that drive changes in performance, without manual queries.}
  {cta = Read}
  {image = ../../assets/data-validation-aa-cja/trend-line-card.png}
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Analyze Customer Journey Analytics and Adobe Analytics data">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/analytics-chat" title="Analyse des données Customer Journey Analytics et Adobe Analytics">
                        <img class="is-bordered-r-small" src="../../assets/coworker-funnel-response-card.png" alt="Analyse des données Customer Journey Analytics et Adobe Analytics"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/analytics-chat" title="Analyse des données Customer Journey Analytics et Adobe Analytics">Analyse des données Customer Journey Analytics et Adobe Analytics</a>
                    </p>
                    <p class="is-size-6">Répond aux questions en langage naturel sur vos vues de données ou suites de rapports, crée des entonnoirs et d’autres visualisations et trouve où les clients reviennent. Vous pouvez ouvrir n’importe quelle visualisation dans Analysis Workspace pour une analyse plus approfondie.</p>
                </div>
                <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/analytics-chat" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Lecture</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Explore trends and root causes">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/root-cause-analysis" title="Explorer les tendances et les causes profondes">
                        <img class="is-bordered-r-small" src="../../assets/data-validation-aa-cja/trend-line-card.png" alt="Explorer les tendances et les causes profondes"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/root-cause-analysis" title="Explorer les tendances et les causes profondes">Explorer les tendances et les causes profondes</a>
                    </p>
                    <p class="is-size-6">Identifie les tendances dans vos données Customer Journey Analytics et Adobe Analytics ainsi que les facteurs qui entraînent des modifications de performances, sans requêtes manuelles.</p>
                </div>
                <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/root-cause-analysis" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Lecture</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

<!--
CARDS

* https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/implementation-guide
  {title = Plan your implementation}
  {description = Creates a personalized, step-by-step plan for implementing Customer Journey Analytics, upgrading from Adobe Analytics, or setting up Content Analytics, Marketing Campaign Analytics, or Streaming Media collection on the Edge. Plans include details such as owners, effort estimates, dependencies, and validation steps.}
  {cta = Read}
  {image = ../../assets/ui-guide-6.png}

* https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/intelligent-checklist
  {title = Generate an implementation checklist}
  {description = Turns your Customer Journey Analytics implementation plan into a checklist in Coworker Projects, where your team can assign steps, track status, and add approval gates.}
  {cta = Read}
  {image = ../../assets/data-validation-aa-cja/date-detail.png}
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Plan your implementation">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/implementation-guide" title="Planification de la mise en œuvre">
                        <img class="is-bordered-r-small" src="../../assets/ui-guide-6.png" alt="Planification de la mise en œuvre"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/implementation-guide" title="Planification de la mise en œuvre">Planifier la mise en œuvre</a>
                    </p>
                    <p class="is-size-6">Crée un plan détaillé et personnalisé pour la mise en œuvre de Customer Journey Analytics, la mise à niveau à partir d’Adobe Analytics ou la configuration de la collecte de Content Analytics, Marketing Campaign Analytics ou de médias en flux continu sur Edge. Les plans incluent des détails tels que les propriétaires, les estimations d'effort, les dépendances et les étapes de validation.</p>
                </div>
                <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/implementation-guide" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Lecture</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Generate an implementation checklist">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/intelligent-checklist" title="Générer une liste de contrôle d’implémentation">
                        <img class="is-bordered-r-small" src="../../assets/data-validation-aa-cja/date-detail.png" alt="Générer une liste de contrôle d’implémentation"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/intelligent-checklist" title="Générer une liste de contrôle d’implémentation">Générer une liste de contrôle d’implémentation</a>
                    </p>
                    <p class="is-size-6">Transforme votre plan de mise en œuvre Customer Journey Analytics en une liste de contrôle dans les projets de collègues, où votre équipe peut affecter des étapes, suivre le statut et ajouter des points de contrôle d’approbation.</p>
                </div>
                <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/intelligent-checklist" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Lecture</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

<!--
CARDS

* https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/data-validation-aa-cja
  {title = Validate data when upgrading from Adobe Analytics to Customer Journey Analytics}
  {description = Compares dimensions, metrics, and trends between your Adobe Analytics report suites and Customer Journey Analytics data views, then recommends fixes to support your upgrade.}
  {cta = Read}
  {image = ../../assets/data-validation-aa-cja/trend-bar-card.png}

* https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/streaming-media-validation
  {title = Validate your Streaming Media implementation}
  {description = Checks your datastream, schema, dataset, data view, and session data to confirm that streaming media tracking is configured and collecting data correctly.}
  {cta = Read}
  {image = ../../assets/ui-guide-8.png}
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Validate data when upgrading from Adobe Analytics to Customer Journey Analytics">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/data-validation-aa-cja" title="Valider les données lors de la mise à niveau d’Adobe Analytics vers Customer Journey Analytics">
                        <img class="is-bordered-r-small" src="../../assets/data-validation-aa-cja/trend-bar-card.png" alt="Valider les données lors de la mise à niveau d’Adobe Analytics vers Customer Journey Analytics"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/data-validation-aa-cja" title="Valider les données lors de la mise à niveau d’Adobe Analytics vers Customer Journey Analytics">Valider les données lors de la mise à niveau d’Adobe Analytics vers Customer Journey Analytics</a>
                    </p>
                    <p class="is-size-6">Compare les dimensions, mesures et tendances entre vos suites de rapports Adobe Analytics et vos vues de données Customer Journey Analytics, puis recommande des correctifs pour prendre en charge votre mise à niveau.</p>
                </div>
                <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/data-validation-aa-cja" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Lecture</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Validate your Streaming Media implementation">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/streaming-media-validation" title="Validation de la mise en œuvre de Streaming Media">
                        <img class="is-bordered-r-small" src="../../assets/ui-guide-8.png" alt="Validation de la mise en œuvre de Streaming Media"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/streaming-media-validation" title="Validation de la mise en œuvre de Streaming Media">Valider la mise en œuvre de Streaming Media</a>
                    </p>
                    <p class="is-size-6">Vérifie le flux de données, le schéma, le jeu de données, la vue de données et les données de session pour confirmer que le suivi des médias en flux continu est configuré et que la collecte de données est correcte.</p>
                </div>
                <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/streaming-media-validation" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Lecture</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

<!--
CARDS

* https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/validate-dataset-quality-for-cja
  {title = Validate dataset quality for Customer Journey Analytics}
  {description = Identifies the datasets that feed your Customer Journey Analytics reporting, then checks schemas, identity quality, and field quality so you can resolve issues before you build dashboards.}
  {cta = Read}
  {image = ../../assets/data-validation-aep/dataset-validation.png}

* https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/data-validation-aep
  {title = Validate data after ingestion into Experience Platform}
  {description = Runs statistical and semantic checks on Experience Platform datasets and fields to find data quality issues, such as invalid values or mapping problems.}
  {cta = Read}
  {image = ../../assets/data-validation-aep/null-values.png}
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Validate dataset quality for Customer Journey Analytics">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/validate-dataset-quality-for-cja" title="Valider la qualité du jeu de données pour Customer Journey Analytics">
                        <img class="is-bordered-r-small" src="../../assets/data-validation-aep/dataset-validation.png" alt="Valider la qualité du jeu de données pour Customer Journey Analytics"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/validate-dataset-quality-for-cja" title="Valider la qualité du jeu de données pour Customer Journey Analytics">Valider la qualité du jeu de données pour Customer Journey Analytics</a>
                    </p>
                    <p class="is-size-6">Identifie les jeux de données qui alimentent vos rapports Customer Journey Analytics, puis vérifie les schémas, la qualité des identités et la qualité des champs afin que vous puissiez résoudre les problèmes avant de créer des tableaux de bord.</p>
                </div>
                <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/validate-dataset-quality-for-cja" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Lecture</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Validate data after ingestion into Experience Platform">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/data-validation-aep" title="Valider les données après ingestion dans Experience Platform">
                        <img class="is-bordered-r-small" src="../../assets/data-validation-aep/null-values.png" alt="Valider les données après ingestion dans Experience Platform"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/data-validation-aep" title="Valider les données après ingestion dans Experience Platform">Valider les données après ingestion dans Experience Platform</a>
                    </p>
                    <p class="is-size-6">Exécute des contrôles statistiques et sémantiques sur les jeux de données et les champs d’Experience Platform pour identifier les problèmes de qualité des données, tels que des valeurs non valides ou des problèmes de mappage.</p>
                </div>
                <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/data-validation-aep" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Lecture</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

Pour plus d’informations sur ces cas d’utilisation, y compris sur les compétences utilisées et les exemples d’invites, voir [Cas d’utilisation des informations sur les données](/help/chat/use-cases/overview.md#data-insights).

### Prise en main

Le Chat des collègues peut également vous aider à :

* **Comparer les performances** : comparez les mesures sur plusieurs canaux, périodes ou segments côte à côte.
* **Mesurer les performances de la campagne** : découvrez les performances des campagnes, des canaux et des propriétés web sur une période donnée.
* **Analyser les entonnoirs** : parcourez les entonnoirs de conversion à plusieurs étapes et observez le taux de déperdition à chaque étape.
* **Mesures de prévision** : projetez les valeurs des mesures futures à partir des données Customer Journey Analytics ou Adobe Analytics historiques, par exemple si vous êtes sur la bonne voie pour atteindre un objectif de chiffre d’affaires.
* **Créer des résumés exécutifs et des résumés d’indicateurs de performance clés** : produisez des résumés de performances prêts pour les parties prenantes, des recommandations et des résumés de diapositives.
* **Analyser les tendances et les causes opérationnelles** : interroger les données historiques de séries temporelles pour les audiences, les jeux de données et les parcours, et identifier ce qui a provoqué une modification.
* **Création de compétences Customer Journey Analytics personnalisées** : transformez une analyse que vous répétez en une compétence réutilisable qui persiste entre les sessions.

<!--
CARDS

* https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/analytics-chat
  {title = Analyze data with Coworker Chat}
  {description = Ask questions in natural language to build funnels, create visualizations, and find where customers drop off in the journey.}
  {cta = Read}
  {image = ../../assets/coworker-funnel-response-card.png}

* https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/root-cause-analysis
  {title = Explore trends and root causes}
  {description = Investigate changes in your Customer Journey Analytics data and uncover what drives them, without writing manual queries.}
  {cta = Read}
  {image = ../../assets/data-validation-aa-cja/trend-line-card.png}
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Analyze data with Coworker Chat">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/analytics-chat" title="Analyse des données avec le chat des collègues">
                        <img class="is-bordered-r-small" src="../../assets/coworker-funnel-response-card.png" alt="Analyse des données avec le chat des collègues"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/analytics-chat" title="Analyse des données avec le chat des collègues">Analyse des données avec la conversation des collègues</a>
                    </p>
                    <p class="is-size-6">Posez des questions en langage naturel pour créer des entonnoirs, créer des visualisations et déterminer où les clients se retrouvent dans le parcours.</p>
                </div>
                <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/analytics-chat" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Lecture</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Explore trends and root causes">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/root-cause-analysis" title="Explorer les tendances et les causes profondes">
                        <img class="is-bordered-r-small" src="../../assets/data-validation-aa-cja/trend-line-card.png" alt="Explorer les tendances et les causes profondes"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/root-cause-analysis" title="Explorer les tendances et les causes profondes">Explorer les tendances et les causes profondes</a>
                    </p>
                    <p class="is-size-6">Examinez les modifications apportées à vos données Customer Journey Analytics et découvrez ce qui les motive, sans écrire de requêtes manuelles.</p>
                </div>
                <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/root-cause-analysis" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Lecture</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

<!--
CARDS

* https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/validate-dataset-quality-for-cja
  {title = Validate Customer Journey Analytics data}
  {description = Check dataset quality with the data validation skill and resolve issues before you build dashboards.}
  {cta = Read}
  {image = ../../assets/data-validation-aep/dataset-validation.png}

* https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/data-validation-aa-cja
  {title = Validate data during your upgrade}
  {description = Compare Adobe Analytics and Customer Journey Analytics data to confirm that your upgrade is on track.}
  {cta = Read}
  {image = ../../assets/data-validation-aa-cja/trend-bar-card.png}
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Validate Customer Journey Analytics data">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/validate-dataset-quality-for-cja" title="Validation des données Customer Journey Analytics">
                        <img class="is-bordered-r-small" src="../../assets/data-validation-aep/dataset-validation.png" alt="Validation des données Customer Journey Analytics"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/validate-dataset-quality-for-cja" title="Validation des données Customer Journey Analytics">Valider les données Customer Journey Analytics</a>
                    </p>
                    <p class="is-size-6">Vérifiez la qualité du jeu de données avec les compétences de validation des données et résolvez les problèmes avant de créer des tableaux de bord.</p>
                </div>
                <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/validate-dataset-quality-for-cja" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Lecture</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Validate data during your upgrade">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/data-validation-aa-cja" title="Valider les données pendant la mise à niveau">
                        <img class="is-bordered-r-small" src="../../assets/data-validation-aa-cja/trend-bar-card.png" alt="Valider les données pendant la mise à niveau"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/data-validation-aa-cja" title="Valider les données pendant la mise à niveau">Valider les données pendant la mise à niveau</a>
                    </p>
                    <p class="is-size-6">Comparez les données d’Adobe Analytics et de Customer Journey Analytics pour confirmer que la mise à niveau est correctement effectuée.</p>
                </div>
                <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/data-validation-aa-cja" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Lecture</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->



## Mise en page Tableau des principaux cas d’utilisation

<!-- The following table are links to each of the stand-alone articles in this folder -->

| Cas d’utilisation | Description |
| --- | --- |
| [Analyse des données Customer Journey Analytics et Adobe Analytics](/help/chat/use-cases/data-insights/analytics-chat.md) | Répond aux questions en langage naturel sur vos vues de données ou suites de rapports, crée des entonnoirs et d’autres visualisations et trouve où les clients reviennent. Vous pouvez ouvrir n’importe quelle visualisation dans Analysis Workspace pour une analyse plus approfondie. |
| [Explorer les tendances et les causes profondes](/help/chat/use-cases/data-insights/root-cause-analysis.md) | Identifie les tendances dans vos données Customer Journey Analytics et Adobe Analytics ainsi que les facteurs qui entraînent des modifications de performances, sans requêtes manuelles. |
| [Planifier la mise en œuvre](/help/chat/use-cases/data-insights/implementation-guide.md) | Crée un plan détaillé et personnalisé pour la mise en œuvre de Customer Journey Analytics, la mise à niveau à partir d’Adobe Analytics ou la configuration de la collecte de Content Analytics, Marketing Campaign Analytics ou de médias en flux continu sur Edge. Les plans incluent des détails tels que les propriétaires, les estimations d&#39;effort, les dépendances et les étapes de validation. |
| [Générer une liste de contrôle d’implémentation](/help/chat/use-cases/data-insights/intelligent-checklist.md) | Transforme votre plan de mise en œuvre Customer Journey Analytics en une liste de contrôle dans les projets de collègues, où votre équipe peut affecter des étapes, suivre le statut et ajouter des points de contrôle d’approbation. |
| [Valider les données lors de la mise à niveau d’Adobe Analytics vers Customer Journey Analytics](/help/chat/use-cases/data-insights/data-validation-aa-cja.md) | Compare les dimensions, mesures et tendances entre vos suites de rapports Adobe Analytics et vos vues de données Customer Journey Analytics, puis recommande des correctifs pour prendre en charge votre mise à niveau. |
| [Valider la mise en œuvre de Streaming Media](/help/chat/use-cases/data-insights/streaming-media-validation.md) | Vérifie le flux de données, le schéma, le jeu de données, la vue de données et les données de session pour confirmer que le suivi des médias en flux continu est configuré et que la collecte de données est correcte. |
| [Valider la qualité du jeu de données pour Customer Journey Analytics](/help/chat/use-cases/data-insights/validate-dataset-quality-for-cja.md) | Identifie les jeux de données qui alimentent vos rapports Customer Journey Analytics, puis vérifie les schémas, la qualité des identités et la qualité des champs afin que vous puissiez résoudre les problèmes avant de créer des tableaux de bord. |
| [Valider les données après ingestion dans Experience Platform](/help/chat/use-cases/data-insights/data-validation-aep.md) | Exécute des contrôles statistiques et sémantiques sur les jeux de données et les champs d’Experience Platform pour identifier les problèmes de qualité des données, tels que des valeurs non valides ou des problèmes de mappage. |

Pour plus d’informations sur ces cas d’utilisation, y compris sur les compétences utilisées et les exemples d’invites, voir [Cas d’utilisation des informations sur les données](/help/chat/use-cases/overview.md#data-insights).

