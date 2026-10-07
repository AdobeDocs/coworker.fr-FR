---
title: Outils Journey Optimizer dans la passerelle CX Coworker
description: Découvrez les outils Adobe Journey Optimizer disponibles via la passerelle CX Coworker.
hide: true
source-git-commit: 6c126810936bea3e883d74e6ff685991cb40cd4a
workflow-type: tm+mt
source-wordcount: '930'
ht-degree: 6%
---
# Outils Adobe Journey Optimizer dans la passerelle CX Coworker {#ajo-mcp}

Utilisez les outils de produit Adobe Journey Optimizer pour inspecter les configurations des campagnes, des parcours et des canaux à partir d’un client compatible MCP. Ces outils sont disponibles via la passerelle [&#128279;](overview.md) lorsque votre organisation est activée et que votre compte utilisateur dispose des autorisations Journey Optimizer requises.

Pour plus d’informations, voir [Utilisation des clients MCP](https://experienceleague.adobe.com/fr/docs/journey-optimizer/using/content-management/combine/ajo-mcp){target="_blank"} dans la documentation de Adobe Journey Optimizer.

Pour une expérience de conversation et d’analyse permettant de créer, de simuler et d’analyser des parcours, reportez-vous au [Journey Agent](https://experienceleague.adobe.com/fr/docs/cx-enterprise-ai/experience-cloud-ai/agents/ajo-agent) à la place.

>[!AVAILABILITY]
>
>Les outils du produit Journey Optimizer se trouvent dans Beta. L’accès se fait sur invitation uniquement et nécessite l’activation de l’organisation Adobe. Voir [Accès aux outils de la passerelle CX Coworker](access.md).

## Fonctionnalités principales {#mcp-capabilities}

Les outils Journey Optimizer fournissent une surface en lecture seule pour la révision des configurations de campagne, de parcours et de canal. Vous pouvez ainsi :

- Répertoriez les campagnes Journey Optimizer et filtrez par statut.
- Récupérez les détails de la campagne, y compris le ciblage, le planning, le canal et les métadonnées de configuration du contenu.
- Répertoriez et examinez les parcours dans votre sandbox, y compris les embranchements, les conditions et les actions.
- Répertorier les configurations des canaux pour les canaux e-mail, SMS, push et WhatsApp.
- Répertorier les actions marketing disponibles pour l’application des politiques de gouvernance des données.
- Examinez la configuration de la campagne, du parcours et du canal en langage naturel sans naviguer dans les écrans du produit.

>[!IMPORTANT]
>
>Tous les outils Journey Optimizer du Beta actuel sont en lecture seule. La création, la mise à jour, la suppression, le démarrage, l’arrêt ou la publication de campagnes ou de parcours n’est pas pris en charge.

## Outils disponibles {#mcp-tools}

| Outil | Description |
| --- | --- |
| `ajo_campaign_list` | Parcourez les campagnes marketing Journey Optimizer. Prend en charge le filtrage par statut, tel que `DRAFT`, `LIVE`, `STOPPED` et `COMPLETED`. |
| `ajo_campaign_get` | Récupérez les détails et la configuration d’une campagne spécifique par identifiant, y compris le ciblage de l’audience, le planning, le canal et les métadonnées des paramètres de contenu. |
| `ajo_journey_list` | Parcourez tous les parcours de votre sandbox Journey Optimizer. |
| `ajo_journey_get` | Récupérez toutes les informations sur un parcours spécifique par ID, y compris son embranchement, ses conditions et ses actions. |
| Visualisation du parcours | Effectuez le rendu de la structure et du flux d’un parcours pour une exploration visuelle interactive. |
| `ajo_channel_configuration_list`, `ajo_channel_configuration_get` | Affichez les paramètres prédéfinis de surface et les paramètres de branding pour les canaux e-mail, SMS, notification push ou [!DNL WhatsApp]. |
| `ajo_channel_configuration_resource_list`, `ajo_channel_configuration_resource_get` | Répertoriez et récupérez les ressources de configuration de prise en charge référencées par les configurations de canal, telles que les informations d’identification push, les sous-domaines de messagerie, les pools d’adresses IP, les informations d’identification SMS et les informations d’identification [!DNL WhatsApp]. |
| `ajo_marketing_action_list` | Répertoriez les actions marketing disponibles pour l’application des politiques de gouvernance des données. |

## Exemples de prompts {#mcp-use-cases}

| Objectif | Exemple de prompt |
| --- | --- |
| Vue d’ensemble de la campagne | « Afficher toutes mes campagnes Journey Optimizer. » |
| Audit de statut | « Quelles sont les campagnes actuellement actives ? » |
| Détails de la campagne | « Obtenez les détails complets des `[campaign ID]` de campagne. » |
| Vue d’ensemble du parcours | « Montrez-moi tous mes parcours Journey Optimizer. » |
| Détails du parcours | « Obtenez les détails complets des `[journey ID]` de parcours, y compris l’embranchement et les conditions. » |
| Public et ciblage | « Quelle audience est ciblée dans l’`[campaign ID]` de campagne ? » |
| Planning et minutage | « Quand l’exécution de la campagne est-elle planifiée `[campaign ID]` ? » |
| Dépannage | « Vérifiez la configuration des `[campaign ID]` de campagne et signalez les problèmes possibles. » |
| Configuration des canaux | « Quelles configurations de canal e-mail sont disponibles ? » |
| Audit de canal | « Quelles configurations de canal sont manquantes ou incomplètes ? » |
| Gouvernance | « Quelles actions marketing sont disponibles dans mon sandbox ? » |

## Outils de gestion de contenu {#mcp-content-management}

Outre les outils de produit en lecture seule ci-dessus, les utilisateurs de Journey Optimizer peuvent découvrir et gérer des ressources de contenu (modèles de contenu, fragments, pages de destination et contenu de message intégré de parcours ou de campagne) directement depuis CX Coworker à l’aide d’invites de langage naturel. Cette fonctionnalité s’appuie sur un ensemble distinct d’outils MCP compatibles en lecture et écriture pour le contenu Journey Optimizer et est disponible pour tous les clients qui ont accès à CX Coworker.

Pour plus d’informations, voir [Outils de gestion de contenu](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/get-started/essentials/ajo-coworker-skills#content-management){target="_blank"} dans la documentation de Adobe Journey Optimizer.

Les outils de gestion de contenu vous permettent d’effectuer les opérations suivantes :

- Parcourez les modèles de contenu, les fragments et les pages de destination, et récupérez leur structure, leurs métadonnées et leur statut.
- Récupérez le contenu du message intégré configuré sur un nœud d’action de parcours ou de campagne.
- Créez et mettez à jour des modèles de contenu pour n’importe quel canal.
- Créer, mettre à jour, cloner et publier des fragments.
- Remplacez une variante de canal sur le message intégré d’un nœud d’action de parcours ou de campagne.

>[!IMPORTANT]
>
>Contrairement aux outils de produit en lecture seule ci-dessus, les outils de gestion de contenu prennent en charge les opérations d’écriture. La recherche de texte intégral dans les modèles ou les fragments, la validation des modèles ou des fragments, la création ou la publication de pages de destination et la suppression de modèles de contenu, de fragments ou de pages de destination ne sont pas prises en charge.

## Contexte et autorisations du produit {#mcp-context}

Votre compte utilisateur doit disposer des autorisations nécessaires pour afficher les campagnes, les parcours et les configurations de canal Journey Optimizer que vous interrogez. Le MCP ne contourne pas les autorisations de produit.

Si votre organisation utilise plusieurs sandbox, spécifiez le sandbox ou le contexte de l’environnement dans votre invite lorsque vous avez besoin des résultats d’un sandbox spécifique.

## Limites connues {#mcp-limitations}

| Limite | Description | Solution de contournement |
| --- | --- | --- |
| Surface en lecture seule | Les outils Journey Optimizer exposent uniquement les opérations de récupération. Vous ne pouvez pas créer, mettre à jour, supprimer, démarrer, arrêter ou publier de campagnes ou de parcours. | Utilisez l’interface utilisateur ou les API de Journey Optimizer pour les opérations d’écriture. |
| Aucune mesure d’engagement ou de performances | Les outils ne renvoient pas de données de rapport telles que les impressions, les taux de clic publicitaire, les conversions ou les statistiques de diffusion. | Utilisez les rapports Journey Optimizer, les outils Customer Journey Analytics ou les outils Adobe Analytics pour les mesures de performances. |
| La pagination de la liste des campagnes est limitée | La liste des campagnes renvoie la première page de résultats, avec un maximum de 50 campagnes triées par ordre alphabétique. Les valeurs de décalage et de limite ne sont pas appliquées. | Utilisez `Get Campaign` directement si l’identifiant de campagne est connu. Utilisez l’interface utilisateur de Journey Optimizer pour une navigation et un filtrage complets. |
| Aucun filtrage côté serveur par date, canal ou planning | Les listes Campaign prennent en charge le filtrage du statut, mais pas le filtrage par date de publication, date de planning, canal ou type de campagne. | Utilisez la liste des campagnes de l’interface utilisateur de Journey Optimizer pour le filtrage de date et de canal natif. |
| Récupération du contenu du message non disponible via les outils du produit | Les outils de produit en lecture seule ci-dessus ne permettent pas de trouver des messages HTML, des objets, des jetons de personnalisation ni du contenu d’offre. | Utilisez les [&#x200B; outils de gestion de contenu &#x200B;](#mcp-content-management) pour récupérer et mettre à jour le contenu des messages intégrés ou pour l’afficher directement dans l’interface utilisateur de Journey Optimizer. |