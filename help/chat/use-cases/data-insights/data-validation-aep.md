---
title: Valider vos données Experience Platform avec un collègue
description: Découvrez comment utiliser les compétences de validation des données de CX Enterprise Coworker pour vérifier la qualité de vos jeux de données et champs Adobe Experience Platform par le biais du chat.
feature: AI Tools
role: User
level: Intermediate
doc-type: Tutorial
last-substantial-update: 2026-08-27T00:00:00.000Z
jira: PLAT-302857
feature_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: dbee38135a5491fd21b65fdbb70ba60d949d7560
workflow-type: tm+mt
source-wordcount: '1054'
ht-degree: 0%
---

# Valider vos données Experience Platform avec un collègue

Collègue inclut la compétence Validation des données qui vérifie la qualité des données de vos jeux de données Experience Platform. Utilisez-le pour exécuter des validations statistiques et sémantiques sur les jeux de données, analyser les champs du jeu de données et identifier les problèmes de qualité des données, le tout via une seule conversation avec vos collègues.

Les ingénieurs de données, les administrateurs de données et les ingénieurs d’implémentation l’utilisent pour des contrôles qualité rapides, sans requêtes SQL ni hiérarchies de schémas complexes.

Utilisez cette compétence pour :

* Validez les champs d’identité et d’événement clés après une nouvelle implémentation ou une mise à jour d’implémentation.
* Recherchez un problème de mappage suspecté en examinant les principales valeurs d’un champ et les valeurs non valides.
* Exécutez des contrôles continus de gestion des données sur les jeux de données critiques pour détecter précocement les régressions.

<!--TODO: skill display name "Data Validation skill" confirmed via the published KT-22622 video page (validate-dataset-quality-for-cja.md, merged 2026-09-16). Still need the technical skill ID from engineering (Petru Adrian Snep) for the use-cases overview table row. That page didn't add one either.-->

>[!NOTE]
>
>Cette compétence est en lecture seule. Cela ne modifie pas vos données, schémas ou mappages.

## Avant de commencer

Pour valider vos données avec Coworker, vous devez :

* Nom ou ID du jeu de données à valider.
* (Facultatif) Nom d’un champ spécifique à valider si vous ne souhaitez pas que la compétence sélectionne automatiquement les champs.

## Démarrer une session de validation

1. Connectez-vous à un collègue.

1. Sélectionnez [!UICONTROL **Nouvelle conversation**].

1. Dans le champ de texte, demandez à l’agent de valider un champ ou un jeu de données. Par exemple :

   **Invite**

   > Valider le jeu de données « Electronics Sample 1000 »

   ![Écran d’accueil de la conversation avec l’invite Valider le jeu de données Electronics Sample 1000 saisie dans le champ de message.](../../assets/data-validation-aep/start-session.png)

   >[!TIP]
   >
   >Ajoutez le nom de votre jeu de données avec le mot « jeu de données » pour que la compétence puisse l’identifier correctement. Par exemple, utilisez « Valider l’échantillon électronique du jeu de données 1000 » au lieu de « Valider l’échantillon électronique 1000 ».

   Votre requête est acheminée vers la compétence Validation des données , qui analyse un échantillon de votre jeu de données et renvoie les résultats de la même conversation.

## Choisir les éléments à valider

Vous pouvez valider un seul champ ou un jeu de données entier.

>[!BEGINTABS]

>[!TAB Validation de champ]

Validez un champ spécifique dans un jeu de données. Cette option fournit les éléments suivants :

* Null count et valeur distincte count.
* Valeurs distinctes principales et leurs fréquences.
* Validation sémantique assistée par l’IA qui signale les valeurs qui ne correspondent pas au format attendu du champ, en fonction des métadonnées du champ et de ses valeurs réelles.

Exemples d’invites :

* Validez le champ d’e-mail dans le jeu de données Customers_2024.
* Validez le statut du champ pour le jeu de données customer_events_2024.
* Validez le champ person.address.city pour le jeu de données de données client.

>[!TAB Validation du jeu de données]

Validez jusqu’à cinq champs à la fois dans un jeu de données. Vous pouvez spécifier les champs vous-même ou laisser la compétence analyser le jeu de données et sélectionner automatiquement les champs les plus pertinents. Cette option renvoie les mêmes informations que la validation du champ, pour chaque champ que vous validez.

Exemples d’invites :

* Validez le jeu de données 2024 des données client.
* Valider les champs e-mail, téléphone pour Customers_2024.
* Résumez les paramètres firstName, lastName et bornDate pour les données client.

>[!ENDTABS]

## Consulter les résultats

Pour chaque champ validé, les résultats apparaissent sous la forme d&#39;une ligne dans un tableau avec les colonnes suivantes :

| Colonne | Description |
| --- | --- |
| [!UICONTROL Nom du champ] | Nom du champ. |
| [!UICONTROL Chemin du champ] | Chemin d’accès complet du champ dans le schéma. |
| [!UICONTROL Type de champ] | Type de données du champ. |
| [!UICONTROL Valeurs valides] | Pourcentage de valeurs échantillonnées qui réussissent la validation. |
| [!UICONTROL Valeurs distinctes] | Pourcentage de valeurs échantillonnées distinctes. |
| [!UICONTROL Valeurs nulles] | Pourcentage de valeurs échantillonnées nulles. |
| [!UICONTROL Les 5 premières valeurs distinctes] | Les cinq valeurs les plus courantes et leurs fréquences. |
| [!UICONTROL 5 premières valeurs non valides] | Les cinq valeurs non valides les plus courantes, avec une explication pour chacune, par exemple « format d’e-mail non valide ». |
| insight supplémentaire | Une courte note en langage naturel sur la qualité du terrain. |

Sous les résultats, Coworker ajoute une liste **Étapes suivantes** suggérant des invites de relance, telles que la validation d’un autre champ ou la réexécution du jeu de données.

Lorsque vous validez un seul champ, Coworker renvoie également un graphique :

![Conversation avec un collègue présentant un graphique en anneau et un résumé écrit pour le champ Marque, signalant 79,5 % de valeurs valides, 20,5 % de valeurs nulles et aucune valeur non valide détectée.](../../assets/data-validation-aep/null-values.png)

Sélectionnez [!UICONTROL **Graphique**] ou [!UICONTROL **Tableau**] pour basculer entre les vues des mêmes résultats.

Lorsque vous validez un jeu de données, les résultats apparaissent dans un tableau avec une ligne par champ. Les champs que vous nommez apparaissent tels que vous les avez spécifiés :

![Table de conversation des collègues intitulée Validation de champ d’exemple 1000 d’électronique, affichant les résultats de validation pour les champs de catégorie, de marque et de prix que l’utilisateur a nommés à l’invite.](../../assets/data-validation-aep/field-validation.png)

Les champs sélectionnés par les compétences apparaissent automatiquement de la même manière :

![Table de conversation des collègues présentant les résultats de validation de cinq champs sélectionnés automatiquement dans le jeu de données Exemple d’électronique 1000 : Catégorie, Marque, Prix, Inventaire et Condition.](../../assets/data-validation-aep/dataset-validation.png)

Sélectionnez [!UICONTROL **CSV**] pour télécharger le tableau complet des résultats.

## Contrôles effectués par validation des données

La compétence effectue les types de vérification suivants sur chaque champ et jeu de données :

* **Contrôles d&#39;exhaustivité** : nombres et pourcentages nuls et manquants.
* **Contrôles de distribution** : valeurs distinctes principales et leurs distributions, et détection de cardinalité élevée.
* **Vérifications sémantiques par rapport au schéma** : utilise le nom, le type et la description du champ XDM pour déduire ce à quoi ressemble une valeur valide, puis signale les anomalies.
* **Vérifications tenant compte du type de données**, le cas échéant :
  * E-mail : format et plausibilité du domaine.
  * Téléphone : préparation au format, par exemple E.164.
  * Dates et horodatages : contrôles de format de base, par exemple ISO-8601.

Ces contrôles associent des statistiques déterministes à une validation sémantique assistée par LLM afin de détecter les valeurs qui semblent fausses, même lorsqu’elles correspondent techniquement au schéma.

## Limites

Avant de valider vos données, gardez à l’esprit les restrictions suivantes. Ces contraintes équilibrent les performances avec les fonctionnalités et définissent les attentes en matière d’analyse et d’informations attendues.

* **Échantillonnage uniquement** : la compétence valide un échantillon du jeu de données (généralement les 1 000 lignes les plus récentes), et non le jeu de données entier. Les analyses de jeux de données complets ne sont pas disponibles.
* **Limite du nombre de champs** : lorsque vous validez un jeu de données, la compétence analyse jusqu’à cinq champs par requête. Vous pouvez spécifier ces champs ou laisser la compétence les sélectionner automatiquement.
* **Sémantique probabiliste** : la détection des valeurs non valides repose en partie sur l’inférence basée sur LLM, qui peut parfois ne pas détecter des erreurs subtiles ou marquer des valeurs limites.
* **Lecture seule** : la compétence ne modifie pas vos données ni leur schéma. Il met en évidence les problèmes potentiels, mais n’effectue pas de correctifs automatisés.

Si vos besoins de validation sont plus exhaustifs ou nécessitent une logique commerciale complexe, complétez ces résultats avec des outils supplémentaires tels que les validations de Query Service ou de Préparation de données.

**Informations connexes**

* [Validation des données Adobe Analytics en données Customer Journey Analytics lors de la mise à niveau](./data-validation-aa-cja.md)
* [Valider les données Customer Journey Analytics avec les compétences de validation des données dans Coworker](./validate-dataset-quality-for-cja.md)
* [Valider vos données (assistant d’IA)](https://experienceleague.adobe.com/fr/docs/cx-enterprise-ai/experience-cloud-ai/agents/data-validation)
* [Rapports Trust Your Customer Journey Analytics : compétences en validation des données dans Adobe CX Coworker](https://www.youtube.com/watch?v=gCSm_QYSYhk) (vidéo)
