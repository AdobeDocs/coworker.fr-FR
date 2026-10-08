---
title: Générer une liste de contrôle d’implémentation dans les projets de collègues
description: Découvrez comment les projets de collègues génèrent une liste de contrôle d’implémentation préremplie à partir de votre plan des guides d’implémentation, avec des étapes que vous pouvez affecter et suivre.
hold: true
source-git-commit: 2bf31c1348054a16ba7e7c0c26c0ff913634aa27
workflow-type: tm+mt
source-wordcount: '703'
ht-degree: 0%
---

# Générer une liste de contrôle d’implémentation avec les projets de collègues

Adobe CX Enterprise Coworker peut générer un projet de liste de contrôle d’implémentation dans les projets de collègues, pré-renseigné avec les étapes ordonnées de votre plan de guide d’implémentation pour Customer Journey Analytics, une mise à niveau d’Adobe Analytics vers Customer Journey Analytics, Content Analytics (ACA), Marketing Campaign Analytics (MCA) ou Streaming Media. Coworker automatise ou aide avec autant d’étapes que techniquement possible, afin que vous et votre équipe disposiez d’un emplacement unique et traçable pour travailler sur votre implémentation.

Si vous dirigez une implémentation, exécutez des étapes techniques ou avez simplement besoin de visibilité sur la progression, vous pouvez utiliser cette liste de contrôle pour affecter du travail, suivre le statut et collaborer avec votre équipe, sans quitter Coworker.

>[!NOTE]
>
>Tenez compte des points suivants :
>
>* Cette fonction fait partie d’un workflow plus large et facultatif : étapes d’implémentation ou de mise à niveau personnalisées (voir [Planifier votre implémentation avec un collègue](./implementation-guide.md)), implémentation (cette liste de contrôle) et validation (par exemple, [Valider votre Adobe Analytics pour la mise à niveau de Customer Journey Analytics](./data-validation-aa-cja.md) ou [Valider votre implémentation de Streaming Media](./streaming-media-validation.md)). Vous n’avez pas besoin d’utiliser les trois étapes, mais la génération de cette liste de contrôle nécessite un plan de guide d’implémentation terminé.
>* Les étapes que Coworker exécute ou aide à inclure automatiquement un signal de confiance ou de vérification. Passez en revue ces étapes avant de les marquer comme terminées — Mon collègue ne présente pas les résultats automatisés comme des faits vérifiés.

Utilisez cette liste de contrôle pour :

* Lancez une implémentation ou une migration avec un ensemble ordonné d’étapes préremplies pour le chemin de votre produit, au lieu d’assembler manuellement un plan.

* Vérifiez le statut en cours d’implémentation, y compris ce qui est bloqué et ce qui suit, sans demander directement au responsable d’implémentation.

* Planifiez une implémentation multi-plateforme ou multi-région, où les étapes s’exécutent en parallèle ou par phases plutôt qu’en une seule ligne droite.

* Laissez Coworker exécuter des étapes directement, si possible, comme exécuter une vérification de validation entre vos configurations Adobe Analytics et Customer Journey Analytics.

* Introduisez des points de contrôle d’approbation pour les étapes qui doivent être approuvées avant que votre équipe n’avance.


## Avant de commencer

<!-- FLAG: Open question — release note confirms a "predefined playbook" transforms the guide plan into a Coworker Project, but it's unconfirmed whether Coworker runs that playbook automatically or the user has to trigger/follow it manually. Written below as if Coworker does it automatically; verify before publishing. Exact UI mechanics also unconfirmed since Coworker Projects platform documentation doesn't exist yet. -->

### Informations nécessaires

Pour générer une liste de contrôle d’implémentation, vous avez besoin des éléments suivants :

* Une conversation du guide de mise en œuvre terminée pour votre chemin de produit. Voir [Planifier la mise en œuvre avec un collègue](./implementation-guide.md). Coworker transforme automatiquement ce plan en projet Coworker, en utilisant un playbook prédéfini — vous n’avez pas besoin d’exporter quoi que ce soit vous-même.

* Accès aux projets de collègues dans votre organisation.

### Limites

Avant d’utiliser cette fonctionnalité, tenez compte des points suivants :

* **Ne possède pas le contenu du guide** : cette fonctionnalité consomme les plans des compétences du guide d’implémentation. Il ne crée ni ne conserve ce contenu sous-jacent.
* **Le comportement de synchronisation n’est pas encore entièrement défini** : la liste de contrôle est destinée à rester synchronisée avec les mises à jour de votre plan de guide d’implémentation, mais le mécanisme de synchronisation exact est toujours en cours de définition. Recherchez manuellement les mises à jour du plan directeur si votre implémentation s’étend sur une longue période.
* **Requires Coworker Projects** : cette fonctionnalité dépend de la plateforme Coworker Projects disponible dans votre entreprise.

## Générer une liste de contrôle

<!-- FLAG: Best guess, not confirmed by source docs. Coworker Projects UI isn't documented in this repo yet — verify exact navigation and UI labels once available. -->

1. Connectez-vous à un collègue.

1. Sélectionnez [!UICONTROL **Projets**] dans le rail de navigation.

1. Sélectionnez [!UICONTROL **Nouveau projet**], puis sélectionnez le playbook prédéfini qui correspond à votre plan de guide de mise en œuvre.

   Coworker transforme votre plan en un projet pré-renseigné avec les étapes ordonnées pour votre chemin.

## Consulter les résultats

Coworker génère votre liste de contrôle d’implémentation en tant que projet de collègue à partir duquel vous et votre équipe pouvez travailler.

**Vue Projet**

Votre projet regroupe les étapes de mise en œuvre ordonnées de votre plan. Pour chaque étape, vous pouvez :

* Attribuer un propriétaire
* Mise à jour du statut, par exemple en cours ou terminé
* Marquez une étape comme non applicable ou ignorez-la si elle ne s’applique pas à votre implémentation
* Ajouter des commentaires et collaborer avec votre équipe
* Exiger une approbation avant qu’une étape ne soit considérée comme terminée, pour les étapes qui doivent être approuvées

**Étapes automatisées et assistées**

Lorsque cela est techniquement possible, Coworker exécute ou aide directement une étape, comme l’affichage des données de configuration ou d’état à partir d’Adobe Analytics ou de Customer Journey Analytics. Ces étapes comportent un signal de confiance ou de vérification, comme décrit ci-dessus.

**Exports**

Exportez votre liste de contrôle ou sa progression au niveau du résumé vers Jira, Workfront ou Excel afin de pouvoir la plier dans votre workflow de gestion de projet existant.

**Listes de contrôle multiples**

Si vous gérez plusieurs implémentations simultanées, telles que plusieurs suites de rapports, régions ou marques, vous pouvez gérer plusieurs projets de liste de contrôle d’implémentation au lieu d’en limiter un seul.
