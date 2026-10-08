---
title: Valider des données Customer Journey Analytics avec les compétences de validation des données de Coworker
description: Découvrez comment valider les données Customer Journey Analytics à l’aide des compétences de validation des données dans Coworker et résoudre les problèmes avant de créer des tableaux de bord.
feature: AI Tools
role: User
level: Beginner, Intermediate
doc-type: Feature Video
duration: 330
last-substantial-update: 2026-09-16
jira: KT-22622
source-git-commit: 2bf31c1348054a16ba7e7c0c26c0ff913634aa27
workflow-type: tm+mt
source-wordcount: '628'
ht-degree: 0%
---
# Validez les données Customer Journey Analytics avec les compétences en validation de données dans [!DNL Coworker]

La qualité des données est la base de rapports précis dans Adobe Customer Journey Analytics (CJA). Avant de créer des mesures, des tableaux de bord, des segments ou des parcours client, il est essentiel de déterminer si les données Adobe Experience Platform sous-jacentes (AEP) sont dignes de confiance.

Dans cette vidéo, vous apprendrez à utiliser la **compétence Validation des données dans Adobe CX Enterprise Coworker** pour évaluer rapidement la qualité des jeux de données qui alimentent votre implémentation de Customer Journey Analytics, sans écrire de requêtes ni inspecter manuellement les données.

>[!VIDEO](https://video.tv.adobe.com/v/3503519/?learn=on&enablevpops)

## Découvrez les jeux de données sous-jacents à vos rapports CJA

Découvrez comment Coworker peut identifier :

- Les jeux de données connectés à Customer Journey Analytics
- Connexions et vues de données associées à un sandbox spécifique
- Les jeux de données alimentant activement les rapports
- Caractéristiques clés du jeu de données, telles que le statut de diffusion en continu et les espaces de noms d’identité

En sachant exactement quels jeux de données alimentent vos rapports, vous pouvez concentrer les efforts de validation là où ils comptent le plus.

## Explorer les schémas du jeu de données et les champs disponibles

Découvrez comment inspecter les schémas de jeux de données directement depuis Adobe Experience Platform.

Un collègue récupère les détails et les surfaces du schéma :

- Commerce et champs de transaction
- Informations sur les produits
- Données d’interaction web
- Champs d’identité
- Attributs de campagne et marketing
- Dimensions de l’appareil et géographiques

Vous obtenez ainsi un inventaire des champs disponibles à des fins d’analyse, et vous pouvez mettre en évidence la différence entre les champs qui existent dans un schéma et ceux qui contiennent des données utilisables.

## Valider la qualité de l’identité

Les données d’identité sont essentielles pour Customer Journey Analytics, car elles prennent en charge le compte rendu des performances au niveau de la personne et l’analyse de parcours cross-canal.

Dans cette vidéo, vous découvrirez comment Coworker :

- Valide les champs d’identité
- Vérifie les valeurs nulles et l’exhaustivité des données
- Évalue la qualité de l’identifiant
- Attributs d’identité de surfaces manquants ou indisponibles

L’exemple de validation indique que les identités ECID et d’e-mail sont entièrement renseignées et valides dans l’exemple, tandis que l’Analytics ID n’a pas pu être récupéré. Cela fournit un signal utile pour décider quels identifiants peuvent prendre en charge l’assemblage des profils et les rapports.

## Analyse de la qualité des champs individuels

Un champ peut exister dans un jeu de données mais ne pas convenir à la création de rapports.

Regardez comment Coworker valide un champ de suivi de campagne et génère des rapports :

- Taux de population
- Pourcentages nuls
- Cohérence des données
- Détection de valeur non valide

Dans l’exemple, les valeurs du code de suivi présentes sont claires et cohérentes, mais environ 85 % des lignes sont nulles. Un angle mort important apparaît alors au niveau des rapports avant qu’une dimension CJA ou une mesure de campagne ne soit créée sur le champ.

## Effectuer une validation de jeu de données optimisée par l’IA

Plutôt que de valider des champs individuels un par un, Coworker peut évaluer un jeu de données entier.

Vous apprendrez comment les compétences en validation de données :

- Sélectionne les champs importants à valider
- Évalue l&#39;exhaustivité et la qualité
- Compare l’intégrité des données entre les champs.
- Met en évidence les points forts et les risques potentiels liés aux rapports

Les résultats de la validation fournissent une carte de viabilité pour CJA. Les champs propres tels que le nom de la page web et le code de messagerie peuvent être prêts pour le reporting. Les champs épars tels que la valeur d&#39;achat, le nom de la campagne et le code de suivi nécessitent une enquête.

## Identification des risques liés au chiffre d’affaires et à l’attribution

La vidéo montre également comment la validation des données peut découvrir des problèmes qui affectent la précision des rapports, notamment :

- Données de campagne fragmentées
- Informations d’attribution manquantes
- Valeurs de transaction incomplètes
- Écarts dans la mesure des revenus

Dans le jeu de données affiché, le nombre d’achats est disponible, mais le montant des commandes n’est pas renseigné de manière fiable. Il s’agit d’un problème à examiner avant d’approuver la création de rapports de revenus.

## Importance de la validation des données pour Customer Journey Analytics

La fiabilité de Customer Journey Analytics dépend de celle des données qui le sous-tendent.

La validation des jeux de données avant la création de rapports aide les équipes à :

- Augmenter la confiance dans les résultats d’analyse
- Améliorer les pratiques de gouvernance des données
- Réduire les erreurs de création de rapports
- Identifier plus tôt les problèmes de mise en œuvre
- Résolution plus efficace des problèmes liés aux mesures inattendues

Avec Coworker, ces vérifications peuvent être lancées à l’aide d’invites de langage naturel, ce qui rend la validation des données plus accessible aux utilisateurs et utilisatrices techniques et non techniques.

