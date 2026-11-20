---
title: Connecteur externe Jira / Atlassian Rovo
description: Découvrez comment configurer le connecteur externe Jira / Atlassian Rovo dans CX Enterprise Coworker et connectez-vous avec Atlassian pour lire et rechercher des éléments de travail Jira.
role: Admin, User
level: Beginner
badgeBeta: label="Beta" type="Informative" tooltip="Ce connecteur est en version bêta."
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
hide: true
source-git-commit: 92e7715a5eb7ab4f8feb7348384c94fabc1b78cf
workflow-type: tm+mt
source-wordcount: '1482'
ht-degree: 1%
---

# Connecteur externe Jira / Atlassian Rovo {#jira-atlassian-rovo}

Utilisez le connecteur externe [!DNL Jira] / [!DNL Atlassian Rovo] pour lire et rechercher vos [!DNL Jira] éléments de travail dans Adobe CX Enterprise Coworker. Une fois que vous avez configuré le connecteur, demandez à vos collègues de rechercher des éléments de travail, de lire leurs détails et d’effectuer une recherche avec Jira Query Language (JQL). Le connecteur est un serveur MCP (Model Context Protocol) hébergé par [!DNL Atlassian].

>[!AVAILABILITY]
>
>Le connecteur externe [!DNL Jira] / [!DNL Atlassian Rovo] est en version bêta. La documentation et les fonctionnalités peuvent changer.

## Configuration du connecteur {#connector-configuration}

Le processus de configuration du connecteur comprend trois parties distinctes :

* Préparation de **[!DNL Atlassian]:** Un administrateur de l’organisation [!DNL Atlassian] autorise le domaine d’URL de redirection de Coworker et révise les politiques d’accès MCP.
* **Configuration de l’organisation :** Un administrateur Collègue configure le connecteur une seule fois pour l’ensemble de l’organisation. L&#39;administrateur choisit les outils en lecture seule que les membres peuvent utiliser.
* **Connexion du membre :** Chaque membre se connecte avec son propre compte [!DNL Atlassian]. Les membres peuvent accéder uniquement aux données [!DNL Jira] que leur compte est autorisé à afficher.

L&#39;enregistrement de la configuration de l&#39;organisation ne connecte aucun membre et n&#39;accorde aucune autorisation [!DNL Jira]. Chaque membre doit se connecter séparément.

Le connecteur ne dispose d’aucune option de compte de service partagé ou de jeton API. Mon collègue enregistre automatiquement l’application OAuth avec [!DNL Atlassian], de sorte que vous ne saisissiez pas d’ID client ni de secret client.

Bien que le nom du connecteur inclue [!DNL Atlassian Rovo], le connecteur demande [!DNL Jira] accès en lecture et en recherche uniquement. Il ne demande pas d&#39;accès spécifique à [!DNL Confluence], [!DNL Rovo], en écriture ou destructif. Les autres fonctionnalités MCP [!DNL Atlassian] ne sont pas nécessairement disponibles via ce connecteur.

## Conditions préalables {#prerequisites}

Avant de commencer, vérifiez que vous disposez des éléments suivants :

* **Pour la configuration de l&#39;organisation :** Compte autorisé à gérer les connecteurs d&#39;organisation dans Coworker, dans une organisation où le connecteur [!DNL Jira]/[!DNL Atlassian Rovo] est disponible.
* **Pour la préparation de [!DNL Atlassian] :** un administrateur de l’organisation [!DNL Atlassian] qui peut approuver l’accès au MCP et le domaine de l’URL de redirection de Coworker.
* **Pour la connexion du membre :** [!DNL Atlassian] comptes avec accès aux [!DNL Jira] sites, projets et éléments de travail prévus.
* **Pour l&#39;accès au réseau :** [!DNL Atlassian] les places sur la liste autorisée IP et les politiques d&#39;application qui autorisent la connexion. Une connexion réussie ne confirme pas que les requêtes d’outil sont autorisées.
* **[!DNL Rovo]activé :** [!DNL Rovo] activé pour votre organisation [!DNL Atlassian] et les [!DNL Jira] sites prévus avant que les membres n’utilisent le connecteur. Pour plus d&#39;informations, consultez [Comment activer Rovo](https://www.atlassian.com/software/rovo/guides/admin-guide/rovo-activation) dans la documentation [!DNL Atlassian].

## Préparer l&#39;accès à [!DNL Atlassian] {#prepare-atlassian}

Avant la connexion des membres, un administrateur de l&#39;organisation [!DNL Atlassian] prépare l&#39;accès dans [!DNL Atlassian Administration] :

1. Ouvrez [!DNL Atlassian Administration] et sélectionnez l’organisation prévue.

1. Sélectionnez **[!UICONTROL Connecteurs]** > **[!UICONTROL Serveur MCP Atlassian]** > **[!UICONTROL Ajouter un domaine]**.

1. Ajoutez le domaine de l’URL de **[!UICONTROL redirection]** affichée dans la boîte de dialogue de configuration de Coworker. Pour la boîte de dialogue, voir [Configurer le connecteur pour votre organisation](#configure-organization).

   Suivez les règles de format du domaine [!DNL Atlassian] au lieu de coller l’URL complète. Pour plus d’informations, consultez [domaines de serveur Atlassian MCP disponibles](https://support.atlassian.com/security-and-access-policies/docs/available-atlassian-mcp-server-domains/) dans la documentation [!DNL Atlassian].

1. Examinez les groupes d&#39;autorisations MCP, les politiques d&#39;application et les places sur la liste autorisée IP avec l&#39;administrateur [!DNL Atlassian]. Pour plus d’informations, consultez la documentation [!DNL Atlassian] suivante :

   * [Outils Atlassian MCP pris en charge](https://support.atlassian.com/atlassian-ai-gateway/docs/supported-tools/), pour les groupes d’autorisations et les portées dont chaque outil a besoin
   * [Contrôler les paramètres du serveur Atlassian MCP](https://support.atlassian.com/security-and-access-policies/docs/control-atlassian-mcp-server-settings/), pour l&#39;authentification et la liste autorisée IP

Utilisez toujours l’URL de redirection affichée dans la boîte de dialogue Collègue pour l’environnement que vous configurez. Ne copiez pas d’URL de redirection à partir d’un autre environnement.

## Configuration du connecteur pour votre organisation {#configure-organization}

Les administrateurs rendent le connecteur [!DNL Jira] / [!DNL Atlassian Rovo] disponible pour tous les membres de l’organisation. Les modifications apportées à la page d’organisation s’appliquent à tous les utilisateurs de votre organisation.

1. Ouvrez **[!UICONTROL Personnalisations]**, sélectionnez **[!UICONTROL Org]**, puis **[!UICONTROL Connecteurs externes]**. Sur la carte **[!UICONTROL Jira / Atlassian Rovo]**, sélectionnez **[!UICONTROL Configurer]**. Les membres ne peuvent pas configurer ni supprimer cette connexion.

1. Dans la boîte de dialogue **[!UICONTROL Connecter Jira / Atlassian Rovo]**, passez en revue l’**[!UICONTROL URL du serveur]** fixe, `https://mcp.atlassian.com/v2/mcp`.

   Vérifiez l’**[!UICONTROL URL de redirection]** et assurez-vous qu’un administrateur [!DNL Atlassian] approuve son domaine, comme décrit dans [Préparer l’accès Atlassian](#prepare-atlassian). Vous ne saisissez aucune information d’identification OAuth.

1. Sous **[!UICONTROL Outils disponibles pour les utilisateurs]**, choisissez les outils que les membres peuvent utiliser. Pour plus d&#39;informations, voir [Outils disponibles](#available-tools).

   L’outil de découverte de site `getAccessibleAtlassianResources` est obligatoire et reste activé. Les cinq autres outils sont facultatifs. Pour bloquer un outil facultatif pour tous les membres de votre organisation, supprimez-le. Pour rétablir les outils que vous avez supprimés, sélectionnez **[!UICONTROL Restaurer tous les outils]**. Vous pouvez enregistrer la configuration avec uniquement la découverte de site activée, mais les membres ne peuvent alors pas lire ni rechercher des éléments de travail.

   ![Boîte de dialogue Connecter Jira / Atlassian Rovo affichant l&#39;URL du serveur, une URL de redirection expurgée et six outils disponibles pour les utilisateurs, avec l&#39;outil getAccessibleAtlassianResources requis et cinq outils facultatifs.](./assets/jira-atlassian-rovo/org-configure.png){width="500" zoomable="yes"}

1. Sélectionnez **[!UICONTROL Enregistrer la connexion]**, puis vérifiez les détails de la connexion.

   Le connecteur demande les portées OAuth suivantes lorsque chaque membre se connecte :

   | Portée | Rôle |
   | --- | --- |
   | `read:me`, `read:account` | Prend en charge l’autorisation avec le compte [!DNL Atlassian] du membre. |
   | `read:jira:agent-interface` | Lire les données [!DNL Jira]. |
   | `search:jira:agent-interface` | Rechercher les données [!DNL Jira]. |
   | `offline_access` | Actualisez le jeton de connexion. |

   Le délai d’expiration de l’outil est de 60 secondes. La première connexion et la découverte d’outils peuvent prendre plus de temps.

### Outils disponibles {#available-tools}

Le connecteur [!DNL Jira] / [!DNL Atlassian Rovo] fournit les outils en lecture seule suivants :

| Outil | Description | Contrôle administrateur |
| --- | --- | --- |
| `getAccessibleAtlassianResources` | Recherchez les [!DNL Atlassian] sites et ID de cloud auxquels vous pouvez accéder. Les outils [!DNL Jira] ont besoin de cet outil. | Requis |
| `atlassianUserInfo` | Obtenez les informations de compte de l’utilisateur connecté. | Facultatif |
| `getJiraIssue` | Obtenir un élément de travail [!DNL Jira] par ID ou clé. | Facultatif |
| `searchJiraIssuesUsingJql` | Rechercher [!DNL Jira] éléments de travail avec JQL. | Facultatif |
| `discover` | Recherchez d’autres opérations d’outil et leurs schémas d’entrée. | Facultatif |
| `executeRead` | Exécutez les opérations de lecture trouvées via `discover`, telles que la lecture de commentaires, de journaux de modifications, de projets, de tableaux et de sprints. | Facultatif |

>[!IMPORTANT]
>
>Les outils `discover` et `executeRead` donnent aux membres l’accès à d’autres opérations de lecture autorisées en tant que groupe. Vous ne pouvez pas désactiver des opérations individuelles. Si cet accès n’est pas acceptable pour votre organisation, supprimez les deux outils. Le connecteur n&#39;inclut pas les opérations d&#39;écriture (`executeWrite`) ni les opérations destructives (`executeDestructive`).

La suppression des outils facultatifs limite leur disponibilité dans Coworker. Cela ne réduit pas les portées OAuth que le connecteur demande lors de la connexion.

Chaque outil a besoin de groupes d&#39;autorisations et de portées [!DNL Atlassian] spécifiques. Pour plus d’informations, voir [Outils de MCP Atlassian pris en charge](https://support.atlassian.com/atlassian-ai-gateway/docs/supported-tools/) dans la documentation [!DNL Atlassian].

## Se connecter en tant que membre {#sign-in-as-a-member}

Une fois qu’un administrateur a configuré le connecteur, chaque membre se connecte avec son propre compte [!DNL Atlassian]. Vous n’avez pas besoin d’un ID client, d’un secret client ou d’un jeton d’accès pour vous connecter.

1. Ouvrez **[!UICONTROL Personnalisations]**, sélectionnez **[!UICONTROL Utilisateur]**, puis **[!UICONTROL Connecteurs externes]**.

1. Recherchez la carte **[!UICONTROL Jira / Atlassian Rovo]**. Si la carte indique **[!UICONTROL Non configuré]** et **[!UICONTROL Pas encore disponible. Votre administrateur doit configurer ceci.]**, demandez à votre administrateur de [configurer le connecteur](#configure-organization). Les membres ne peuvent pas configurer le connecteur.

1. Sélectionnez **[!UICONTROL Se connecter]** et utilisez le compte [!DNL Atlassian] ayant accès au site [!DNL Jira] prévu. Renseignez les informations d’authentification unique (SSO), d’authentification multifacteur (MFA) et les invites de consentement requises. Vérifiez les accès en lecture et en recherche demandés avant de donner votre consentement.

   >[!IMPORTANT]
   >
   >Continuez uniquement si vous reconnaissez l’application et que votre organisation approuve l’accès demandé.

1. Revenez à Coworker et ouvrez les détails du connecteur. La connexion est en lecture seule pour les membres et vous pouvez afficher les outils activés par votre administrateur. Sélectionnez **[!UICONTROL Tester la connexion]** pour confirmer la connexion.

1. Vous pouvez éventuellement effectuer une petite vérification en lecture seule, comme décrit dans [Vérifier votre accès Jira](#check-access).

Un test réussi ne confirme pas que vous pouvez accéder à chaque site, projet ou élément de travail [!DNL Jira].

## Vérifier votre accès à [!DNL Jira] {#check-access}

Pour confirmer que le connecteur peut lire vos données, démarrez une conversation et saisissez une invite en lecture seule.

Exemple d’invite :

* « Recherchez dans Jira jusqu’à cinq éléments de travail qui me sont affectés, triés selon la dernière mise à jour. Insérez leurs clés et liens. Ne modifiez rien. »

Pour que cette invite fonctionne, votre administrateur doit activer un outil de recherche et votre compte [!DNL Jira] doit être autorisé à afficher les éléments de travail.

## Résolution des problèmes d’accès {#troubleshoot-access}

Si la connexion ou l’accès échoue, vérifiez les points suivants auprès de votre administrateur :

| Problème | Éléments à vérifier |
| --- | --- |
| Connexion bloquée pour le client ou le domaine | Vérifiez que le domaine de l’URL de redirection pour votre environnement est approuvé dans [!DNL Atlassian Administration], sous les paramètres **[!UICONTROL Serveur MCP Atlassian]**. |
| Le consentement réussit, mais les appels aux outils sont refusés | Vérifiez vos autorisations [!DNL Jira], les groupes d’autorisations MCP [!DNL Atlassian], les politiques d’application et les places sur la liste autorisée IP. Pour connaître les groupes d’autorisations requis par chaque outil, consultez [Outils Atlassian MCP pris en charge](https://support.atlassian.com/atlassian-ai-gateway/docs/supported-tools/). |
| La recherche JQL échoue, mais d’autres lectures fonctionnent | Vérifiez que votre administrateur a activé `searchJiraIssuesUsingJql` et que la connexion demande la portée `search:jira:agent-interface`. |
| Le consentement renvoie `invalid_request` | Demandez à votre administrateur de confirmer que la connexion demande `read:me` et `read:account` en plus des portées [!DNL Jira]. |
| Des portées plus anciennes restent visibles après une modification | Un remplacement de fournisseur d’authentification `jira_login` de niveau utilisateur obsolète peut être prioritaire sur la connexion d’organisation. Demandez à un administrateur de mettre à jour ou de supprimer uniquement ce remplacement obsolète, puis connectez-vous à nouveau. |
| Il manque un outil | Demandez à votre administrateur de vérifier la sélection d’outils. Les opérations de lecture supplémentaires nécessitent à la fois `discover` et `executeRead`, les portées requises et les autorisations appropriées. |
| **[!UICONTROL La connexion de test]** est lente ou expire | La découverte d’outils peut prendre plus de temps que le délai d’expiration de 60 secondes. Vérifiez si le problème est la lenteur de la découverte ou un échec de connexion avant de modifier les informations d’identification. |

Lorsque vous demandez de l’aide, ne partagez pas de mots de passe, de jetons, de codes d’autorisation ou d’URL de consentement. Ne les incluez pas dans les captures d’écran ou les tickets d’assistance.
