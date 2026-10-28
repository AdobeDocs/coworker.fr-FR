---
title: Migration de projets Adobe Analytics vers Customer Journey Analytics
description: Utilisez des collaborateurs pour valider, mapper et migrer des projets Adobe Analytics Workspace et leurs composants vers Customer Journey Analytics, puis vérifier le statut de migration.
feature: AI Tools
role: Admin
level: Intermediate
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: decc8d209d4c9c177c6329a30668f0bbb8bd2c00
workflow-type: tm+mt
source-wordcount: '1785'
ht-degree: 1%
---

# Migrer des projets Adobe Analytics vers Customer Journey Analytics avec un collègue

<!-- FLAG: Confidence: High for the conversation flow, which is sourced from screenshots of the Coworker UI (October 2026) and the aa-mcp tool descriptions. The component migration tools run through the aa-mcp integration; there's no dedicated skill yet. Medium for statements that Coworker shares mappings and migration rules with migrations in the Adobe Analytics user interface; the user believes this is likely. Confirm with engineering. -->

Utilisez Adobe CX Enterprise Coworker pour migrer des projets Adobe Analytics et leurs composants associés vers Customer Journey Analytics au cours d’une seule conversation.

Coworker confirme que les dimensions et mesures de votre projet sont mappées à votre vue de données Customer Journey Analytics, vous aide à mapper celles qui ne le sont pas, puis recrée le projet dans Customer Journey Analytics.

<!-- FLAG: Add the planned general availability date when it's confirmed. -->

>[!AVAILABILITY]
>
>La fonctionnalité décrite dans cet article se trouve dans la phase de test limité de la publication et peut ne pas encore être disponible dans votre environnement. Cette note sera supprimée lorsque la fonctionnalité sera disponible.

>[!IMPORTANT]
>
>Avant de migrer des projets, lisez [Préparer la migration des composants et des projets d’Adobe Analytics vers Customer Journey Analytics](https://experienceleague.adobe.com/fr/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration) dans la documentation d’Adobe Analytics. Elle explique comment préparer une migration, les éléments inclus, ceux qui provoquent des erreurs et l’impact des mappages sur l’ensemble de l’organisation. Ces informations s’appliquent aux migrations dans Coworker.

## Différences par rapport à la migration dans l’interface utilisateur d’Adobe Analytics

<!-- FLAG: Add rows as differences are confirmed. Who can migrate and How you migrate: SME Scott Tomko (October 2026); Coworker matches the Analytics 2.0 Component Migration APIs, and functionally both methods do much the same thing. Project owner: Coworker behavior is from a test conversation (October 2026); the Adobe Analytics user interface behavior is from component-migration.md in the Adobe Analytics docs. Mapping dimensions and metrics: Confidence Medium for the Coworker column, which is based on the aa-mcp tool descriptions and a test conversation, not on an observed failed validation. Confirm that Coworker suggests and updates mappings, and whether it asks for confirmation before it updates a mapping. The Adobe Analytics user interface behavior is from component-migration.md in the Adobe Analytics docs. -->

La migration de projets avec Coworker diffère de la migration dans l’interface utilisateur d’Adobe Analytics des manières suivantes :

| | Coworker | Interface utilisateur d’Adobe Analytics |
| --- | --- | --- |
| **Qui peut migrer des projets** | Administrateurs Adobe Analytics et utilisateurs disposant de l’autorisation [!UICONTROL **Migration des composants**] | Administrateurs Adobe Analytics uniquement |
| **Propriétaire du projet** | L’utilisateur qui effectue la migration | Utilisateur spécifié dans le champ [!UICONTROL **Propriétaire du projet**] |
| **Mappage de dimensions et de mesures** | Un collègue valide le projet et répertorie la manière dont chaque dimension et mesure est mappée. Pour les qui ne peuvent pas être mappés automatiquement, Coworker suggère une dimension ou une mesure dans votre vue de données et met à jour le mappage. | Dans la section [!UICONTROL **Mapper le schéma**] , sélectionnez chaque dimension ou mesure avec un statut [!UICONTROL **Non mappé**] et mappez-la manuellement. |
| **Comment migrer** | Décrivez ce que vous souhaitez dans une invite. Le collègue fait le travail, en posant quelques questions en cours de route. Par exemple, un collègue peut créer un projet avec les composants que vous avez nommés, puis le migrer. Voir [Démarrer à partir de composants spécifiques](#start-from-specific-components). | Créez un projet dans Analysis Workspace, ajoutez les composants à migrer et enregistrez le projet. Ensuite, dans [!UICONTROL **Migration des composants**], sélectionnez le projet, spécifiez un propriétaire de projet, mappez le schéma de chaque suite de rapports, puis sélectionnez [!UICONTROL **Migrer**]. |

## Conditions préalables

<!-- FLAG: Confidence: High for the Adobe Analytics MCP and permission bullets, which come from the release announcement and SME Scott Tomko (October 2026): like the Analytics 2.0 Component Migration APIs, Coworker lets non-admins with the Component Migration permission migrate projects, while the Adobe Analytics UI is admin-only. Open question: Coworker makes the user who runs the migration the owner of the new project, but the aa-mcp tool description says the owner "should be an admin" and the Adobe Analytics component migration docs say the owner must be a Customer Journey Analytics administrator. Confirm whether a non-admin who runs a migration needs Customer Journey Analytics admin rights, or whether Coworker assigns a different owner. -->

Pour migrer des projets avec Coworker, vous avez besoin des éléments suivants :

* Accès au MCP Adobe Analytics. Les outils de migration des composants sont activés automatiquement pour les clients qui disposent d’un accès à Adobe Analytics MCP. Pour confirmer que [!UICONTROL **aa-mcp**] est connecté, consultez [Commencer à analyser les données avec le chat d’un collègue](/help/chat/use-cases/data-insights/analytics-chat.md).

* les droits d’administrateur Adobe Analytics ou l’autorisation [!UICONTROL **Migration des composants**] dans Admin Console. Il n&#39;est pas nécessaire d&#39;être administrateur.

* Les [conditions préalables](https://experienceleague.adobe.com/fr/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration#prerequisites) pour la migration des composants dans la documentation d’Adobe Analytics.

* Projet qui utilise des suites de rapports de base. Les suites de rapports virtuelles ne peuvent pas être migrées.<!-- FLAG: Sourced from Coworker's response in the UI. The Adobe Analytics component migration docs don't mention virtual report suites. Confirm, and consider adding it to those docs. -->

## Vérification des mappages de suites de rapports avant la migration

<!-- FLAG: Confidence: Medium. The recommendation to review mappings before the first migration from a report suite is inferred from the Adobe Analytics guidance to decide mappings as an organization; Coworker also validates mappings during each migration. Confirm with Scott. -->

Pensez à vérifier comment les dimensions et les mesures d’une suite de rapports sont mappées avant votre première migration depuis cette suite de rapports. Les mappages s’appliquent à chaque projet que votre organisation migre. Par conséquent, leur résolution permet d’abord aux projets ultérieurs de passer la validation. Pour plus d’informations sur le choix des mappages, voir [Décider en tant qu’organisation de la manière dont vous allez mapper les composants](https://experienceleague.adobe.com/fr/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration#decide-as-an-organization-how-you-will-map-components) dans la documentation d’Adobe Analytics.

Pour passer en revue les mappages, sélectionnez [!UICONTROL **Vérifier les mappages uniquement**] dans l’onglet [!UICONTROL **Portée**] ou demandez directement à votre collègue :

**Invites**

* « Montrez-moi comment les dimensions et les mesures de ma suite de rapports sont mappées à ma vue de données »
* « Quelles dimensions et mesures de ma suite de rapports ne sont pas mappées à ma vue de données ? »

Vous pouvez également demander à un collègue de mettre à jour les mappages.

Si vous ignorez cette révision, Coworker [vérifie toujours les mappages pour chaque projet que vous migrez](#review-the-validation-results-and-mappings).

## Démarrer une migration

<!-- FLAG: Confidence: High that migration works at the project level and that components migrate with their project (component-migration.md in the Adobe Analytics docs), and that components that already exist in Customer Journey Analytics aren't re-created (prepare-component-migration.md). Medium-low for when to use each method and for combining them; this guidance is inferred and isn't in the Adobe Analytics docs. Confirm with Scott. Also confirm whether Coworker creates a project automatically when you ask it to migrate only components (for example, "Migrate my Spring sale segments to CJA"), or whether you must ask it to create the project. -->

Coworker migre toujours un projet et ses composants associés. Pour migrer des composants spécifiques, demandez à un collègue de les ajouter à un nouveau projet, puis migrez ce projet.

Les composants qui existent déjà dans Customer Journey Analytics ne sont pas recréés. Vous pouvez donc utiliser les deux méthodes. Par exemple, migrez d’abord vos projets les plus importants, puis migrez les composants restants. Choisissez par où commencer en fonction de ce que vous souhaitez dans Customer Journey Analytics :

* **Migrer un projet** lorsque vous souhaitez conserver les panneaux et les visualisations du projet dans Customer Journey Analytics. Voir [Démarrer à partir d’un projet](#start-from-a-project).
* **Migrez des composants spécifiques** lorsque vous souhaitez des composants tels que des segments, des mesures calculées ou des périodes dans Customer Journey Analytics, mais que vous n’avez pas besoin des projets qui les utilisent. Par exemple, vous pouvez prévoir de créer de nouveaux projets dans Customer Journey Analytics qui les incluront. Voir [Démarrer à partir de composants spécifiques](#start-from-specific-components).

### Démarrer à partir d’un projet

Pour migrer un projet et ses composants associés, procédez comme suit :

1. Connectez-vous à un collègue.

1. Sélectionnez **[!UICONTROL Nouvelle conversation]**.

1. Dans le champ de texte, demandez à Coworker de migrer votre projet. Par exemple :

   **Invite**

   > Je souhaite migrer les composants d’Adobe Analytics vers Customer Journey Analytics.

   Un collègue décrit ce qu’il peut migrer et lance un questionnaire.

1. Dans l’onglet [!UICONTROL **Portée**], sélectionnez l’une des options suivantes, puis sélectionnez [!UICONTROL **Suivant**] :

   <!-- FLAG: Confidence: Medium for the "Plan a full upgrade" description. It likely hands off to the implementation guide skill and leaves the migration flow. Confirm with engineering. Also confirm what the Source & target tab asks; it was skipped in the screenshots. The Next and Submit buttons on the first questionnaire's Source & target and Review tabs are assumed to work like the second questionnaire. -->

   | Option | Description |
   | --- | --- |
   | [!UICONTROL **Un projet AA spécifique**] | Migrez un projet que vous nommez. Suivez les étapes restantes de cette section. |
   | [!UICONTROL **Vérifier les mappages uniquement**] | Vérifiez comment les mesures et dimensions d’une suite de rapports sont mappées à une vue de données, sans migrer quoi que ce soit. Consultez la section [&#x200B; Vérification des mappages de suites de rapports avant de migrer](#review-report-suite-mappings-before-you-migrate). |
   | [!UICONTROL **Planifiez une mise à niveau complète**] | Obtenez un plan de bout en bout pour passer d’Adobe Analytics à Customer Journey Analytics. Voir [Planifier la mise en œuvre avec un collègue](/help/chat/use-cases/data-insights/implementation-guide.md). |

1. (Facultatif) Répondez aux questions sur l’onglet [!UICONTROL **Source et cible**], puis sélectionnez [!UICONTROL **Suivant**].

1. Dans l’onglet [!UICONTROL **Vérifier**], confirmez vos réponses, puis sélectionnez [!UICONTROL **Envoyer**].

   Mon collègue vérifie les sociétés Adobe Analytics auxquelles vous avez accès et le nombre de suites de rapports de base dont chacune dispose, puis lance un second questionnaire.

1. Répondez aux questions suivantes en sélectionnant [!UICONTROL **Suivant**] après chacune d’elles :

   | Tabulation | Question | Contexte supplémentaire |
   | --- | --- | --- |
   | [!UICONTROL **Projet**] | Quel est le nom du projet AA que vous souhaitez migrer ? | Un nom partiel est correct. |
   | [!UICONTROL **Suite de rapports**] | Quelle suite de rapports le projet utilise-t-il ? | Sélectionnez une suite de rapports dans la liste ou saisissez le nom d’une autre suite. |
   | [!UICONTROL **Vue de données**] | Vers quelle vue de données CJA doit-il migrer ? | (Facultatif) Saisissez le nom d’une vue de données ou laissez-le vide et un collègue suggère des vues de données correspondantes. |

1. Dans l’onglet [!UICONTROL **Vérifier**], confirmez vos réponses, puis sélectionnez [!UICONTROL **Envoyer**].

   Pour ignorer le questionnaire à n’importe quelle étape, sélectionnez [!UICONTROL **Ignorer le questionnaire**] et décrivez plutôt ce que vous souhaitez dans le chat.

1. Continuez avec [Consultez les résultats de la validation et les mappages](#review-the-validation-results-and-mappings).

### Démarrer à partir de composants spécifiques

<!-- FLAG: Sourced from a prompt that SME Scott Tomko ran in Coworker (October 2026). The example is generalized; the original prompt named a customer. Coworker may ask a few questions along the way. Confirm what happens to the project that Coworker creates in Adobe Analytics, and to its migrated copy in Customer Journey Analytics, if you only wanted the components. -->

Pour migrer des composants spécifiques :

1. Demandez à un collègue de créer un projet avec ces composants, puis migrez-le. Par exemple :

   **Invite**

   > Je souhaite migrer tous mes segments Analytics portant le nom « Vente de printemps » vers CJA. Créez un projet Workspace avec tous ces segments ajoutés, puis migrez ce projet vers CJA.

   Un collègue crée le projet dans Adobe Analytics.

1. Passez à la section suivante, [Consultez les résultats de la validation et les mappages](#review-the-validation-results-and-mappings).

## Examinez les résultats de la validation et les mappages

<!-- FLAG: Confidence: Medium for the steps that fix a failed validation. They're based on the aa-mcp tool descriptions and on a test conversation where validation passed only after the project's panel was switched to a base report suite. Confirm how Coworker presents a failed validation, and whether it asks for confirmation before it updates a mapping. -->

Un collègue valide le projet par rapport à la vue de données que vous avez sélectionnée, puis indique si le projet peut être migré. La liste des résultats répertorie chaque dimension et mesure du projet, ainsi que la dimension ou la mesure Customer Journey Analytics à laquelle elle est mappée. Par exemple :

* **Mesure :** occurrences deviennent des événements
* **Dimension:** L&#39;heure reste l&#39;heure

Pour les composants et les éléments de projet qui sont migrés, consultez la section [Comprendre ce qui est inclus dans une migration](https://experienceleague.adobe.com/fr/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration#understand-what-is-included-in-a-migration) dans la documentation d’Adobe Analytics.

Si la validation ne réussit pas :

* **Dimensions ou mesures qui ne peuvent pas être automatiquement mappées :** un collègue suggère une dimension ou une mesure dans votre vue de données pour les mapper, met à jour le mappage, puis valide à nouveau le projet. Vous pouvez également indiquer à vos collègues la dimension ou la mesure à laquelle la mapper, par exemple, « Mapper les pages vues à web.webPageDetails.pageViews.value ».

* **Éléments non pris en charge :** supprimez tous les éléments non pris en charge du projet dans Adobe Analytics. Par exemple, assurez-vous que chaque panneau utilise une suite de rapports de base plutôt qu’une suite de rapports virtuelle. Demandez ensuite à votre collègue de vérifier à nouveau le projet. Pour obtenir la liste des éléments non pris en charge, voir [Présentation des éléments non pris en charge à l’origine d’erreurs](https://experienceleague.adobe.com/fr/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration#understand-unsupported-elements-that-cause-errors) dans la documentation d’Adobe Analytics.

Pour vérifier les mappages de l’ensemble d’une suite de rapports avant de migrer, consultez [Vérification des mappages des suites de rapports avant la migration](#review-report-suite-mappings-before-you-migrate).

## Migrer le projet

1. Lorsque la validation est réussie, un collègue demande si la version Customer Journey Analytics de votre projet doit être créée sur la vue de données que vous avez sélectionnée. Sélectionnez [!UICONTROL **Oui, migrer**], puis sélectionnez [!UICONTROL **Envoyer**].

   Pour arrêter sans migrer, sélectionnez [!UICONTROL **Non, arrêter ici**].

   Coworker recrée le projet dans Customer Journey Analytics, avec vous comme propriétaire du projet. Votre projet Adobe Analytics d’origine ne change pas.

1. Passez à la section suivante, [Vérification du statut de migration](#check-the-migration-status).

## Vérification du statut de migration

Les migrations s’exécutent en arrière-plan, de sorte que le nouveau projet peut ne pas être prêt immédiatement.

1. Demander à un collègue de vérifier le statut de la migration :

   **Invite**

   > Vérification de l’état

   <!-- FLAG: The Failed row links to Retry a failed migration in the Adobe Analytics docs, but those steps use the Component migration page in the Adobe Analytics UI, which is admin-only. A non-admin with the Component Migration permission can't follow them. Confirm with Scott whether Coworker can retry a failed migration (for example, "Retry the migration"). If so, replace the link with a prompt. -->

   Un collègue signale l’un des statuts suivants :

   | Statut | Signification |
   | --- | --- |
   | En file d’attente | La migration est en attente de démarrage. |
   | Démarré | La migration est en cours. |
   | Terminé | La migration est terminée. Coworker fournit un résumé de ce qui a été migré, y compris le nom du projet et la vue de données. |
   | Échec | Échec de la migration. Vous pouvez réessayer la migration. Voir [Reprise d’une migration ayant échoué](https://experienceleague.adobe.com/fr/docs/analytics/admin/admin-tools/component-migration/component-migration#retry-a-failed-migration) dans la documentation d’Adobe Analytics. |

1. Une fois la migration terminée, ouvrez le nouveau projet dans la liste de vos projets dans Customer Journey Analytics Workspace.

1. (Facultatif) Transférez la propriété du projet à tout utilisateur dans Customer Journey Analytics. Pour plus d’informations, voir [&#x200B; Transfert de ressources &#x200B;](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/tools/asset-transfer/transfer-assets).

Une fois la migration terminée, Coworker peut suggérer un autre projet de migration.

## Conseils pour de meilleurs résultats

* Laissez la vue de données vide dans le questionnaire si vous ne savez pas laquelle utiliser. Un collègue suggère des vues de données correspondant à la suite de rapports.
* Après avoir migré, comparez vos données Adobe Analytics et Customer Journey Analytics pour confirmer que vos rapports correspondent. Voir [Validation des données avec un collègue lors de la mise à niveau d’Adobe Analytics vers Customer Journey Analytics](/help/chat/use-cases/data-insights/data-validation-aa-cja.md).

## Étapes suivantes

* Pour migrer les projets dans l’interface utilisateur d’Adobe Analytics à la place, consultez [Migration des composants et des projets d’Adobe Analytics vers Customer Journey Analytics](https://experienceleague.adobe.com/fr/docs/analytics/admin/admin-tools/component-migration/component-migration) dans la documentation d’Adobe Analytics.
* Pour les autres cas d’utilisation d’implémentation et d’administration, voir [Présentation de l’implémentation et de l’administration intelligentes](/help/chat/use-cases/data-insights/data-governance-and-validation.md).
