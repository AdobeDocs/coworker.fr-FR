---
title: Prise En Main Du Chat Entre Collègues Dans Playground
description: Découvrez comment utiliser le Module de conversation des collègues dans Playground pour découvrir comment les invites en langage naturel peuvent vous aider à apprendre, à étudier et à affiner votre travail.
hide: true
autotag-review: '2026-09-02T16:21:52.199Z'
TQID: 'https://experienceleague.adobe.com/a-9nJwwe4TFdi0ljwyyHfVfz-VqHL5lQbtmkU5P1Axw'
product_v2:
  - id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87
    internal-label: CX Enterprise
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
  - id: edbd1a0e-46c8-49da-8c10-dba9ec80bba9
    internal-label: Experience Platform
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fdddec33-c9cb-4459-b8b6-2664395a6f10
    internal-label: Real-Time Customer Data Platform
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
feature_v2:
  - id: 9c3a4e5f-6d7b-4c8a-8e9f-1b2c3d4e5f6a
    internal-label: Datasets
  - id: a4a9911c-3a92-4f17-a7f9-fe2eb3235fef
    internal-label: Monitoring
  - id: a50ad69b-1331-40e9-b634-531a085a6a54
    internal-label: Identities
  - id: a9eb38d5-9d89-492f-af4e-b968a07f2d91
    internal-label: Permissions
  - id: abc02dd6-664f-446a-9aaa-675bc0f2fe4a
    internal-label: Sources
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: ba929a52-9339-4154-9487-317dc875a3c7
    internal-label: Use cases
  - id: d21bd11d-08df-4cd6-ad8f-cb59a09de5c0
    internal-label: Sandboxes
  - id: d2a6cbf4-df32-480f-909e-b42f66dcb9f0
    internal-label: Places
  - id: de9975b2-c43a-4287-9698-4f4cad92b83f
    internal-label: Schemas
  - id: ebefeaba-efa6-45e2-ae01-f6171cdb8d1e
    internal-label: Tier
  - id: eec185bd-7d60-4193-ba3f-da427569936a
    internal-label: Destinations
  - id: f5a6b7c8-5003-4003-9003-500000000003
    internal-label: Services
topic_v2:
  - id: b4dd41a7-ccf8-4e9d-918e-acaab534a307
    internal-label: Data quality
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c4147b6e-073b-4d3c-9ab1-d60f2f4434ef
    internal-label: Behavioral data
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
    internal-label: Governance
source-git-commit: dbee38135a5491fd21b65fdbb70ba60d949d7560
workflow-type: tm+mt
source-wordcount: '1671'
ht-degree: 4%
---
# Prise en main du Chat avec un collègue dans Playground

Utilisez la discussion entre collègues dans Playground pour découvrir comment les invites en langage naturel peuvent vous aider à apprendre, à étudier et à affiner votre travail. Playground fournit des exemples de façons de démarrer une conversation afin que vous puissiez rapidement comprendre ce que le Chat des collègues peut faire.

>[!IMPORTANT]
>
>Utilisez les éléments suivants pour terminer cet exercice :
>
>- Lien : [ao.adobe.io](https://ao.adobe.io/)
>- Instance : AEP GenAI - VA7
>- Sandbox : `fsi-box`

## Démonstration d’AI Coworker : campagne de mise à niveau de la carte de crédit [!DNL weBank]

Cet exercice couvre Real-Time CDP et Adobe Journey Optimizer.

Vous êtes un stratège CX Enterprise chez **[!DNL weBank]**, une société de services financiers axée sur le numérique. Utilisez l’IA Coworker pour passer des données brutes à une campagne active, entièrement par le biais de la conversation.

## Partie 1 : comprendre votre entreprise

### 1.1 — Connaître l&#39;étendue des terres

**Invite**

> Me donner un aperçu de mon sandbox — de combien d’audiences, de jeux de données et de destinations dispose-t-on ?

**Résultat attendu**

Coworker renvoie un inventaire complet des sandbox en secondes :

| Ressource | Nombre |
| --- | --- |
| Audiences | 21 |
| Jeux de données | 30 |
| Schémas | 28 |
| Sources | 3 |
| Destinations | 1 (Amazon S3) |
| Parcours | 0 |

### 1.2 — Quelles audiences existent déjà ?

**Invite**

> Répertorier toutes mes audiences, triées par taille

**Résultat attendu**

Coworker répertorie 21 audiences triées par taille, de 8 012 profils à 0 :

| Catégorie | Audience | Profils |
| --- | --- | --- |
| Scores de propension | Mise à niveau de la carte de crédit élevée | 1,195 |
| Scores de propension | Méthode | 4,113 |
| Scores de propension | Faible | 8,012 |
| Propension hypothécaire | Élevé | 1,233 |
| Propension hypothécaire | Méthode | 4,141 |
| Propension hypothécaire | Faible | 7,946 |
| Niveaux de valeur de compte | +500K | 4,377 |
| Niveaux de valeur de compte | 250-500K | 4,537 |
| Niveaux de valeur de compte | 100 À 250 000 | 2,666 |
| Niveaux de valeur de compte | 50 À 100 000 | 894 |
| Niveaux de valeur de compte | &lt;50K | 846 |
| Données démographiques | Femme | 6,719 |
| Données démographiques | Homme | 6,601 |
| Géographie | Côte Est | 2,260 |
| Géographie | Côte Ouest | 1,740 |
| Opt-in du canal | E-mail | 6,597 |
| Opt-in du canal | SMS | 6,675 |
| Date de naissance | Anniversaire ce mois | 0 |
| Date de naissance | Dans les 7 jours | 0 |
| Date de naissance | Today | 0 |
| Date de naissance | 30 prochains jours | 0 |

Toutes les audiences d’anniversaire affichent actuellement 0, car elles dépendent du temps.

### 1.3 — Quelles données alimentent ces audiences ?

**Invite**

> Quels jeux de données ai-je qui contiennent des données client ?

**Résultat attendu**

Coworker identifie deux jeux de données métier clés et les jeux de données système associés :

| Jeu de données | Description |
| --- | --- |
| **weBank : CRM** | Données de profil/compte client (profil + identité activé) |
| **weBank : actions des clients** | Données d’événement comportemental (profil + identité activé) |

Les jeux de données Journey Optimizer système pour les signaux d’engagement incluent le suivi des e-mails, le suivi des notifications push, le consentement et les commentaires des messages.

## Partie 2 : Découvrir les bons champs

### 2.1 — Rechercher les champs de valeur de compte

**Invite**

> Quels champs sont disponibles en rapport avec la valeur ou le solde du compte ?

**Résultat attendu**

Coworker affiche le champ principal et les champs associés dans le jeu de données **weBank : CRM** :

| Champ | Remarques |
| --- | --- |
| `_aepgenai_va7.fsiBankAccountDetails.totalAccountValue` | Champ de Principal ; utilisé dans les 5 audiences de niveau Valeur du compte |
| `numberOfAccounts` | Champ associé |
| `accountType` | Champ associé |
| `currentStatement` | Champ associé |
| `actionAmount` | Champ associé |

### 2.2 — Rechercher les champs de carte de crédit

**Invite**

> Rechercher des champs liés à la carte de crédit ou au type de carte

**Résultat attendu**

Coworker identifie ces champs dans le schéma **weBank : CRM** :

| Champ | Description |
| --- | --- |
| `_aepgenai_va7.fsiBankAccountDetails.creditcardType` | Stocke le type de carte (Visa, Mastercard, Amex) |
| `_aepgenai_va7.fsiBankAccountDetails.creditcardHolder` | Nom du détenteur de carte |

### 2.3 — Champs géographiques

**Invite**

> Existe-t-il un champ pour l’État d’origine ou la région ?

**Résultat attendu**

Coworker identifie les champs géographiques dans le jeu de données **weBank : CRM** :

| Champ | Remarques |
| --- | --- |
| `homeAddress.state` | Abréviation d’État des États-Unis, utilisée dans les sections Lives on East Coast et Lives on West Coast. |
| `homeAddress.stateProvince` | Également trouvé |
| `homeAddress.region` | Également trouvé |
| `placeContext.geo.stateProvince` | Également trouvé |

## Partie 3 : trouver l’audience appropriée pour une campagne de réactivation

### 3.1 — Demandez à l&#39;IA de vous aider à trouver la bonne audience

**Invite**

> Aidez-moi à trouver ou à créer l’audience appropriée pour une campagne de réactivation de carte de crédit. Je souhaite cibler les clients qui ont obtenu un score de propension élevé ou moyen pour une mise à niveau de carte de crédit, mais qui n’ont pas encore pris de mesures

**Résultat attendu**

Un collègue trouve deux audiences candidates qui n’ont jamais été ciblées dans un parcours ou une destination :

| Audience | Profils |
| --- | --- |
| Mise à niveau de la carte de crédit élevée | 1,195 |
| Medium de mise à niveau des cartes de crédit | 4,113 |

Options recommandées :

| Option | Approche |
| --- | --- |
| **A** | Utilisez les deux directement avec l’embranchement par parcours : offre agressive pour High, nurture pour Medium |
| **B** | Créer un segment dérivé de segments avec une logique de mise à niveau-exclusion pour une gestion plus épurée |

Taille combinée : environ 5 308 profils

### 3.2 — Créer l&#39;audience de précision

**Invite**

> Créez une audience de clients qui se trouvent dans l’audience « Propensions : mise à niveau élevée des cartes de crédit » ET qui ont une valeur de compte de plus de 250 000 $ ET qui ont choisi d’envoyer un e-mail

Nommez-le **Mise à niveau vers la version Platinum - Éligible aux e-mails de valeur élevée** → Sélectionnez un plan de → par lots pour l’approuver.

**Résultat attendu**

Le collaborateur calque la propension à l’apprentissage automatique, la valeur financière et l’éligibilité des canaux en un seul segment de précision, un travail qui nécessiterait normalement un ticket d’équipe de données.

### 3.3 — Estimation de la taille et de la cascade

**Invite**

> Quelle est la taille de cette audience ? Montrez-moi la répartition de la cascade.

**Résultat attendu**

Coworker renvoie une estimation du nombre de profils en temps réel et un graphique en cascade visuel :

| Étape de filtrage | Résultat |
| --- | --- |
| Mise à niveau de la carte de crédit à forte propension | Environ 1 195 profils |
| + Valeur du compte supérieure à 250 000 $ | Réduit davantage |
| + Opt-In D’E-Mail | Nombre adressable final |

Cela indique exactement quelle condition est le plus grand filtre et s’il faut assouplir les critères.

### 3.4 — Rechercher des audiences similaires

**Invite**

> Existe-t-il des audiences existantes similaires à celle que je viens de créer ?

**Résultat attendu**

Coworker confirme qu’il n’existe aucune audience combinée unique, mais tous les blocs de création sont déjà présents :

| Bloc de création | Détails |
| --- | --- |
| Propension : mise à niveau des cartes de crédit élevée | Score ≥ 90 |
| Valeur du compte : 250-500K | Audience existante |
| Valeur Du Compte : +500K | Audience existante |
| Souscription Aux E-Mails | `consents.marketing.email.val = "y"` |

Un collègue confirme qu’il n’y a aucun risque de duplication et recommande de continuer.

## Partie 4 : création du Parcours

### 4.1 — Trouvez des idées de parcours fondées sur vos données

**Invite**

> En fonction des cas d’utilisation populaires dans les services financiers, suggérez des parcours à gain rapide que je peux créer avec les audiences que j’ai

**Résultat attendu**

Coworker suggère cinq idées de parcours concrètes fondées sur des audiences réelles :

| idée de parcours | Audiences |
| --- | --- |
| Touche de fidélité d’anniversaire | Anniversaire dans les 7 jours + Niveau de valeur du compte |
| Entretien de la mise à niveau des cartes de crédit | Mise à niveau CC élevée + opt-in aux e-mails |
| Portée régionale du prêt hypothécaire | Prêt hypothécaire élevé + côte Est/Ouest |
| Mise à niveau des conseils sur le niveau de richesse | Valeur Du Compte : +500K |
| Opt-In Cross-Channel Activation | Opt-in des e-mails moins Opt-in des SMS |

### 4.2 — Création du parcours de mise à niveau de la carte de crédit

**Invite**

> Créez un parcours à l’aide de l’audience « Mise à niveau vers la version Platine - Éligible aux e-mails de valeur élevée ». Envoyez une notification push présentant les avantages de la carte platine weBank. Patientez 3 jours. Si le client n&#39;a pas postulé, envoyez un SMS avec une offre à durée limitée de 0% APR pendant 12 mois sur les transferts de solde. Patientez encore 5 jours. Si toujours aucune application, envoyez une notification push finale avec une invitation de banque personnelle.

Vérifier le plan → Approuver le plan → Accorder des autorisations

**Résultat attendu**

Coworker crée un parcours complet à 3 contacts et à 2 canaux à partir d’une seule description en langage naturel, y compris les temporisateurs d’attente, les contrôles de condition et les offres croissantes.

### 4.3 — Bonus : création d&#39;un parcours à partir d&#39;une image

**Invite**

> Créer ce parcours à partir de l&#39;image que j&#39;ai téléchargée

**Résultat attendu**

Il lit l’image chargée (y compris les nœuds, les canaux, les temps d’attente et les conditions) et génère le parcours complet dans Journey Optimizer. Cela transforme un artefact de planification directement en parcours déployable.

### 4.4 — Vérification des conflits

**Invite**

> Existe-t-il des parcours actifs susceptibles d’entrer en conflit avec le parcours que je viens de créer ?

**Résultat attendu**

Coworker vérifie automatiquement le chevauchement des audiences, les collisions de planification et la saturation des canaux dans tous les parcours actifs.

## Partie 5 : transformer les abandons Parcours en une nouvelle audience

### 5.1 — Identifier le point de restitution

**Invite**

> Montrez-moi le parcours que je viens de créer et identifiez l’étape qui a la plus forte chute

**Résultat attendu**

Coworker analyse les événements d’étape de parcours et surfacique le nœud avec le taux de sortie le plus élevé. Par exemple :

> 68 % des profils ayant reçu le premier e-mail ne l’ont jamais ouvert et l’ont quitté avant l’étape SMS.

### 5.2 — Créer une audience de type « drop-off »

**Invite**

> Transformez ces abandons de parcours en une nouvelle audience, celle des personnes qui ont rejoint le parcours de mise à niveau vers la version Platine mais n’ont jamais atteint l’étape SMS

Nommez-le **Mise à niveau vers la version Platinum - E-mail des non-répondeurs** → Sélectionnez le lot → approuver le plan

**Résultat attendu**

Coworker crée une nouvelle audience basée sur les données comportementales du parcours, c’est-à-dire les profils qui sont entrés dans le parcours mais n’ont pas atteint l’étape SMS. Cette audience est immédiatement utilisable pour une campagne de relance.

### 5.3 — Réactiver les abandons

**Invite**

> Créez un parcours de réactivation pour l’audience « Mise à niveau vers la version Platine - E-mail des non-répondeurs ». Essayez une approche différente : commencez par envoyer une notification push mettant en évidence une offre de 75 000 points bonus à durée limitée, patientez 2 jours, puis envoyez une invitation par publipostage direct pour visiter leur succursale locale.

Vérifier le plan → Approuver le plan → Accorder des autorisations

**Résultat attendu**

Coworker crée un parcours de récupération dédié en utilisant différents canaux et messages pour les non-répondeurs. Vous avez maintenant bouclé la boucle sur une fuite de conversion, entièrement par conversation.

## Partie 6 : contrôle qualité et validation automatisés

### 6.1 — Actualisation des données et contrôle de l’intégrité de l’ingestion

**Invite**

> Existe-t-il des problèmes de qualité des données avec les jeux de données qui alimentent mes audiences ? Vérifiez l’intégrité de l’ingestion pour weBank : CRM et weBank : Actions des clients

**Résultat attendu**

Un collègue signale l’intégrité de l’ingestion pour chaque jeu de données :

| Jeu de données | État | Détails |
| --- | --- | --- |
| **weBank : CRM** | Bon | 39 enregistrements ingérés, 32 au profil, aucun échec |
| **weBank : actions des clients** | Indicateur mineur | 441 enregistrements ingérés ; 35 avaient des horodatages expirés ; environ 8 % étaient exclus en raison de la période de durée de vie |

Recommandation : vérifiez les paramètres de TTL ou recherchez les enregistrements obsolètes dans le système source.

### 6.2 — Valider le parcours avant publication

**Invite**

> Consultez le parcours de mise à niveau vers la version Platine pour identifier les erreurs ou les problèmes de qualité — vérifiez les temps d’attente manquants, les chemins d’accès d’impasse, les configurations de canal manquantes et les écarts d’éligibilité d’audience

**Résultat attendu**

Un collègue inspecte la structure du parcours et signale des problèmes tels que :

| Type d&#39;événement | Exemple |
| --- | --- |
| Chemins d’accès dans l’impasse | Chemins qui ne se terminent pas par un nœud de fin |
| Configuration des canaux | Configurations de surface de canal manquantes dans les actions |
| Minuteurs d’attente | Minuteurs qui peuvent entraîner des problèmes de SLA |
| Contenu | Nœuds à contenu manquant |

## Partie 7 : Surveillance et gouvernance

### 7.1 — Suivre l’intégrité de l’audience au fil du temps

**Invite**

> Montrez-moi comment l’audience « Propensions : mise à niveau élevée des cartes de crédit » a changé au cours des 30 derniers jours

**Résultat attendu**

Coworker renvoie une vue de série temporelle de la croissance ou du déclin de l’audience avec une analyse des tendances, ce qui vous aide à identifier si la notation du modèle ML dérive ou si les modifications des données en amont affectent la qualification.

### 7.2 — Diagnostiquer un changement

**Invite**

> Pourquoi l’audience « Valeur du compte : +500K » a-t-elle diminué récemment ?

**Résultat attendu**

Un collègue effectue une analyse causale en décomposant la modification entre :

| Facteur | Question |
| --- | --- |
| Actualisation des données | Y a-t-il eu un écart d’ingestion ? |
| Fusionner les modifications de politique | L’assemblage des profils a-t-il changé ? |
| Modifications de la source en amont | Les données CRM ont-elles cessé de circuler ? |
| Comportement réel du client | La valeur des comptes a-t-elle vraiment diminué ? |

Cela remplace 1 à 2 jours de tri des analystes.

