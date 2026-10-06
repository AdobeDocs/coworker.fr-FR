---
title: Créer et exécuter une compétence de point de contrôle qualité dans Coworker
description: Découvrez comment utiliser une compétence Collègue personnalisée pour valider automatiquement les activations d’audience par rapport aux listes de suppression, aux limites de fréquence et aux normes de nommage avant le déploiement.
role: User
level: Beginner, Intermediate
doc-type: Feature Video
duration: 101
last-substantial-update: 2026-09-08
jira: KT-22379
source-git-commit: dbee38135a5491fd21b65fdbb70ba60d949d7560
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 1%
---

# Créer et exécuter une compétence de point de contrôle qualité à l’aide de compétences d’IA personnalisées

Les équipes marketing s’appuient sur des règles et des processus de gouvernance pour s’assurer que les audiences sont correctement activées. Avant de lancer une audience vers une destination, les équipes doivent souvent vérifier les listes de suppression, les limites de fréquence, les exigences de consentement et les conventions de nommage.
 
Le problème est que ces contrôles dépendent souvent des connaissances tribales et des révisions manuelles. Quand les processus vivent dans la tête des gens, des erreurs peuvent se produire.

Dans cette vidéo, vous découvrirez comment une compétence de collègue personnalisée agit comme un point d’activation, validant automatiquement les audiences par rapport aux normes d’activation de votre entreprise avant qu’elles ne soient déplacées en aval.

>[!VIDEO](https://video.tv.adobe.com/v/3503162/?learn=on&enablevpops)

## Exemple de compétence de point de contrôle de qualité d’activation
 
Vous pouvez créer votre propre compétence réutilisable **point de contrôle de la qualité de l’activation** en collant une invite dans Coworker. Les capacités de création de compétences de l’autre collègue convertissent l’invite en une compétence enregistrée dans **votre propre environnement**. Voici un exemple basé sur la démonstration vidéo.
 
L’essentiel est de définir **vos propres normes de réussite/échec** pour les trois points de contrôle de la gouvernance :
 
1. Suppression/Consentement
2. Limite De Fréquence
3. Convention d’affectation des noms
 
Le cadre reste le même pour tous. Personnalisez les sections marquées d’**`[...]`** pour qu’elles correspondent aux normes de votre entreprise.

## invite de Principal

> **Enregistrez-le en tant que compétence appelée « Point de contrôle de qualité d’activation »**

```text
It's a governance gate that runs a pre-activation checklist before any audience is sent to a destination.

It is read-only. It never activates, mutates, or copies anything.

Resolve the named audience and destination from our Knowledge Graph, evaluate the three gates below, then render one visual scorecard containing:

- An Alert banner
- One MetricCard per gate
- A DataTable with:
- Gate
- Status
- Finding
- Required Fix

Provide a single verdict:

- CLEARED only if all three gates pass
- BLOCKED if any gate fails

For every failed gate, provide the specific remediation needed.
 
All gates fail closed:

- Missing data = BLOCKED
- Never assume success when information is unavailable
 
Trigger phrases:

- "run the activation gate"
- "is this audience ready to activate"
- "pre-activation checklist"
- "can I activate to ..."

The three gates are:
 
[Paste Gate 1, Gate 2, and Gate 3 definitions here]
```

## Porte 1 : Suppression/Consentement
 
> Modifiez cette section pour qu’elle corresponde aux exigences de suppression et de consentement de votre organisation.
 

```text
Gate 1 – Suppression List

Pass only if a recognized suppression, opt-out, or consent audience is applied alongside the target audience.

Discover eligible lists using name patterns such as:

- suppress
- opt-in
- opt out
- consent
- do not contact
 
Because suppression lists may live in destination dataflows rather than audience metadata, require the marketer to confirm one is attached.
 
If no suppression or consent list exists anywhere in the sandbox, fail hard.
 
Our standard:

[Example: A consent audience is mandatory for all email and SMS destinations. For direct mail destinations it is optional.]
```

## Porte 2 : Limite De Fréquence

> Modifiez cette section pour qu’elle corresponde aux exigences de fréquence de diffusion de votre organisation.

```text
Gate 2 – Frequency Cap
 
Read the delivery frequency on the resolved destination.

Pass if:

- Frequency is present
- Frequency is bounded

Fail if:

- Frequency is blank
- Frequency is unbounded

Our standard:

[Example: Frequency must be DAILY or less frequent. Any hourly cadence or blank value is blocked.]
```

## Porte 3 : convention d’affectation des noms
 
> Modifiez cette section pour qu’elle corresponde aux règles de nommage des audiences de votre organisation.
 

```text
Gate 3 – Naming Convention

Evaluate the audience name programmatically.

Any rule violation causes failure.

Block names that:

- Contain "test"
- Contain "copy"
- Contain an auto-copy suffix such as _[6-hex]
- Contain timestamps
- Contain 24-character object IDs
- Start with a bare number or cryptic short code
- Are entirely lowercase
- Are excessively short or unclear
- Use generic defaults such as:
- Save audience
- Email
- New Accounts
- Lack a category–qualifier separator

Our standard:

[Example: [Line of Business] – [Criteria] in title case]

Example:

Mortgage – High Propensity Prospects

When blocked on naming, always propose a compliant replacement name.
```

## Instructions

### &#x200B;1. Personnaliser uniquement les sections entre crochets

Ne mettez à jour que les sections contenues dans **`[...]`**.
 
Ces sections définissent les normes de gouvernance spécifiques de l’organisation.
 
Tout le reste doit rester inchangé :

- Résolution de l’audience
- Évaluation du point de contrôle
- Rendu de la carte de score
- Logique de verdict


### &#x200B;2. Vérifier les conditions préalables
 
Cette compétence dépend des éléments suivants :
 
- Accès au graphique de connaissances
- Découverte de l’audience
- Découverte des destinations
- Découverte de la liste de suppression
- Prise en charge des artefacts visuels
- Bannière d’alerte
- Cartes de mesure
- Rendu du tableau de données

Si ces fonctionnalités ne sont pas disponibles dans l’environnement du client, la compétence ne peut pas s’exécuter comme prévu.

### &#x200B;3. Conserver la compétence en lecture seule

La compétence doit toujours rester en lecture seule.

Insérez explicitement cette exigence dans l’invite pour vous assurer que la compétence n’est jamais confondue avec un workflow d’activation.

Le point de contrôle Qualité de l’activation évalue uniquement le niveau de préparation à l’activation. Il n’active **pas** les audiences, ne modifie pas les configurations et ne copie pas les données.
