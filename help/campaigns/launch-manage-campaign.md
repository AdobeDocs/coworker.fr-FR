---
description: Découvrez comment lancer une campagne, planifier son lancement et sa fréquence, et arrêter définitivement une campagne active qui est activement envoyée.
title: Lancement et gestion d’une campagne
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
feature_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: dbee38135a5491fd21b65fdbb70ba60d949d7560
workflow-type: tm+mt
source-wordcount: '610'
ht-degree: 2%
---
# Lancement et gestion d’une campagne {#launch-campaign}

Une fois votre campagne créée, apprenez à la lancer, à planifier son lancement et à l’arrêter si nécessaire.

>[!AVAILABILITY]
>
>Actuellement, la campagne Launch n’est disponible que pour les utilisateurs des régions d’Amérique du Nord.

## Lancement d’une campagne

1. Dans la campagne terminée, cliquez sur **Vérifier et lancer**.

   >[!NOTE]
   >
   >S’il manque des éléments, une boîte de dialogue s’affiche, répertoriant les éléments à compléter. Apportez les correctifs nécessaires et sélectionnez à nouveau **Vérifier et lancer**.

1. Une fois que la campagne a passé le contrôle de préparation, la boîte de dialogue de lancement s’ouvre, affichant un aperçu de l’e-mail et de l’audience.

1. Examinez le planning affiché dans la boîte de dialogue. Pour le modifier, utilisez les options de planning décrites dans [Planifier au lancement d’une campagne](#schedule-when-a-campaign-launches) puis cliquez sur **Enregistrer**.

1. Cliquez sur **Lancer la campagne** lorsque vous avez terminé.

>[!NOTE]
>
>- Une campagne ne peut pas être lancée avec un exemple d’audience (non réelle), des brouillons d’e-mails qui n’ont pas été vérifiés ou des paramètres d’envoi non configurés.
>
>- Si vous planifiez une campagne, vous pouvez toujours la modifier avant son lancement. Il n’est pas nécessaire de passer en mode brouillon.

## Planning du lancement d’une campagne {#schedule-when-a-campaign-launches}

Lors du lancement d’une campagne, vous pouvez choisir le moment exact de son lancement : immédiatement, à une date et une heure spécifiques dans le futur ou selon un planning récurrent. Vous pouvez également revenir ultérieurement et modifier le planning d’une campagne qui a déjà été lancée ou planifiée.

### Conditions préalables

La campagne doit être prête à être lancée (toute configuration requise est terminée).

### Planifier une campagne au lancement

1. Dans la campagne, cliquez sur **Vérifier et lancer**.

1. Dans la boîte de dialogue de lancement, choisissez une option de planification :
   - **Maintenant** : la campagne commence à envoyer immédiatement après le lancement.
   - **Planifier une fois** : sélectionnez une date ultérieure **Date de début** (date et heure confondues).
   - **Récurrent** : choisissez une **Fréquence** (Quotidienne, Hebdomadaire ou Mensuelle) et une heure de début, puis définissez le modèle de périodicité (voir les champs ci-dessous).

1. Si Récurrent est sélectionné, choisissez si la campagne se termine **Jamais** ou **À une date**, puis choisissez une date de fin, le cas échéant.

1. Confirmez pour lancer la campagne avec le planning sélectionné.

### Modifier un planning existant

1. Ouvrez la campagne et accédez à ses paramètres.

1. Recherchez la section Planning et sélectionnez la synthèse du planning actuel.

1. Mettez à jour le planning à l’aide des mêmes options que celles décrites ci-dessus.

1. Enregistrez la modification.

### Champs de saisie

| Champ | Description | Obligatoire ? |
| --- | --- | --- |
| Mode horaire | Choix entre Maintenant, Planifier une fois ou Récurrent | Oui |
| Date de début | Date et heure de début de la campagne (mode Planifier une seule fois) | Oui, pour Planifier une fois |
| Fréquence | Quotidienne, hebdomadaire ou mensuelle (mode récurrent) | Oui, pour récurrent |
| Heure de début | Heure d’envoi par la campagne récurrente | Oui, pour récurrent |
| Jours de la semaine | Le ou les jours où la campagne se répète | Oui, pour la fréquence hebdomadaire |
| Jour du mois | Le jour du mois où la campagne se répète | Oui, pour la fréquence mensuelle |
| Terminer la campagne | Jamais, ou à une date de fin spécifique | Oui, pour récurrent |

### Éléments à noter

- Les campagnes récurrentes peuvent être définies pour s’exécuter indéfiniment ou jusqu’à une date de fin spécifique. Les campagnes ponctuelles et immédiates ne comportent pas d’option de date de fin, puisqu’elles s’exécutent une seule fois.
- La planification ne prend pas en charge les intervalles de répétition personnalisés, tels que « toutes les 2 semaines » ou « tous les 3 jours ». Il ne prend pas non plus en charge la périodicité mensuelle relative, telle que « le deuxième lundi du mois ».

## Arrêter une campagne {#stop-campaign}

Vous pouvez arrêter une campagne qui envoie activement (une campagne « active ») directement à partir de la page des détails de la campagne.

>[!CAUTION]
>
>L’arrêt d’une campagne est permanent. Les destinataires cessent immédiatement de progresser dans la campagne et la campagne ne peut pas reprendre ni redémarrer par la suite. Pour envoyer à nouveau, vous devez créer une campagne et la lancer.

<!--

### Prerequisites

- [NEEDS INPUT - to confirm with engineer: does stopping a campaign require a specific role or permission, or can any user with campaign access do this?]

-->

### Comment arrêter une campagne

1. Ouvrez une campagne actuellement active.

1. Dans l’en-tête des détails de la campagne, cliquez sur **Arrêter la campagne**.

1. Cliquez sur **Arrêter** pour confirmer.
