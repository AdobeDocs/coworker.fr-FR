---
title: Validation de la mise en œuvre de Streaming Media avec un collègue
description: Découvrez comment la compétence Validation des médias en flux continu de Coworker vérifie votre configuration, vos sessions et vos journaux pour confirmer que votre implémentation effectue correctement le suivi.
hold: true
source-git-commit: 2bf31c1348054a16ba7e7c0c26c0ff913634aa27
workflow-type: tm+mt
source-wordcount: '1304'
ht-degree: 2%
---

# Validation de la mise en œuvre de Streaming Media avec Coworker

Adobe CX Enterprise Coworker comprend une compétence Validation des médias en flux continu qui vérifie votre implémentation des médias en flux continu Adobe (analyses vidéo et audio) sur Edge Network, alimentant Customer Journey Analytics et/ou Adobe Analytics. Au lieu de référencer manuellement Assurance, la configuration des jeux de données, les groupes de champs de schéma XDM, la configuration des vues de données Customer Journey Analytics et les journaux réseau bruts, vous obtenez un seul rapport de validation.

Si vous implémentez ou résolvez les problèmes liés au suivi des médias en flux continu, vous pouvez utiliser ces compétences pour confirmer que votre implémentation est correctement configurée, collecter les données comme prévu et capturer ce que vous avez l’intention de suivre, le tout dans une seule conversation de conversation avec vos collègues.

>[!NOTE]
>
>Tenez compte des points suivants :
>
>* Cette compétence fait partie d’un workflow plus large et facultatif : étapes d’implémentation ou de mise à niveau personnalisées (voir [Planifier votre implémentation avec des collègues](./implementation-guide.md)), implémentation (voir [Générer une liste de contrôle d’implémentation avec des projets de collègues](./intelligent-checklist.md)) et validation (cette compétence). Vous n’avez pas besoin d’utiliser les trois étapes. Par exemple, vous pouvez valider votre mise en œuvre des médias en flux continu sans jamais générer de plan ou de liste de contrôle.
>* Cette compétence valide et diagnostique les problèmes. Cela ne corrige pas votre configuration ou vos données. Utilisez ses résultats pour guider votre propre remédiation.

Utilisez cette compétence pour :

* Exécutez un audit de configuration sur votre flux de données, schéma XDM, jeu de données et vue de données Customer Journey Analytics, le premier point de contrôle rompu étant identifié comme la cause probable.

  Cette fonctionnalité est actuellement en disponibilité limitée.

* Validez un identifiant de session vidéo spécifique et vérifiez exactement à quel bond, à quelle ingestion de jeu de données ou à quel mappage Customer Journey Analytics une incohérence s’est produite.

* Validez une session à partir d’un journal Charles ou HAR chargé, ou d’une liste d’URL plus simple, sans avoir besoin d’une session Assurance en direct.

  Cette fonctionnalité est actuellement en disponibilité limitée.

* Obtenez un contrôle d’intégrité global avec une seule invite, aucun ID de session ni journal requis, qui regroupe votre configuration et un échantillon de sessions récentes.

## Avant de commencer

<!-- FLAG: General access prerequisite is inferred, not stated explicitly in source docs. Per-mode inputs (session ID, log file) are directly sourced from Functional Requirements. -->

### Informations nécessaires

Pour valider l’implémentation des médias en flux continu, vous avez besoin des éléments suivants :

* Accès à Coworker avec les données Adobe Experience Platform et Customer Journey Analytics de votre entreprise connectées.

* Pour une validation d’ID de session, identifiant de session vidéo à vérifier.

* Pour une validation basée sur un journal, utilisez un fichier journal Charles ou HAR, ou une liste d’URL plus simple au format .txt, .md ou .json.

Aucune entrée spécifique n’est requise pour un audit de configuration ou un contrôle d’intégrité global. Coworker lit automatiquement votre configuration existante et échantillonne les sessions récentes.

### Limites

Avant d’utiliser cette compétence, tenez compte des points suivants :

* **Diagnostic uniquement** : cette compétence ne corrige pas votre configuration ou vos données. Il identifie les problèmes; vous faites le changement.
* **Médias en flux continu uniquement** : cette compétence couvre les implémentations de médias en flux continu sur Edge Network. Les jeux de données non multimédias et les implémentations web ou d’applications Analytics standard sont couverts par d’autres compétences de validation de Coworker.
* **À la demande uniquement** : cette compétence n’assure pas de surveillance en temps réel ou continue. Exécutez-le lorsque vous souhaitez effectuer une vérification plutôt que comme une alerte continue.
* **Pas de robot d&#39;exploration intégré** : cette compétence n’explore pas votre site ou votre application pour vous. Si vous souhaitez valider la couverture telle qu’explorée, fournissez une sortie de robot d&#39;exploration ou de navigateur découplé comme preuve.
* **Implémentations Edge Network uniquement** : les chemins d’implémentation Media SDK hérités et Analytics uniquement ne sont pas pris en charge.
* **Des fonctionnalités plus larges ne sont pas encore incluses** : la validation des événements en direct et du flux de pulsation, la validation des playbooks ou des scénarios des clients, un cumul des tableaux de bord historiques multi-plateformes et la validation de l’activation de Real-Time CDP ou de Adobe Journey Optimizer en aval sont prévus pour les versions ultérieures.

## Démarrer une session de validation

1. Connectez-vous à un collègue.

1. Sélectionnez [!UICONTROL **Nouvelle conversation**].

1. Dans le champ de texte, décrivez ce que vous souhaitez valider. Par exemple :

   **Invite**

   > Validez le #123 d’ID de session vidéo.

   Votre requête est acheminée vers la compétence Validation des médias en flux continu , qui exécute le mode de validation correspondant.

1. (Conditionnel) Si la compétence requiert des informations supplémentaires, telles qu’un ID de session ou un fichier journal, indiquez-le lorsque vous y êtes invité.

## Choisir le mode de validation

La compétence Validation des médias en flux continu comprend quatre modes.

### Audit de configuration

Cette fonctionnalité est actuellement en disponibilité limitée.

Validez l’ensemble de votre flux Adobe Experience Platform, du flux de données à la vue de données Customer Journey Analytics, y compris votre schéma XDM, votre jeu de données et toutes les règles de préparation des données ou les champs dérivés de Customer Journey Analytics. Un collègue signale une carte de score de réussite/échec par bond et signale le premier point de contrôle rompu comme cause probable.

Exemples d’invites :

* Validez la configuration des médias en flux continu pour la vue de données, le jeu de données et le flux de données.
* Vérifiez ma configuration des médias en streaming de bout en bout.
* Mon flux de données Media Analytics est-il correctement configuré pour Customer Journey Analytics ?

### Validation de l’ID de session

Vérifiez les lignes du jeu de données Adobe Experience Platform par rapport à la vue de données Customer Journey Analytics pour une session vidéo spécifique et déterminez si un écart est un problème d’ingestion du jeu de données ou un problème de mappage Customer Journey Analytics.

Exemples d’invites :

* Validez le #123 d’ID de session vidéo.
* Pourquoi la session abc-123 ne s’affiche-t-elle pas dans Customer Journey Analytics ?
* Comparez la session xyz entre le jeu de données et la vue de données Customer Journey Analytics.

### Validation basée sur le journal

Cette fonctionnalité est actuellement en disponibilité limitée.

Validez une session à partir d’un journal Charles ou HAR que vous téléchargez, ou d’une liste d’URL plus simple, sans avoir besoin d’une session Assurance en direct. Il valide les modèles de point d’entrée, les codes de réponse, le séquencement des événements et la cadence de ping, ainsi que les états qui ont été exécutés avec un degré de confiance maximal, réduits ou ignorés.

Exemples d’invites :

* Validez les journaux associés aux données de médias en flux continu.
* Vérifiez ce journal Charles pour les #456 d’ID de session.
* Validez cette liste d’URL par rapport aux pings de média attendus.

### Tableau de bord de validation

Obtenez un contrôle d’intégrité global avec une seule invite. Il regroupe l’audit de configuration et une vérification légère de session échantillonnée dans un seul statut et indique explicitement que les vérifications basées sur les journaux n’ont pas été exécutées si aucun journal n’a été fourni.

Exemples d’invites :

* Vérifiez les données des médias en flux continu.
* Me donner un rapport sur l’implémentation de mes médias en flux continu
* Dans quelle mesure mon implémentation des médias en flux continu est-elle globalement saine ?

## Consulter les résultats

Chaque mode renvoie les résultats dans un format adapté à votre validation.

**Résultats de l’audit de la configuration**

Une carte de performance de réussite/échec par bond couvrant le flux de données, le schéma XDM, le jeu de données, la vue de données Customer Journey Analytics et les règles de champ dérivées ou de préparation des données. Un collègue identifie le premier tronçon défaillant comme la cause principale probable.

**Résultats de la validation ID de session**

Un résumé des rapports Customer Journey Analytics uniquement, comprenant l’ID de session, les métadonnées du contenu, le nombre de lignes par type d’événement, les valeurs des mesures clés et une note d’intégrité. En cas d’écart, Coworker identifie si cela s’est produit lors de l’ingestion du jeu de données ou à l’étape de mappage Customer Journey Analytics.

>[!NOTE]
>
>Les ID de session et les valeurs d’identité authentifiées sont exclus par défaut de tout résumé exporté ou partagé.

**Résultats de la validation basés sur le journal**

Validation de la structure et du séquencement du journal chargé, couvrant les modèles de point d’entrée, les codes de réponse, l’ordre des événements et la cadence de ping. Les états du collègue qui s’exécutaient à confiance totale, ceux qui s’exécutaient à confiance réduite et ceux qui étaient ignorés, selon que vous avez fourni une capture de journal complète ou une liste d’URL plus simple.

**Résultats du tableau de bord**

Un seul état consolidé intitulé « Configuration + Données disponibles », combinant les résultats de votre audit de configuration avec une vérification échantillonnée des sessions récentes. Le collègue nomme les sessions échantillonnées et indique explicitement que les vérifications basées sur les journaux n’ont pas été exécutées car aucun journal n’a été fourni.

## Fonctionnement de la validation

Chaque mode est mappé à un moteur dédié :

* **Moteur de validation de configuration** : lit la configuration de votre flux de données, de votre schéma XDM, de votre jeu de données et de votre vue de données Customer Journey Analytics, et l’évalue par rapport à un ensemble fixe de points de contrôle.
* **Moteur de vérification croisée de session** : étant donné un ID de session, interroge votre jeu de données et la vue de données Customer Journey Analytics, calcule le nombre et le type de lignes attendus pour cette session et compare les résultats réels à chaque saut.
* **Analyseur de journaux et programme de validation** : analyse le journal ou la liste d’URL chargés, reconstruit la séquence et le minutage des requêtes et applique des contrôles structurels, de séquencement et de couche réseau.
* **Moteur d’agrégation des tableaux de bord** : exécute le moteur de validation de configuration et une exécution échantillonnée du moteur de vérification croisée de session, et les combine en un seul statut lorsque vous n’avez pas fourni d’ID de session, de journal ou de playbook.
