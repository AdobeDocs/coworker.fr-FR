---
title: Outils Real-Time CDP dans la passerelle CX Coworker
description: Découvrez comment connecter Adobe Real-Time CDP aux clients MCP à l’aide du serveur MCP.
hide: true
source-git-commit: 6c126810936bea3e883d74e6ff685991cb40cd4a
workflow-type: tm+mt
source-wordcount: '789'
ht-degree: 4%
---
# Outils Real-Time CDP dans la passerelle CX Coworker {#rtcdp-mcp}

Vous pouvez utiliser les outils de produit Real-Time CDP MCP pour inspecter les audiences, les destinations, les sources, les espaces de noms d’identité et l’intégrité de l’activation à partir d’un client compatible MCP. Ces outils sont disponibles via la passerelle unifiée [](overview.md) lorsque votre organisation est activée et que votre compte utilisateur dispose des autorisations Real-Time CDP requises.

>[!AVAILABILITY]
>
>L’outil de produit Real-Time CDP se trouve dans Beta. L’accès se fait sur invitation uniquement et nécessite l’activation de l’organisation Adobe. Voir [Accès aux outils de la passerelle CX Coworker](access.md).

## Fonctionnalités principales {#mcp-capabilities}

Les outils Real-Time CDP fournissent une surface de surveillance et de triage en lecture seule. Vous pouvez ainsi :

* Répertorier et inspecter les audiences, y compris l’état du cycle de vie, l’origine et l’espace de noms d’identité.
* Consultez les traitements d’évaluation et d’exportation des audiences pour identifier les échecs récents.
* Inspectez les comptes de destination configurés, les flux de destination et l’historique d’exécution d’activation.
* Inspectez les connecteurs source, les comptes, les flux et l’historique d’exécution de l’ingestion.
* Répertorier les espaces de noms d’identité et les politiques de fusion.

>[!IMPORTANT]
>
>Tous les outils Real-Time CDP du Beta actuel sont en lecture seule. La création, la mise à jour, l’activation ou la suppression d’audiences, de destinations, de sources ou de flux de données n’est pas prise en charge.

## Outils disponibles {#mcp-tools}

| Zone | Outil | Description |
| --- | --- | --- |
| Audiences | `search_audiences` | Répertoriez et recherchez des audiences par nom, type d’entité, état du cycle de vie, espace de noms d’identité ou origine. |
| Audiences | `preview_audience_membership` | Estimez la taille d’une expression de segment PQL ou SDD avant de l’enregistrer en tant qu’audience. |
| Audiences | `inspect_audience_evaluation_jobs` | Récupérez les enregistrements de tâche d’évaluation de segment pour diagnostiquer les problèmes d’actualisation d’audience ou confirmer l’historique des évaluations récentes. |
| Audiences | `inspect_audience_export_jobs` | Récupérez les enregistrements de tâche d’exportation d’audience pour confirmer les exportations terminées ou les détails d’échec de surface. |
| Destinations | `search_destination_connectors` | Répertorier les types de connecteurs de destination disponibles dans la plateforme. |
| Destinations | `search_destination_accounts` | Répertorier les comptes de destination authentifiés. |
| Destinations | `search_destination_input_connections` | Récupérez l’entrée côté Experience Platform d’un flux de destination. |
| Destinations | `search_destination_output_connections` | Récupérez le point d’entrée externe d’un flux de destination, y compris le chemin d’accès cible, le format de fichier et la configuration de diffusion. |
| Destinations | `search_destination_flows` | Répertorier et inspecter les flux d’activation de destination configurés, y compris l’état, les mappages et le planning. |
| Destinations et sources | `inspect_flow_runs` | Récupérez l’historique d’exécution du flux source et de destination, y compris le statut, le minutage, le nombre d’enregistrements et les détails des échecs. |
| Sources | `search_source_connectors` | Répertorier les types de connecteurs source disponibles dans la plateforme. |
| Sources | `search_source_accounts` | Répertorier les comptes sources authentifiés. |
| Sources | `search_source_input_connections` | Récupérez ce qu’un flux source extrait d’un compte. |
| Sources | `search_source_output_connections` | Récupérez la destination du jeu de données Experience Platform pour un flux source. |
| Sources | `search_source_flows` | Répertorier et inspecter les pipelines d’ingestion source configurés, y compris l’état, les mappages et le planning. |
| Identité | `search_identity_namespaces` | Répertorier les définitions d’espaces de noms d’identité dans votre sandbox. |
| Identité | `search_merge_policies` | Répertorier les enregistrements de politique de fusion qui contrôlent la manière dont les profils clients en temps réel sont assemblés. |

## Exemples de prompts {#mcp-use-cases}

| Objectif | Exemple de prompt |
| --- | --- |
| Liste des audiences | « Répertorier mes audiences dans le sandbox `prod`. » |
| Inspection d’une audience | « Afficher les détails et l’état du cycle de vie pour l’ID d’audience `abc123`. » |
| Diagnostiquer les problèmes d’évaluation | « Afficher les tâches d’évaluation d’audience les plus récentes et signaler les échecs. » |
| Vérifier les traitements d’exportation | « Répertoriez les tâches d’exportation d’audience récentes et affichez le statut de chacune d’elles. » |
| Estimer la taille de l’audience | « Estimez la taille de cette expression PQL avant de l’enregistrer : `homeAddress.country = 'US'`. » |
| Vérifier la configuration de destination | « Répertorier mes flux d’activation de destination et afficher ceux qui sont activés ou désactivés. » |
| Enquête sur une exécution d’activation ayant échoué | « Affichez-moi l’historique d’exécution de l’ID de flux `xyz789` et résumez les erreurs. » |
| Vérifier l’ingestion de la source | « Afficher l’historique d’exécution récent pour les échecs de `src456` d’identifiant de flux source et d’indicateur. » |
| Inspection de la configuration d’identité | « Quels espaces de noms d’identité sont configurés dans mon sandbox ? » |

## Autorisations {#mcp-context}

Votre organisation Adobe et votre contexte de sandbox sont établis une seule fois au niveau de la connexion de la passerelle et s’appliquent à chaque famille d’outils, de sorte que vous ne changez pas d’organisation ou de sandbox à partir des outils Real-Time CDP. Pour définir ce contexte pour une session, voir [Contexte du produit pour les appels d’outils](install.md#mcp-connect-params).

Votre compte utilisateur doit être autorisé à afficher les ressources Real-Time CDP que vous interrogez. La passerelle ne contourne pas les autorisations de produit.

## Limites connues {#mcp-limitations}

| Limite | Description | Solution de contournement |
| --- | --- | --- |
| Surface en lecture seule | Les outils Real-Time CDP exposent uniquement les API de récupération. Vous ne pouvez pas créer, mettre à jour, activer ou supprimer des audiences, des destinations, des sources ou des flux de données. | Utilisez l’interface utilisateur de Real-Time CDP ou les API Experience Platform pour les opérations d’écriture. |
| Aucune mesure d’engagement ou de diffusion | Les outils ne renvoient pas de statistiques de diffusion, d’engagement ou de mesures de conversion en aval à partir des plateformes de destination. | Utilisez les rapports de la plateforme de destination, les outils Customer Journey Analytics ou les outils Adobe Analytics pour obtenir des données d’engagement et de conversion. |
| La requête de segment doit être créée en externe. | `preview_audience_membership` nécessite une expression PQL ou SDD valide. L’outil ne compose pas la requête pour vous. | Créez l’expression dans le créateur de segments ou l’API Segmentation Service, puis collez-la dans votre invite. |
| Pagination via des jetons de continuation | Les outils de liste renvoient des résultats paginés. L’énumération complète sur des sandbox très volumineux nécessite le chaînage de jetons de continuation. | Requêtes étroites à l’aide de filtres tels que le nom, l’état, la spécification de connexion ou la période. |
| Le filtrage des exécutions d’activation est basé uniquement sur le temps | Le contrôle d’exécution de l’activation prend en charge le filtrage par statut et horodatage de fin, mais pas directement par type d’erreur ou plateforme de destination. | Le filtrage par `flowId` d’abord pour la portée s’exécute vers un flux de destination spécifique. |

