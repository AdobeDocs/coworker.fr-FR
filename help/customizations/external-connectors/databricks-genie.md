---
title: Connecteur Externe Genie De Blocs De Données
description: Découvrez comment configurer le connecteur externe Genie de Databricks dans CX Enterprise Coworker avec un principal de service ou une connexion par personne pour interroger les données de Databricks.
role: Admin, User
level: Beginner
badgeBeta: label="Beta" type="Informative" tooltip="Ce connecteur est en version bêta."
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
hide: true
source-git-commit: 4f03df081c098fb1dc1044cb022663ce4d9b3d86
workflow-type: tm+mt
source-wordcount: '1570'
ht-degree: 1%
---

# Connecteur externe Databricks Genie {#databricks-genie}

Utilisez le connecteur externe [!DNL Databricks Genie] pour poser des questions sur vos données [!DNL Databricks] en langage clair dans Adobe CX Enterprise Coworker. [!DNL Genie] écrit le code SQL et renvoie les réponses dans le chat. Le connecteur relie Coworker au serveur MCP ([!DNL Genie One] Model Context Protocol) dans votre espace de travail [!DNL Databricks].

>[!AVAILABILITY]
>
>Le connecteur externe [!DNL Databricks Genie] est en version bêta. La documentation et les fonctionnalités peuvent changer.

## Configuration du connecteur {#connector-configuration}

Le processus de configuration du connecteur comprend deux parties distinctes :

* **Configuration de l’organisation :** un administrateur connecte un collègue à un espace de travail [!DNL Databricks], choisit la manière dont les personnes se connectent et sélectionne les outils que les membres peuvent utiliser.
* **Accès membre :** les membres utilisent la connexion avec une identité d’organisation partagée ou leur propre identité [!DNL Databricks], selon l’option de connexion.

L’administrateur choisit l’une des options de connexion suivantes :

| Option | Prestations de l’administrateur | Fonctionnement de l’accès |
| --- | --- | --- |
| **[!UICONTROL Principal de service de l’organisation]** | Identifiant client et secret client d’un principal de service [!DNL Databricks]. | Tous les membres utilisent les autorisations du principal de service. Les membres ne se connectent pas à [!DNL Databricks]. |
| **[!UICONTROL Chaque personne se connecte]** | L’identifiant client d’une connexion d’application OAuth [!DNL Databricks] et un secret client facultatif. | Chaque membre se connecte avec sa propre identité [!DNL Databricks] et l’accès suit ses autorisations [!DNL Databricks]. |

Aucune option n’accorde d’autorisations [!DNL Databricks] que l’identité sélectionnée ne possède déjà. [!DNL Databricks] applique les autorisations [!DNL Unity Catalog] à chaque demande.

## Conditions préalables {#prerequisites}

Ce connecteur fonctionne avec [!DNL Databricks Genie One]. Il ne prend pas en charge les URL MCP d’espace de [!DNL Genie] héritées. Pour connecter un autre serveur MCP [!DNL Databricks], tel qu’un serveur [!DNL Databricks SQL], ajoutez-le séparément en tant qu’intégration.

Avant de commencer, vérifiez que vous disposez des éléments suivants :

* **Pour la configuration d’organisation :** compte autorisé à gérer les connecteurs d’organisation dans Coworker.
* **Pour l’espace de travail [!DNL Databricks] :** URL HTTPS d’un espace de travail où [!DNL Genie One] est disponible.
* **Pour l’option principal de service :** l’identifiant client et le secret client d’un principal de service [!DNL Databricks].
* **Pour l’option de connexion par personne :** une connexion d’application OAuth [!DNL Databricks] et son identifiant client. Vous avez également besoin d’un administrateur [!DNL Databricks] qui peut enregistrer l’URL de redirection de Coworker.
* **Pour l’accès [!DNL Databricks] :** les autorisations de Workspace, de [!DNL Genie] et de données pour l’identité qui sera utilisée. Un collègue n’accorde pas ces autorisations.

>[!IMPORTANT]
>
>Ne partagez jamais de secrets clients, de jetons d’accès ou d’autres informations d’identification dans des captures d’écran, des conversations ou des tickets d’assistance.

Pour obtenir des instructions, consultez la documentation [!DNL Databricks] suivante :

* [Génie One MCP](https://docs.databricks.com/aws/en/agents/mcp-tools/genie-mcp){target="_blank"}
* [Activer ou désactiver les applications OAuth de partenaire](https://docs.databricks.com/aws/en/integrations/enable-disable-oauth){target="_blank"}
* [Autoriser l’accès principal du service aux briques de données avec OAuth](https://docs.databricks.com/aws/en/dev-tools/auth/oauth-m2m){target="_blank"}

## Configuration du connecteur pour votre organisation {#configure-organization}

Les administrateurs rendent le connecteur [!DNL Databricks Genie] disponible pour tous les membres de l’organisation. Les modifications apportées à la page d’organisation s’appliquent à tous les utilisateurs de votre organisation. Seul un administrateur d’organisation peut ajouter cette connexion. Les membres ne peuvent pas le configurer à partir de la vue **[!UICONTROL Utilisateur]**.

1. Ouvrez **[!UICONTROL Personnalisations]**, sélectionnez **[!UICONTROL Organisation]**, puis **[!UICONTROL Connecteurs externes]**. Sur la carte **[!UICONTROL Databricks Genie]**, sélectionnez **[!UICONTROL Configurer]**.

1. Dans la boîte de dialogue **[!UICONTROL Connecter le génie des briques de données]**, saisissez l’URL de votre espace de travail ou l’URL MCP [!DNL Genie One] dans **[!UICONTROL URL du serveur]**. Un collègue enregistre la source au format suivant :

   ```text
   https://<workspace-host>/ai-gateway/mcp-services/system.ai.genie_one_mcp
   ```

   Utilisez l’URL de votre propre espace de travail. Mon collègue rejette les URL qui n’utilisent pas HTTPS ou qui utilisent des chemins d’accès non pris en charge. Les URL d’espace de [!DNL Genie] héritées, telles que les `/api/2.0/mcp/genie/<space-id>`, ne sont pas prises en charge.

1. Sous **[!UICONTROL Qui se connecte ?]**, sélectionnez une option de connexion, puis renseignez ses paramètres.

   ![Boîte de dialogue Connecter le génie des briques de données avec le principal de service de l’organisation sélectionné, affichant les champs Identifiant du client principal de service et Secret du client principal de service , ainsi que la section Outils disponibles pour les utilisateurs ](./assets/databricks-genie/org-service-principal.png){width="500" zoomable="yes"}.

   * **[!UICONTROL Principal de service de l’organisation] :** les requêtes utilisent les autorisations du principal de service. Utilisez cette option pour un accès automatisé ou géré de manière centralisée. Les membres ne se connectent pas à [!DNL Databricks].

     | Paramètre | Description |
     | --- | --- |
     | **[!UICONTROL Identifiant client principal du service]** | Obligatoire. Identifiant client de votre principal de service [!DNL Databricks]. Pour configurer le principal de service, sélectionnez **[!UICONTROL Configuration du principal de service OAuth]** dans la boîte de dialogue. |
     | **[!UICONTROL Secret client principal du service]** | Obligatoire. Secret client du principal de service. Coworker stocke le secret en toute sécurité et l’utilise pour le principal de service de l’organisation. |

   * **[!UICONTROL Chaque personne se connecte] :** les demandes utilisent les autorisations [!DNL Databricks] de chaque personne. Utilisez cette option pour un accès régi et piloté par l’utilisateur. Chaque membre autorise l’application avec sa propre identité [!DNL Databricks].

     | Paramètre | Description |
     | --- | --- |
     | **[!UICONTROL URL de redirection]** | Lecture seule. Copiez cette URL et ajoutez-la lorsque vous enregistrez Coworker en tant que connexion d’application OAuth dans la console de votre compte [!DNL Databricks]. Pour obtenir des instructions, sélectionnez **[!UICONTROL Comment ajouter une connexion d’application OAuth]** dans la boîte de dialogue. L’URL de redirection diffère selon les environnements, alors copiez-la toujours à partir de la boîte de dialogue. |
     | **[!UICONTROL Identifiant client de l’application OAuth]** | Obligatoire. Identifiant client affiché par [!DNL Databricks] après la création de la connexion à l’application. Un collègue l’utilise pour envoyer chaque personne à la page de connexion [!DNL Databricks]. |
     | **[!UICONTROL Secret client de l’application OAuth]** | Facultatif. Saisissez le secret uniquement si vous avez créé la connexion d’application en tant que client confidentiel. Sans secret client, l’application utilise une configuration client publique. |

   Coworker dérive les URL OAuth et les portées de l’espace de travail. Le type d’authentification et le protocole de connexion sont fixes et en lecture seule. Suivez le processus d’approbation de votre organisation pour l’application OAuth et l’accès qu’elle demande.

   >[!IMPORTANT]
   >
   >Avec un principal de service d’organisation, toute personne qui utilise cette connexion agit avec les autorisations du principal de service.

1. Sous **[!UICONTROL Outils disponibles pour les utilisateurs]**, sélectionnez les outils que les membres peuvent utiliser. Le connecteur fournit les outils suivants, tous disponibles par défaut :

   | Outil | Description |
   | --- | --- |
   | `genie_ask` | Posez-[!DNL Genie] une question. |
   | `genie_poll_response` | Vérifiez le statut d’une réponse qui est toujours en cours. |
   | `genie_get_query_result` | Récupérez les résultats de la requête. |
   | `genie_cancel_response` | Annuler une réponse. |

   Pour bloquer un outil pour tous les membres de votre organisation, supprimez sa balise . Coworker enregistre les outils supprimés en tant qu’exclusions pour votre organisation. Au moins un outil doit rester activé. Après avoir supprimé un outil, l’option **[!UICONTROL Restaurer tous les outils]** s’affiche. Sélectionnez-la pour effacer les exclusions et rendre tous les outils disponibles à nouveau.

   ![Boîte de dialogue Génie Connecter des briques de données présentant les quatre balises d’outil sous Outils disponibles pour les utilisateurs, l’avis Accès et autorisations et le résumé de l’authentification, de la connexion et du délai d’expiration de l’outil.](./assets/databricks-genie/org-tools.png){width="500" zoomable="yes"}

   Les membres ne peuvent afficher et utiliser que les outils que vous laissez activés, et ils ne peuvent pas modifier la sélection d’outils. L’activation d’un outil ne donne pas aux membres d’autorisations [!DNL Databricks] supplémentaires. Le délai d’expiration de l’outil est fixé à 300 secondes.

1. Vérifiez **[!UICONTROL Accès et autorisations]**, puis sélectionnez **[!UICONTROL Enregistrer la connexion]**. La carte **[!UICONTROL Databricks Genie]** affiche **[!UICONTROL Configuration enregistrée]**.

   Sélectionnez **[!UICONTROL Afficher la configuration]** pour consulter l’espace de travail, l’authentification, les outils activés et le délai d’expiration de l’outil. Sélectionnez ensuite **[!UICONTROL Test]** pour vérifier la connexion.

   ![Détails du connecteur de briques de données enregistrés affichant la source, l’authentification, la stratégie de l’outil avec quatre outils autorisés, le délai d’expiration de l’outil et la liste des outils.](./assets/databricks-genie/org-details.png){width="700" zoomable="yes"}

Un test réussi ne confirme pas que l’identité sélectionnée dispose des autorisations [!DNL Databricks] dont elle a besoin.

## Utiliser le connecteur en tant que membre {#use-as-member}

Une fois qu’un administrateur a configuré le connecteur, ouvrez-le à partir de votre propre vue **[!UICONTROL Personnalisations]**. Les membres peuvent afficher et tester la connexion, mais ne peuvent pas la modifier ni la supprimer.

1. Ouvrez **[!UICONTROL Personnalisations]**, sélectionnez **[!UICONTROL Utilisateur]**, puis **[!UICONTROL Connecteurs externes]**.

1. Recherchez la carte **[!UICONTROL Databricks Genie]**. Si votre organisation n’a pas configuré le connecteur, la carte indique **[!UICONTROL Non configuré]** et **[!UICONTROL Pas encore disponible. Votre administrateur doit configurer ce paramètre.]** Il n’existe aucun bouton **[!UICONTROL Configurer]** pour les membres. Demandez donc à votre administrateur de [configurer le connecteur](#configure-organization).

1. Si votre organisation utilise un principal de service, la carte indique **[!UICONTROL Disponible par l’intermédiaire de votre organisation]**. Vous n’avez pas besoin de vous connecter. Pour vérifier la connexion, ouvrez les détails du connecteur et sélectionnez **[!UICONTROL Tester la connexion]**.

   Un test réussi indique **[!UICONTROL Connexion réussie]** et le nombre d’outils disponibles.

   ![Détails du connecteur Génie des briques de données affichant un message de réussite de la connexion avec quatre outils disponibles, un avis indiquant que l’administrateur de l’organisation gère la connexion et l’URL du serveur, l’option de connexion, l’authentification, la connexion et le délai d’expiration de l’outil.](./assets/databricks-genie/member-details.png){width="700" zoomable="yes"}

1. Si votre entreprise utilise la connexion par personne, la carte affiche **[!UICONTROL Connexion requise]**. Ouvrez le connecteur, démarrez la connexion et connectez-vous pour [!DNL Databricks] avec le compte prévu. Effectuez toutes les étapes d’authentification unique (SSO) ou d’authentification multifacteur (MFA) requises.

1. Après être revenu à Coworker, vérifiez que le connecteur affiche **[!UICONTROL Connecté]**. Passez en revue les outils activés par votre administrateur et sélectionnez **[!UICONTROL Tester la connexion]** si nécessaire.

La vue Membre est en lecture seule. Elle affiche le statut de la connexion et les outils activés par votre administrateur. Vous ne saisissez pas le secret client OAuth de l’organisation et ne modifiez pas la sélection d’outils. Si la connexion échoue, les détails du connecteur affichent une erreur et des détails techniques. Copiez les détails techniques et partagez-les avec votre administrateur.

Un statut connecté ne garantit pas l’accès à des données spécifiques. [!DNL Databricks] autorisations relatives à l’espace de travail, aux [!DNL Genie] et aux données s’appliquent toujours.

## Résolution des problèmes d’accès {#troubleshoot-access}

Si la configuration, la connexion ou l’accès échoue, vérifiez les points suivants auprès de votre administrateur :

| Problème | Éléments à vérifier |
| --- | --- |
| L’URL du serveur est refusée | L’URL utilise HTTPS et correspond soit à l’origine de l’espace de travail, soit à l’URL MCP [!DNL Genie One] exacte. Supprimez les chemins d’accès aux espaces de [!DNL Genie] hérités et d’autres chemins non pris en charge. |
| La connexion OAuth échoue ou l’URL de redirection ne correspond pas | La connexion d’application OAuth [!DNL Databricks] possède l’URL de redirection exacte à partir du même environnement Coworker. L’identifiant client et, s’ils sont utilisés, le secret client sont corrects. |
| La connexion principale du service échoue | L’ID client et le secret client appartiennent au principal de service prévu, le secret client est valide et le principal de service a accès à l’espace de travail. |
| La connexion a réussi, mais [!DNL Genie] requêtes échouent | Le membre ou le principal de service dispose des autorisations requises en matière d’espace de travail, de [!DNL Genie] et de données. Votre administrateur peut consulter les détails techniques et les outils activés. |
| Un membre ne peut pas voir ni configurer le connecteur | Un administrateur doit d’abord configurer les [!DNL Databricks Genie] dans la vue **[!UICONTROL Organisation]**. Les membres ne peuvent pas créer cette connexion. |
