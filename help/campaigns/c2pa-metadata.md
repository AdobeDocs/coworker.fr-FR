---
description: Découvrez comment les campagnes Coworker joignent et conservent automatiquement les métadonnées C2PA sur les images, de la génération à la diffusion par e-mail.
title: Métadonnées C2PA dans les campagnes Coworker
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: dbee38135a5491fd21b65fdbb70ba60d949d7560
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 27%
---
# Métadonnées C2PA dans les campagnes Coworker {#overview}

De nouvelles lois sur la transparence de l’IA générative voient le jour, et Adobe s’efforce de respecter les exigences applicables dans les différentes juridictions. [Métadonnées C2PA](https://c2pa.org/) est l’outil de provenance utilisé par Adobe pour répondre aux exigences de ces lois.

Les métadonnées C2PA sont des métadonnées durables et invisibles qui enregistrent la manière dont un élément de contenu a été créé ou modifié. Lorsque vous générez ou modifiez une image à l’aide d’outils d’IA génératifs dans les campagnes Coworker, des métadonnées C2PA sont automatiquement associées à cette image. Aucune action n’est requise de votre part.

## Métadonnées C2PA dans les campagnes par e-mail {#c2pa-metadate-email}

Les images envoyées dans vos campagnes par e-mail conservent leurs métadonnées C2PA intactes, de sorte que les destinataires puissent vérifier l’origine et l’authenticité de toute image directement à partir de l’e-mail diffusé.

## Actions qui joignent des métadonnées C2PA {#actions}

Le tableau suivant résume le moment où des métadonnées C2PA sont jointes, en fonction de l’action d’image effectuée dans la génération d’images dans les campagnes Coworker.

| Action | Description | Métadonnées C2PA jointes ? | Exemple de cas d’usage |
| --- | --- | --- | --- |
| **Générer une image** | Créez une image à partir d’une invite de texte ou d’une image de référence, ou générez une image similaire à partir d’une image existante. | Toujours. L’image est générée par l’IA générative, elle transfère donc toujours de nouvelles métadonnées C2PA. | Une image de bannière pour une campagne par e-mail est générée à partir d’un prompt de texte qui décrit le visuel souhaité. |

## Types de contenu et leur portée {#content-types}

* **Images** : prises en charge. Les métadonnées C2PA sont jointes lorsque les images sont générées avec l’IA générative et conservées par le biais d’opérations de recadrage, de superposition de texte et de superposition d’image effectuées par la génération d’images dans les campagnes Coworker.
* **Texte** : non applicable. Les sorties texte uniquement dans les campagnes Coworker, telles que la génération de copies, la traduction et les suggestions d’alignement de marque, ne nécessitent pas de métadonnées C2PA.

## Ce qui se passe lorsque le contenu est déplacé {#content-moves}

Les campagnes Coworker conservent les métadonnées C2PA associées aux ressources d’image prises en charge. Si une image contient des métadonnées C2PA lors de l’importation dans les campagnes Coworker, ces informations d’identification sont conservées lorsque la ressource est utilisée dans le contenu de campagne généré et les expériences d’e-mail sortant.

## Ressources supplémentaires {#resources}

* [Transparence du contenu d’IA générative](https://experienceleague.adobe.com/fr/docs/cx-enterprise-ai/experience-cloud-ai/overview/content-transparency){target="_blank"}
* [Instructions d’utilisation de l’IA générative d’Adobe Experience Cloud](https://www.adobe.com/fr/legal/licenses-terms/adobe-dx-gen-ai-user-guidelines.html){target="_blank"}
* [Mécanismes de sécurisation et limites](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/content-management/generate-content/gs-generative#generative-guardrails){target="_blank"}
