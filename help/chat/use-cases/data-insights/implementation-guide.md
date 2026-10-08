---
title: Planification de la mise en œuvre de Customer Journey Analytics ou de Streaming Media avec Coworker
description: Découvrez comment les compétences du guide d’implémentation de Coworker transforment une conversation de présentation en un plan d’implémentation personnalisé et ordonné avec des listes de contrôle exportables.
hold: true
source-git-commit: 2bf31c1348054a16ba7e7c0c26c0ff913634aa27
workflow-type: tm+mt
source-wordcount: '1239'
ht-degree: 1%
---

# Planification de la mise en œuvre avec un collègue

Adobe CX Enterprise Coworker comprend cinq compétences de guide d’implémentation, une pour chaque surface de produit : Customer Journey Analytics, une mise à niveau d’Adobe Analytics vers Customer Journey Analytics, Content Analytics (ACA), Marketing Campaign Analytics (MCA) et Streaming Media. Chaque compétence transforme une courte conversation sur la découverte en un plan d’implémentation personnalisé et adapté aux dépendances, complet avec une liste de contrôle interactive et des exportations prêtes à l’emploi, le tout dans une seule conversation avec le collègue.

Si vous vous tenez debout ou migrez vers l’un de ces produits, vous pouvez utiliser ces compétences pour obtenir un plan ordonné et détaillé, sans avoir à effectuer manuellement des recherches sur les exigences d’implémentation d’Adobe ni à créer un plan de projet à partir de zéro.

>[!NOTE]
>
>Tenez compte des points suivants :
>
>* Ces compétences de guide d’implémentation font partie d’un workflow plus vaste et facultatif : étapes d’implémentation ou de mise à niveau personnalisées (ces guides), implémentation (voir [ Générer une liste de contrôle d’implémentation avec des projets de collègues ](./intelligent-checklist.md)) et validation (par exemple, [Valider votre mise à niveau d’Adobe Analytics vers Customer Journey Analytics](./data-validation-aa-cja.md) ou [Valider votre implémentation Streaming Media](./streaming-media-validation.md)). Vous n’avez pas besoin d’utiliser les trois étapes. Par exemple, vous pouvez valider vos données sans jamais générer de plan ou de liste de contrôle.
>* Ces compétences n’accèdent pas à vos systèmes Adobe et n’apportent aucune modification. Ils vous aident à planifier la mise en œuvre. Il ne l’effectue pas et ne le vérifie pas auprès d’un client en ligne.

Utilisez ces compétences pour :

* Obtenez un plan personnalisé et ordonné pour mettre en place Customer Journey Analytics à partir de zéro, y compris les propriétaires, les estimations d’effort et les dépendances pour chaque étape.

* Obtenez un plan de migration pour passer d’Adobe Analytics à Customer Journey Analytics, y compris le mappage de parité des fonctionnalités d’Adobe Analytics, le séquencement de renvoi historique et un point de contrôle avant de désactiver Adobe Analytics.

* Obtenez un plan guidé pour la mise en œuvre de Content Analytics (ACA), y compris les licences, la confidentialité et la portée des PII, ainsi que l’assistant de configuration guidé.

* Obtenez un plan d’intégration pour Marketing Campaign Analytics (MCA) qui s’adapte à votre chemin d’ingestion, que vous utilisiez les connecteurs source Adobe, votre propre jeu de données ou une approche hybride.

* Obtenez un plan d’implémentation pour la collecte de médias en flux continu sur Edge, y compris la configuration des flux de données, l’implémentation SDK/API par plateforme et le modèle d’événement multimédia.

## Avant de commencer

<!-- FLAG: Best guess, not confirmed by source docs. Requirements doc doesn't state explicit prerequisites for starting a discovery conversation — verify with skills-overview.md or SME before publishing. -->

### Informations nécessaires

Pour démarrer une conversation sur le guide de mise en œuvre, vous avez besoin des éléments suivants :

* Lequel des cinq chemins de mise en œuvre s’applique à vous : Customer Journey Analytics (nouveau), une mise à niveau d’Adobe Analytics vers Customer Journey Analytics, Content Analytics (ACA), Marketing Campaign Analytics (MCA) ou Streaming Media.

* Informations de base sur votre environnement actuel, telles que si vous disposez déjà d’une implémentation d’Adobe Analytics, votre statut de licence ou votre chemin d’ingestion de données prévu. La conversation sur la découverte demande ces détails, mais les préparer accélère le processus.

### Limites

Avant d’utiliser ces compétences, gardez à l’esprit les restrictions suivantes :

* **Planification uniquement** : ces compétences n’accèdent pas à vos systèmes Adobe et n’apportent aucune modification. Ils n’effectuent pas l’implémentation ou ne la vérifient pas par rapport à un client actif.
* **Une surface de produit par compétence** : chaque compétence couvre un seul chemin d’implémentation. Si votre demande s’applique à une autre surface de produit, la compétence vous oriente vers la bonne au lieu de répondre directement.
* **Pas une expérience de suivi de projet à elle seule** : ces compétences génèrent un plan et des exportations, mais ne suivent pas le statut en cours, la collaboration ou les approbations par elles-mêmes. Pour suivre votre plan au fil du temps, transformez-le en projet Collègue à l’aide d’un playbook prédéfini. Voir [ Générer une liste de contrôle d’implémentation avec les projets de collègues](./intelligent-checklist.md).

## Démarrer une session de planification de l’implémentation

1. Connectez-vous à un collègue.

1. Sélectionnez [!UICONTROL **Nouvelle conversation**].

1. Dans le champ de texte, décrivez l’implémentation ou la migration que vous souhaitez planifier. Par exemple :

   **Invite**

   > M’aider à planifier l’implémentation de Customer Journey Analytics.

   Votre requête est acheminée vers la compétence correspondante du guide d’implémentation, ce qui lance une conversation interactive de découverte.

1. (Sous condition) Si la compétence ne peut pas déterminer le chemin d’implémentation qui vous concerne, répondez à la question d’éclaircissement qu’elle pose, puis poursuivez.

## Choisir le chemin d’implémentation

Chaque compétence du guide d’implémentation couvre une surface de produit.

### Customer Journey Analytics

Obtenez un plan d’implémentation personnalisé et ordonné pour mettre en place Customer Journey Analytics à partir de zéro, sans déploiement Adobe Analytics existant à migrer. Votre plan comprend les propriétaires, les estimations d&#39;effort et les dépendances pour chaque étape.

Exemples d’invites :

* M’aider à planifier l’implémentation de Customer Journey Analytics.
* Je suis en train de mettre Customer Journey Analytics en place à partir de zéro. Me créer un plan de mise en œuvre.

### Mise à niveau d’Adobe Analytics vers Customer Journey Analytics

Obtenez un plan de migration qui mappe la parité des fonctionnalités Adobe Analytics à Customer Journey Analytics, qui séquence le renvoi historique et qui comprend une validation et un point de contrôle exécuté en parallèle avant de désactiver Adobe Analytics.

Exemples d’invites :

* M’aider à planifier ma mise à niveau d’Adobe Analytics vers Customer Journey Analytics.
* Me créer un plan de migration d’Adobe Analytics vers Customer Journey Analytics.

### Content Analytics (ACA)

Obtenez un plan guidé pour la mise en œuvre de Content Analytics (ACA), y compris les licences, la confidentialité et la portée des PII, ainsi que l’assistant de configuration guidé. Comme ACA n’a pas de couverture DULE, CMK ou HIPAA, votre forfait inclut des étapes de contrôle de la confidentialité.

Exemples d’invites :

* M’aider à planifier l’implémentation de Content Analytics.
* Me créer un plan de mise en œuvre ACA.

### Marketing Campaign Analytics (MCA)

Obtenez un plan d’intégration pour Marketing Campaign Analytics (MCA) Essentials qui s’adapte à votre chemin d’ingestion, que vous utilisiez les connecteurs source Adobe, votre propre jeu de données ou une approche hybride, afin que les étapes de mappage et d’alignement des données de funnel correspondent à votre environnement.

Exemples d’invites :

* M’aider à planifier l’implémentation de Marketing Campaign Analytics.
* Me créer un plan d’intégration MCA à l’aide de mon propre jeu de données.

### Streaming Media

Obtenez un plan d’implémentation pour la collecte de médias en flux continu sur Edge, couvrant la configuration des flux de données, l’implémentation SDK/API par plateforme et le modèle d’événement multimédia, afin d’instrumenter correctement les sessions, les pings et les terminaisons pour la création de rapports Customer Journey Analytics et/ou Adobe Analytics.

Exemples d’invites :

* M’aider à planifier l’implémentation de Streaming Media.
* Créez-moi un plan pour instrumenter Streaming Media sur Edge.

## Consulter les résultats

Dans la même conversation, un collègue renvoie votre plan d’implémentation sous la forme d’une liste de contrôle interactive et d’un résumé.

**Liste de contrôle interactive**

Une liste de contrôle HTML qui regroupe les étapes de votre implémentation en phases et jalons. Pour chaque étape, la liste de contrôle comprend :

* Une estimation de l’effort
* Un propriétaire principal et tous les propriétaires annexes
* Dépendances matérielles sur d’autres étapes
* Si l’étape peut être ignorée
* Un lien vers la documentation Experience League ou developer.adobe.com appropriée

**Exports**

Téléchargez votre plan au format adapté à votre workflow :

| Exporter | Ce que cela inclut |
| --- | --- |
| CSV | Une liste simple d’étapes |
| Jira-import CSV | Étapes formatées avec des points d’histoire, une priorité et des libellés pour l’importation dans Jira. |
| WORKFRONT CSV | Étapes formatées avec des durées et des prédécesseurs pour l’importation dans Workfront |
| Markdown | Liste de contrôle que vous pouvez coller dans la documentation ou les wikis |

**Résumé in-chat**

En plus de la liste de contrôle, Coworker fournit un résumé en trois parties directement dans la conversation :

1. Aperçu de votre plan
1. Le tableau complet des étapes
1. Liens de téléchargement pour chaque exportation

## Création du plan

Chaque compétence du guide d’implémentation suit le même processus en quatre étapes :

* **Découverte** : une conversation échelonnée pose 5 à 9 ensembles de questions, spécifiques à votre chemin d’implémentation, pour en savoir plus sur votre environnement et vos objectifs.
* **Calculer** : un LLM détermine les étapes conditionnelles et les remplacements de dépendance qui s’appliquent à vos réponses. Il ne rédige pas le plan lui-même.
* **Assembler et rendre** : un processus déterministe résout les dépendances entre les étapes, les classe, calcule le chemin critique (la plus longue chaîne d’étapes dépendantes) et génère votre liste de contrôle et vos exportations.
* **Deliver** : Coworker fournit des liens de téléchargement et un résumé de votre forfait dans le chat.

Cette combinaison de découverte guidée et d&#39;assemblage déterministe signifie que votre plan est généré de manière cohérente à partir de vos réponses, plutôt que de manière libre et écrite.
