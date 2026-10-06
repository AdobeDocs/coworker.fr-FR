---
title: Gestion de la rétention du lac de données
description: Découvrez comment utiliser CX Coworker pour identifier les données d’événement d’expérience qui méritent d’être optimisées, analyser l’utilisation des jeux de données et l’impact sur la rétention et gérer les politiques de rétention du lac de données.
source-git-commit: dbee38135a5491fd21b65fdbb70ba60d949d7560
workflow-type: tm+mt
source-wordcount: '1316'
ht-degree: 1%
---
# Gestion de la rétention du lac de données

Utilisez CX Coworker pour comprendre la valeur des données d’événement d’expérience dans votre sandbox et identifier les données qui peuvent bénéficier de l’optimisation. Vous pouvez commencer par une demande générale, par exemple demander à un collègue d’optimiser les données de votre sandbox ou de nettoyer les jeux de données. Coworker utilise Data Management Agent pour faire apparaître les jeux de données qui méritent d’être étudiés, analyser l’activité d’utilisation d’un jeu de données, modéliser l’impact d’une période de rétention et, le cas échéant, vous aider à gérer sa politique de rétention du lac de données.

## Avant de commencer {#before-you-begin}

Assurez-vous de travailler dans le sandbox qui contient les jeux de données à vérifier. Vous devez également accéder à l’agent de gestion des données et disposer des autorisations Adobe Experience Platform requises. Voir [Conditions préalables de l’agent de gestion des données](https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/agents/data-management#prerequisites).

## Optimisation des données dans votre sandbox {#optimize-data-in-your-sandbox}

Utilisez ces compétences ensemble comme un workflow. Commencez par un objectif général de gestion des données, tel que la compréhension de la valeur de vos données ou l’optimisation des données dans votre sandbox. Coworker vous aide à trouver des jeux de données qui méritent d’être étudiés, à vérifier l’activité d’utilisation d’un jeu de données, à modéliser l’impact d’une période de rétention potentielle, puis à définir, modifier ou supprimer une politique de rétention une fois que vous êtes prêt à agir.

### Rechercher des données à optimiser {#find-data-worth-optimizing}

Pour décider par où commencer, demandez à vos collègues d’identifier les jeux de données d’événements d’expérience qui méritent d’être étudiés. Vous pouvez commencer de manière générale en vous informant sur la valeur de vos données, l’optimisation des données ou le nettoyage des jeux de données. Utilisez les compétences Lister les jeux de données pour examiner la taille de stockage, le nombre de lignes, le statut de conservation existant et l’activation du profil. Vous pouvez filtrer les résultats en fonction de critères tels que la taille du jeu de données, le nombre de lignes ou un accès récent pour affiner la liste. La compétence est en lecture seule. Coworker renvoie un tableau que vous pouvez numériser et comparer, ainsi que des visualisations qui mettent en évidence les jeux de données par taille, nombre de lignes et âge des données.

![Résultats des collègues présentant les jeux de données d’événements d’expérience dans un tableau avec le stockage, le nombre de lignes, les informations de rétention et des visualisations de la taille du jeu de données et de l’âge des données.](../../assets/data-management/dataset-discovery-results.png)

Une fois que vous avez réduit la liste, utilisez la compétence Analyse de l’utilisation des jeux de données pour déterminer dans quelle mesure un jeu de données spécifique est utilisé de manière active.

Tous les jeux de données inutilisés ou abandonnés affichés par cette compétence ne constituent pas un bon candidat pour une politique de rétention du lac de données. Si vous devez supprimer un jeu de données complet ou gérer les données d’une autre boutique Experience Platform, consultez [Choisir la fonctionnalité de gestion du cycle de vie des données appropriée](https://experienceleague.adobe.com/en/docs/experience-platform/data-lifecycle/choose-a-capability). Avant de définir une politique de rétention du lac de données, vérifiez que le jeu de données est un jeu de données d’événement d’expérience.

Exemples d’invites :

- « J’ai le sentiment que mes données peuvent être optimisées. »
- « Aidez-moi à comprendre la valeur de mes données. »
- « Optimiser mes données Sandbox. »
- « Nettoyer mes jeux de données Sandbox. »
- « Afficher mes jeux de données d’événement les plus volumineux. »
- « Affichez-moi les jeux de données de plus de 100 Go qui n’ont pas de jeu de rétention du lac de données. »
- « Je dois supprimer environ 2 To de données. Par où commencer ? »
- « Pouvez-vous m’aider à trouver des données orphelines, abandonnées ou inutilisées ? »
- « Hiérarchisez les jeux de données qui n’ont pas été consultés au cours des 90 derniers jours. »

### Vérifier l’activité d’un jeu de données {#check-how-actively-a-dataset-is-used}

Avant de décider si un jeu de données est un bon candidat pour une politique de rétention du lac de données, découvrez à quel point le jeu de données est utilisé de manière active. Utilisez les compétences Analyser l’utilisation des jeux de données pour évaluer un jeu de données spécifique sur plusieurs signaux d’utilisation. Ces signaux incluent l’activité d’ingestion récente, l’activité de requête, la stabilité du schéma et le fait de savoir si le jeu de données alimente d’autres applications Adobe Experience Platform. La compétence est en lecture seule. Coworker renvoie un niveau d’utilisation global, une répartition des signaux et un résumé en langage clair de ce qu’ils indiquent sur le jeu de données.

<!-- TODO: Confirm the final usage-tier thresholds with engineering after the planned update from a 7-day to a 30-day analysis window is complete. Update this section with the final definitions before publishing. -->

>[!NOTE]
>
>Les mesures affichées sont destinées à fournir des signaux utiles et peuvent ne pas représenter tous les facteurs pertinents pour votre décision. Nous vous recommandons de consulter les détails disponibles et d’appliquer le contexte de votre entreprise avant d’agir.

![Analyse de l’utilisation des jeux de données des collègues présentant le niveau d’utilisation, les signaux d’utilisation individuels et un résumé de l’activité du jeu de données.](../../assets/data-management/dataset-usage-analysis.png)

Exemples d’invites :

- « Dans quelle mesure mon jeu de données d’événements web est-il utilisé ? »

### Modéliser l’impact d’une période de conservation {#model-the-impact-of-a-retention-period}

Avant de vous engager à respecter une période de conservation spécifique, déterminez la quantité de données à conserver ou à supprimer. Utilisez les compétences Analyser la rétention des jeux de données pour examiner les mesures de stockage d’un jeu de données et la répartition par âge de ses données. Il utilise ensuite cette distribution pour modéliser la quantité de données qu’une période de conservation proposée conserverait ou supprimerait. Coworker affiche l’impact estimé par nombre de lignes et taille de stockage.

![Collègue comparant le nombre de lignes conservées et supprimées pendant des périodes de conservation de 30, 60 et 90 jours.](../../assets/data-management/retention-period-comparison.png)

La compétence est en lecture seule. Coworker renvoie l’analyse de l’âge et de l’impact des données directement dans la conversation, afin que vous puissiez comparer les résultats avec les paramètres de conservation actuels du jeu de données avant de décider de les modifier ou non.

Exemples d’invites :

- « Quel serait l’impact si je définissais une période de conservation de 60 jours sur ce jeu de données ? »

### Définir, modifier ou supprimer une politique de rétention {#set-change-or-remove-a-retention-policy}

>[!IMPORTANT]
>
>La période minimale de conservation du lac de données est de 30 jours. Les périodes plus courtes ne sont pas prises en charge.

Une fois que vous avez décidé d’une période de rétention, utilisez les compétences Gérer la rétention des jeux de données pour définir, modifier ou supprimer une politique de rétention du lac de données sur un jeu de données. La compétence vous montre l’impact proposé avant l’application de toute modification. La politique n’est appliquée qu’après approbation explicite de la demande. La description de la modification souhaitée ne l’applique pas.

![Collègue présentant la politique de conservation du lac de données proposée, son impact et la confirmation requise avant l’application de la modification.](../../assets/data-management/retention-impact-preview.png)

Une fois que vous avez confirmé une politique de conservation, il se peut que la modification ne s’affiche dans l’interface utilisateur de Adobe Experience Platform que dans un délai court. La politique de conservation ne supprime pas immédiatement les données expirées. La tâche de rétention initiale commence dans les 24 heures suivant l’application de la politique. Après l’exécution initiale, une tâche planifiée évalue et supprime les enregistrements expirés tous les 30 jours. Pour plus d’informations sur la conservation et la purge](https://experienceleague.adobe.com/en/docs/experience-platform/catalog/datasets/experience-event-dataset-retention-ttl-guide) consultez le guide [Rétention du jeu de données d’événement d’expérience (TTL) .

Chaque modification de la stratégie de rétention est enregistrée dans un journal d&#39;audit, y compris lorsqu&#39;une stratégie est définie, modifiée ou supprimée. Le journal d&#39;audit enregistre qui a apporté chaque modification, quand elle s&#39;est produite et ce qui a été modifié. Vous pouvez suivre le lien fourni par un collègue pour passer en revue ces événements dans l’onglet Journal d’audit du jeu de données dans Adobe Experience Platform. Pour plus d’informations, voir la [présentation des journaux d’audit](https://experienceleague.adobe.com/fr/docs/experience-platform/landing/governance-privacy-security/audit-logs/overview).

![Journal d’audit Adobe Experience Platform présentant une mise à jour de la politique de rétention du lac de données, y compris la date et l’heure, l’utilisateur, le jeu de données, l’action et le statut.](../../assets/data-management/retention-audit-log.png)

Exemples d’invites :

- « Définissez la conservation de ce jeu de données sur 60 jours. »
- « Supprimez la politique de conservation sur ce jeu de données. »

## Bonnes pratiques {#best-practices}

Gardez à l’esprit les pratiques suivantes lors de l’utilisation de l’agent Data Management :

- **Commencez par un objectif général.** Si vous ne savez pas quel jeu de données requiert votre attention, demandez à un collègue de vous aider à comprendre la valeur de vos données ou à optimiser les données dans votre sandbox. Utilisez les compétences Lister les jeux de données pour identifier les jeux de données avec des signaux qui suggèrent une utilisation faible ou inexistante récemment avant d’analyser un jeu de données individuel.
- **Consultez l’aperçu de l’impact avant de confirmer.** Examinez les éléments qui seraient conservés et supprimés avant d’approuver une modification de conservation.
- **Laissez le temps aux modifications d’apparaître.** Après avoir confirmé une modification de la rétention dans CX Coworker, patientez quelques instants le temps que l’interface utilisateur de Adobe Experience Platform reflète la modification.

## Étapes suivantes {#next-steps}

Pour en savoir plus sur les compétences, la portée, le comportement et les limites de l’agent de gestion des données, consultez la [ présentation de l’agent de gestion des données](https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/agents/data-management). Pour plus d’informations sur le fonctionnement des politiques de rétention du lac de données dans Adobe Experience Platform, consultez le guide [Rétention du jeu de données d’événement d’expérience (TTL)](https://experienceleague.adobe.com/en/docs/experience-platform/catalog/datasets/experience-event-dataset-retention-ttl-guide).
