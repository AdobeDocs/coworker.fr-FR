---
description: Guide de référence de l’interface de conversation des collègues, couvrant la navigation, la zone de saisie, les réponses, l’historique de conversation, ainsi que la configuration des compétences, des serveurs MCP et de la mémoire.
title: Guide de l’interface utilisateur de la conversation avec un collègue
jira: KT-22106
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
feature_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: dbee38135a5491fd21b65fdbb70ba60d949d7560
workflow-type: tm+mt
source-wordcount: '1719'
ht-degree: 4%
---
# Guide de l’interface utilisateur du {#ui-guide}

Familiarisez-vous avec l’interface de conversation des collègues. Ce guide couvre tous les aspects, de l’accès à l’application à la navigation dans l’espace de travail, en passant par la manière de tirer le meilleur parti des conversations, de gérer votre historique et de personnaliser votre configuration.

>[!VIDEO](https://video.tv.adobe.com/v/3498558?learn=on)

## Accéder au chat des collègues

Lorsque votre entreprise obtient l’accès à Coworker, vous pouvez utiliser ses fonctionnalités au moyen de l’expérience immersive ou d’une expérience intégrée au produit.

>[!NOTE]
>
>L’expérience intégrée au produit est accessible via l’icône Coworker ![icône Coworker](./assets/icon-coworker.png) en haut à droite. Les détails de l’expérience immersive sont [décrits ci-dessous](#immersive).

Le tableau suivant capture la date à laquelle ces expériences seront disponibles pour chaque application CX Enterprise.

| Application CX Enterprise | Expérience immersive | Expérience intégrée au produit |
|---|---|---|
| RTCDP | Disponible maintenant | Bientôt disponible |
| AJO | Disponible maintenant | Bientôt disponible |
| CJA | Disponible maintenant | Bientôt disponible |
| Workfront | Disponible maintenant | Prochainement : <br><br>* début septembre 2026 dans l’instance d’aperçu pour certains administrateurs système Workfront éligibles <br><br>* mi-septembre 2026 dans l’instance de production pour les clients Workfront à version rapide éligibles <br><br>* mi-octobre 2026 dans l’instance de production pour les clients Workfront à version trimestrielle éligibles |
| Cible | Disponible maintenant | Disponible maintenant |
| AEM | Disponible maintenant | Bientôt disponible |
| Marketo Engage | Disponible maintenant | Bientôt disponible |

### Expérience immersive {#immersive}

Accédez au Chat des collaborateurs en accédant à [&#128279;](https://experience.adobe.com/#/coworker) et en vous connectant avec vos informations d’identification Adobe.

Vous pouvez également y accéder en sélectionnant **Collègue** dans le sélecteur d’applications situé dans l’en-tête supérieur de CX Enterprise.

![Accès à Coworker à partir du sélecteur d’applications CX Enterprise](./assets/ui-guide-1.png)

## Choisissez votre organisation et votre sandbox

Votre contexte actuel s’affiche au bas du rail de navigation de gauche, sous votre nom et votre image de profil. Le contexte détermine les données, les compétences et les outils connectés auxquels une conversation peut accéder. Vous devez donc le confirmer avant de commencer.

Sélectionnez votre nom pour ouvrir le menu du compte, où vous pouvez changer de contexte et modifier les paramètres de l’espace de travail :

| Élément d’interface | Description |
| --- | --- |
| Thème | Enchaînez le thème de l’interface entre Lumière et Sombre. |
| Paramètres | Ouvrez les paramètres de l’espace de travail pour afficher les détails de votre compte et d’autres paramètres. |
| Sélecteur d’organisation | Changer l’organisation IMS sur laquelle le collaborateur s’exécute. |
| Sélecteur de sandbox | Basculez vers le sandbox AEP actif. |
| Applications CX | Accédez à une autre application CX Enterprise connectée à votre compte . |
| Se déconnecter | Déconnectez-vous de votre compte Adobe. |

![Le menu Compte avec le sélecteur d’organisation ouvert](./assets/ui-guide-2.png)

![Le menu Compte avec le sélecteur de sandbox ouvert](./assets/ui-guide-3.png)

## Navigation dans l’interface

L’interface de CX Coworker comporte deux zones principales : le rail de navigation à gauche et la zone de travail de conversation qui remplit le reste de la fenêtre.

![Écran d’accueil](./assets/ui-guide-4.png)

## Le rail de navigation

Le rail vous donne accès à chaque partie du produit et à vos travaux récents.

| Élément d’interface | Description |
| --- | --- |
| Nouvelle conversation | Démarrez une nouvelle conversation. Votre conversation actuelle est enregistrée dans l’historique. |
| Accueil | Revenez au message d’accueil, à la zone de saisie et aux invites suggérées. |
| Conversations | Ouvrez l’historique complet des conversations pour rechercher, épingler, archiver ou supprimer des conversations. |
| Configurations | Gérez les compétences, les serveurs MCP, les places de marché, les modules externes et la mémoire. |
| Épinglé | Conversations que vous avez démarrées et conservées en haut de l’écran pour un accès rapide. Sélectionnez Afficher tout pour les afficher sur la page Conversations . |
| Récents | Vos conversations les plus récentes Sélectionnez Afficher tout pour ouvrir la page Conversations . |

## L’écran d’accueil

L’écran d’accueil est l’endroit où vous commencez. Elle affiche un message d’accueil personnalisé, la zone de saisie et un ensemble d’invites suggérées, tirées de ce que le chat des collègues peut vous aider à faire dans votre sandbox.

### Invites suggérées

Sous Suggérées pour vous, CX Coworker répertorie les exemples de tâches. Sélectionnez une suggestion pour la charger dans la zone de saisie, puis modifiez-la avant de l’envoyer ou envoyez-la en l’état. Les suggestions sont un moyen rapide de voir les types de travail pris en charge par le Module de conversation des collaborateurs : déplacement de schémas entre des sandbox, recherche d’anomalies dans un parcours, validation d’un jeu de données, etc.

### Mentions des entités

Les invites suggérées et vos propres messages peuvent référencer des objets spécifiques dans votre sandbox à l’aide des mentions d’entité telles que +[schéma], +[parcours ] et +[jeu de données]. Une mention d’entité indique à Coworker Chat exactement quel objet vous voulez dire, de sorte que vous pouvez ajouter vos propres mentions en tapant **+**.

## La zone de saisie de conversation

La zone de saisie (intitulée « Demandez à votre collègue ce que vous voulez ») se trouve à l’endroit où vous tapez. Sous le champ de texte se trouve une barre d’outils pour les pièces jointes, le comportement de réponse, la saisie vocale et l’envoi.

| Élément d’interface | Description |
| --- | --- |
| + (Joindre) | Ouvrez le menu Joindre pour ajouter un fichier ou un objet de données au message. |
| Mode Plan | Demandez à la discussion avec un collègue de proposer un plan étape par étape et de faire une pause pour votre approbation avant qu’il n’agisse. Désactivez-le pour permettre à Coworker Chat d&#39;agir directement. |
| Vue Transcription | Contrôlez la proportion de l’activité interne du Chat des collègues qui s’affiche : normale, focalisée ou détaillée. |
| Microphone | Dictez votre message à l’aide d’une entrée vocale. Sélectionnez à nouveau pour arrêter l’enregistrement. |
| Envoyer | Envoyez le message. Lorsque le Chat Coworker répond, cela devient un contrôle d’arrêt que vous pouvez utiliser pour interrompre. |

### Joindre des fichiers et des données

Sélectionnez + pour joindre un contexte à votre message :

- Joindre un fichier : chargez un fichier que le Module de conversation des collaborateurs peut lire et référencer dans sa réponse.
- Ajouter des données ou un objet : référencez un objet de votre sandbox, tel qu’un jeu de données ou un schéma, afin que la conversation avec les collègues fonctionne avec vos données actives.

![Le menu Joindre](./assets/ui-guide-5.png)

### Mode Plan

Activez le mode Plan lorsqu’une tâche est complexe ou modifie les données et que vous souhaitez d’abord examiner l’approche. Le Chat des collègues répond avec un plan et attend votre approbation avant de l&#39;exécuter. Lorsque le mode Plan est désactivé, le Chat des collaborateurs passe directement au travail.

![Mode Plan activé dans la barre d’outils de saisie](./assets/ui-guide-6.png)

### Vue Transcription

La vue de la transcription définit la mesure dans laquelle le raisonnement et l’activité de l’outil du Chat des collègues apparaissent en ligne dans la conversation :

| Élément d’interface | Description |
| --- | --- |
| Normal | Une vision équilibrée : les principales étapes de réflexion et l&#39;activité des outils sont résumées. |
| Focus | Une vue simplifiée qui masque la plupart des étapes intermédiaires afin que vous puissiez voir principalement la réponse. |
| Détaillé | Le détail complet : chaque étape de réflexion, la charge de compétence, la lecture de fichier et la requête. |

![Choix de la vue Transcription](./assets/ui-guide-7.png)

## Utiliser les réponses

Lorsque vous envoyez un message, la discussion avec les collaborateurs effectue la tâche en plein écran, puis renvoie sa réponse. Une réponse peut inclure un raisonnement, un enregistrement des outils utilisés et un ou plusieurs artefacts.

![Une réponse en cours](./assets/ui-guide-8.png)

### Pensée et activité

Pendant qu’il fonctionne, le Chat des collègues montre ce qu’il fait afin que vous puissiez suivre (et vérifier) son processus :

- Blocs de réflexion : étapes réductibles intitulées « Réfléchi pendant » suivies du nombre de secondes (ou millisecondes). Développez-en un pour lire le raisonnement de Coworker Chat.
- Activité de compétence : les entrées telles que Compétence chargée indiquent la capacité spécialisée apportée par la conversation des collaborateurs pour la tâche.
- Activité de fichier et de requête : des entrées telles que Lecture de fichier et Requête Ran 1 enregistrent les fichiers lus par Coworker Chat et les requêtes exécutées, chacune avec le temps nécessaire.

>[!TIP]
>
>Utilisez la vue Transcription détaillée pour voir chaque étape ou la vue Focus pour les masquer.

### Artefacts

Les résultats produits par la conversation avec le collaborateur (tels qu’un tableau d’audiences) s’affichent sous forme de cartes d’artefact dans la réponse. À partir d’une carte d’artefact , vous pouvez télécharger les artefacts de table sous forme de fichier CSV. Lorsqu’une réponse comprend plusieurs artefacts, utilisez les commandes du carrousel (Précédent/Suivant et le nombre, par exemple 1/1) pour vous déplacer entre eux.

### Lire l’analyse

Sous ses artefacts, le Chat des collègues résume ce que signifient les résultats, en mettant en évidence les résultats notables et en suggérant des actions de suivi que vous pouvez entreprendre ensuite.

![Réponse terminée avec le tableau et le résumé de l’artefact](./assets/ui-guide-9.png)

### Envoyer des commentaires et copier les réponses

Chaque réponse comporte des commandes pour la classer et la réutiliser :

- Pouces vers le haut / Pouces vers le bas : évaluez la réponse pour améliorer les réponses futures.
- Copier : copie la réponse en utilisant Copier en tant que Markdown (conserve la mise en forme) ou Copier en tant que texte brut.

![Menu Copier](./assets/ui-guide-10.png)

## Gérer vos conversations

Sélectionnez Conversations dans le rail de navigation pour ouvrir votre historique complet. Les conversations sont regroupées par date, et chaque ligne affiche le titre de la conversation et le nombre de tours qu&#39;elle contient.

| Élément d’interface | Description |
| --- | --- |
| Rechercher par titre | Rechercher une conversation passée par nom. |
| Afficher épinglé | Afficher uniquement les conversations que vous avez démarrées. |
| Afficher les archives | Afficher les conversations archivées. |
| Nouvelle conversation | Démarrer une nouvelle conversation. |
| Menu des lignes (...) | Dans n’importe quelle conversation, démarrez (épingle), renommez, archivez ou supprimez-la. |

![Page Conversations](./assets/ui-guide-11.png)

## Configurations

Les configurations vous permettent de personnaliser ce que le Module de conversation des collègues peut faire. Il comporte cinq onglets : Compétences, Serveurs MCP, Marketplaces, Modules externes et Mémoire.

### Compétences

Les compétences sont des fonctionnalités spécialisées que le chat des collaborateurs appelle automatiquement lorsqu’elles sont pertinentes ou que vous pouvez déclencher en saisissant / dans le chat. L’onglet Compétences répertorie toutes les compétences installées et vous permet d’en ajouter d’autres.

- Ajouter Source : installation de compétences à partir d’une nouvelle source.
- Rechercher : recherche une compétence par nom.
- Changer la vue : basculer entre les mises en page de grille et de liste en utilisant le bouton afficher.

![Onglet Compétences](./assets/ui-guide-12.png)

Sélectionnez une compétence pour afficher ses détails : le plug-in auquel elle appartient, une description du moment où Coworker Chat l’utilise et tous les fichiers qu’elle inclut. Sélectionnez Afficher le fichier SKILL.md pour lire la définition complète de la compétence ou Supprimer le Source pour la désinstaller.

![Vue détaillée de la compétence montrant les fichiers annexes](./assets/ui-guide-13.png)

![Visionneuse SKILL.md](./assets/ui-guide-14.png)

### Serveurs MCP

Les serveurs MCP (Model Context Protocol) connectent le Module de conversation des collaborateurs à des outils et services externes, tels que Adobe Journey Optimizer, Real-Time CDP, Target et Workfront. L’onglet Serveurs MCP répertorie tout ce qui est actuellement connecté et le nombre de connexions actives.

- Ajouter un serveur : connectez un nouvel outil ou service externe.

Chaque carte affiche le nom du serveur, son point d’entrée et toute balise décrivant ce qu’elle fournit.

![Onglet Serveurs MCP](./assets/ui-guide-15.png)

### Places de marché

Les Marketplaces sont des registres de plug-ins à partir desquels vous pouvez naviguer et installer. L’onglet Marketplaces vous permet d’ajouter des registres et de les filtrer par groupe.

- Ajouter un marché : enregistrer un nouveau marché de plug-ins.
- Rechercher / Filtrer par groupe : affinez la liste pour trouver un marketplace.

Chaque marketplace affiche sa source et un statut Prêt une fois qu&#39;elle est disponible à l&#39;installation.

![Onglet Marketplaces](./assets/ui-guide-16.png)

### Plug-ins

Les plug-ins étendent le Module de conversation des collègues grâce à des compétences groupées et à des serveurs MCP installés et gérés ensemble en tant qu’unité. L’onglet Plug-ins indique ce qui est installé et vous permet d’en ajouter d’autres à partir de vos places de marché.

- Parcourez les Marketplaces : trouvez de nouveaux plug-ins à installer.
- Désinstaller : supprime un plug-in installé et tout ce qu’il regroupe.
- Filtrez par marketplace : découvrez quels plug-ins sont issus de quel registre.

![Onglet Modules externes](./assets/ui-guide-17.png)

### Mémoire

La mémoire permet au Chat Coworker de mémoriser vos préférences dans les conversations afin que ses réponses restent pertinentes et personnelles au fil du temps.

- Activer la mémoire : active ou désactive la mémoire intersessions.
- Préférences stockées : les préférences que le chat des collaborateurs a apprises et enregistrées. Chaque entrée peut être modifiée, supprimée ou inspectée, et les entrées peuvent être filtrées par catégorie.
- Historique des mémoires enregistrées : chronologie des modifications apportées à vos mémoires stockées.

![Onglet Mémoire](./assets/ui-guide-18.png)
