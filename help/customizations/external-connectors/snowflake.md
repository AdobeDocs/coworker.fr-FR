---
title: Connecteur externe IA de Snowflake Cortex
description: Découvrez comment configurer le connecteur externe IA Cortex Snowflake dans CX Enterprise Coworker avec un compte de service ou une connexion par personne pour interroger les données Snowflake.
role: Admin, User
level: Beginner
badgeBeta: label="Beta" type="Informative" tooltip="Ce connecteur est en version bêta."
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
hide: true
source-git-commit: 942f76a48eabbc9ac795d9e53aad1faceff31393
workflow-type: tm+mt
source-wordcount: '2057'
ht-degree: 0%
---

# Connecteur externe Snowflake Cortex AI {#snowflake}

Utilisez le connecteur externe [!DNL Snowflake Cortex AI] pour poser des questions sur vos données [!DNL Snowflake] en langage clair dans Adobe CX Enterprise Coworker. Le connecteur relie Coworker à un serveur MCP (Model Context Protocol) géré par [!DNL Snowflake] dans votre compte [!DNL Snowflake]. Coworker peut ensuite utiliser les outils exposés par le serveur, tels que les outils [!DNL Cortex Analyst], [!DNL Cortex Search] et SQL.

>[!AVAILABILITY]
>
>Le connecteur externe [!DNL Snowflake Cortex AI] est en version bêta. La documentation et les fonctionnalités peuvent changer.

## Configuration du connecteur {#connector-configuration}

Le processus de configuration du connecteur comprend deux parties distinctes :

* **Configuration de l’organisation :** un administrateur connecte un collègue à un serveur MCP [!DNL Snowflake] existant, choisit la manière dont les personnes se connectent et sélectionne les outils que les membres peuvent utiliser.
* **Accès membre :** les membres utilisent la connexion avec une identité d’organisation partagée ou leur propre identité [!DNL Snowflake], selon l’option de connexion.

L’administrateur choisit l’une des options de connexion suivantes :

| Option | Prestations de l’administrateur | Fonctionnement de l’accès |
| --- | --- | --- |
| **[!UICONTROL Compte de service de l’organisation]** | Jeton d’accès programmatique (PAT) [!DNL Snowflake] pour un compte de service. | Tous les membres utilisent les autorisations du compte de service. L’expiration ou la révocation des jetons affecte tous les membres. |
| **[!UICONTROL Chaque personne se connecte]** | L’identifiant client et le secret client d’une intégration OAuth [!DNL Snowflake], ainsi qu’un rôle [!DNL Snowflake] facultatif. | Chaque membre se connecte avec sa propre identité [!DNL Snowflake] et l’accès suit ses autorisations [!DNL Snowflake]. |

Aucune option n’accorde de privilèges [!DNL Snowflake] que l’identité sélectionnée ne possède déjà. [!DNL Snowflake] applique les autorisations à chaque demande.

## Conditions préalables {#prerequisites}

Coworker se connecte à un serveur MCP [!DNL Snowflake] existant. Il ne crée pas le serveur ni ses outils. Avant de commencer, vérifiez que vous disposez des éléments suivants :

* **Pour la configuration d’organisation :** compte autorisé à gérer les connecteurs d’organisation dans Coworker.
* **Pour le serveur MCP [!DNL Snowflake] :** URL HTTPS complète du serveur, y compris sa base de données, son schéma et son nom de serveur.
* **Pour l’option compte de service :** un chemin d’accès pour un compte de service dédié. Le rôle de compte de service ne doit disposer que des privilèges nécessaires pour le serveur MCP et ses outils.
* **Pour l’option de connexion par personne :** une intégration OAuth [!DNL Snowflake] avec son identifiant client et son secret client. Vous avez également besoin d’un administrateur [!DNL Snowflake] qui peut enregistrer l’URL de redirection de Coworker et configurer l’intégration.

>[!IMPORTANT]
>
>Ne partagez jamais de PAT, de secrets clients OAuth ou d’autres informations d’identification dans des captures d’écran, des conversations ou des tickets d’assistance. Utilisez des secrets d’organisation et une identité de [!DNL Snowflake] moins privilégiée.

### Configuration du serveur Snowflake MCP {#configure-snowflake-mcp-server}

Un administrateur [!DNL Snowflake] doit effectuer les tâches suivantes dans [!DNL Snowflake] avant de configurer le connecteur :

1. Créez le serveur MCP et définissez les outils qu’il expose.
1. Accordez aux rôles requis l’accès au serveur MCP, à ses outils et aux objets sous-jacents.

   L’accès au serveur MCP n’accorde pas automatiquement l’accès à chaque outil ou objet.

1. Configurez l’authentification pour l’option de connexion que vous prévoyez d’utiliser :

   * Pour l’option compte de service , créez un chemin d’accès pour le compte de service.
   * Pour l’option de connexion par personne, créez une intégration OAuth qui émet des jetons d’actualisation.

Pour obtenir des instructions, consultez la documentation [!DNL Snowflake] suivante :

* [Serveur MCP géré par Snowflake](https://docs.snowflake.com/en/user-guide/snowflake-cortex/cortex-agents-mcp){target="_blank"}
* [Créer un serveur MCP](https://docs.snowflake.com/en/sql-reference/sql/create-mcp-server){target="_blank"}
* [Présentation du contrôle d’accès](https://docs.snowflake.com/en/user-guide/security-access-control-overview){target="_blank"}
* [Configuration de Snowflake OAuth pour les clients personnalisés](https://docs.snowflake.com/en/user-guide/oauth-custom){target="_blank"}
* [Créer une intégration de sécurité (Snowflake OAuth)](https://docs.snowflake.com/en/sql-reference/sql/create-security-integration-oauth-snowflake){target="_blank"}
* [Utilisation de jetons d’accès programmatiques pour l’authentification](https://docs.snowflake.com/en/user-guide/programmatic-access-tokens){target="_blank"}

## Configuration du connecteur pour votre organisation {#configure-organization}

Les administrateurs rendent le connecteur [!DNL Snowflake Cortex AI] disponible pour tous les membres de l’organisation. Les modifications apportées à la page d’organisation s’appliquent à tous les utilisateurs de votre organisation.

1. Ouvrez **[!UICONTROL Personnalisations]**, sélectionnez **[!UICONTROL Organisation]**, puis **[!UICONTROL Connecteurs externes]**. Sur la carte **[!UICONTROL Snowflake Cortex AI]**, sélectionnez **[!UICONTROL Configurer]**.

1. Dans la boîte de dialogue **[!UICONTROL Connecter Snowflake Cortex AI]**, saisissez l’URL complète de votre serveur [!DNL Snowflake] MCP dans **[!UICONTROL URL du serveur]**. L’URL doit utiliser HTTPS et suivre le modèle suivant :

   ```text
   https://<account-host>/api/v2/databases/<database>/schemas/<schema>/mcp-servers/<server-name>
   ```

   Utilisez l’URL exacte de votre compte [!DNL Snowflake] et du serveur MCP. Le nom d’hôte du compte ne doit pas contenir de tiret bas, y compris un tiret bas codé (`%5F`). N’incluez pas d’informations d’identification dans l’URL. Un collègue vérifie le schéma HTTPS, l’hôte et le chemin d’accès avant d’enregistrer.

1. Sous **[!UICONTROL Qui se connecte ?]**, sélectionnez une option de connexion, puis renseignez ses paramètres.

   * **[!UICONTROL Compte de service de l’organisation] :** les requêtes utilisent les autorisations du compte de service par le biais d’un jeton d’accès programmatique (PAT). Utilisez cette option pour un accès géré de manière centralisée. Utilisez un compte de service dédié dont le rôle est limité, et non un compte personnel.

     ![Boîte de dialogue Connecter Snowflake avec le compte de service d’organisation sélectionné, affichant le champ URL du serveur , les options Jeton de compte de service , le champ Jeton d’accès par programmation et un avertissement indiquant que tout le monde agit avec les autorisations du propriétaire du jeton.](./assets/snowflake/org-service-account.png){width="500" zoomable="yes"}

     | Paramètre | Description |
     | --- | --- |
     | **[!UICONTROL Jeton du compte de service]** | Choisissez d’où provient le jeton. Sélectionnez **[!UICONTROL Saisir nouveau]** pour saisir un PAT ou **[!UICONTROL Utiliser un secret existant]** pour réutiliser un secret d’organisation qui contient déjà le jeton. Un secret existant doit contenir la valeur complète de l’en-tête `Authorization`, et pas seulement le jeton brut. |
     | **[!UICONTROL Jeton d’accès programmatique]** | Obligatoire lorsque vous sélectionnez **[!UICONTROL Saisir nouveau]**. Créez le jeton pour un compte de service [!DNL Snowflake] dédié avec uniquement les autorisations requises. Pour obtenir des instructions, sélectionnez **[!UICONTROL Comment créer un jeton d’accès par programmation]** dans la boîte de dialogue. Un collègue stocke le jeton en tant que secret d’organisation. |

     >[!IMPORTANT]
     >
     >Toute personne qui utilise cette connexion agit avec les autorisations du propriétaire du jeton. Si le jeton expire ou est révoqué, la connexion cesse de fonctionner pour tous les membres.

     La création et l’utilisation d’un PAT peuvent être soumises à des politiques de réseau et d’authentification [!DNL Snowflake]. Si la création ou l’authentification de jeton est bloquée, demandez à votre administrateur [!DNL Snowflake] de vérifier ces politiques.

   * **[!UICONTROL Chaque personne se connecte] :** les demandes utilisent les autorisations [!DNL Snowflake] de chaque personne. Utilisez cette option pour un accès régi et piloté par l’utilisateur.

     ![Boîte de dialogue Connecter Snowflake avec Chaque personne se connecte sélectionnée, affichant l’URL de redirection, les options d’informations d’identification de l’intégration OAuth, les champs d’ID client de l’intégration OAuth et de secret client, ainsi que le champ facultatif rôle Snowflake.](./assets/snowflake/org-oauth.png){width="500" zoomable="yes"}

     | Paramètre | Description |
     | --- | --- |
     | **[!UICONTROL URL de redirection]** | Lecture seule. Copiez cette URL et enregistrez-la en tant qu’URI de redirection dans votre intégration de sécurité OAuth [!DNL Snowflake]. La valeur doit correspondre exactement. Pour obtenir des instructions, sélectionnez **[!UICONTROL Comment créer une intégration OAuth Snowflake]** dans la boîte de dialogue. L’URL de redirection diffère selon les environnements, alors copiez-la toujours à partir de la boîte de dialogue. |
     | **[!UICONTROL Informations d’identification de l’intégration OAuth]** | Choisissez d’où proviennent les informations d’identification. Sélectionnez **[!UICONTROL Saisir nouveau]** pour saisir l’identifiant client et le secret client, ou **[!UICONTROL Utiliser un secret existant]** pour sélectionner les secrets d’organisation qui les contiennent. |
     | **[!UICONTROL ID du client d’intégration OAuth]** | Obligatoire lorsque vous sélectionnez **[!UICONTROL Saisir nouveau]**. Identifiant client de votre intégration OAuth [!DNL Snowflake] gérée par le client. |
     | **[!UICONTROL Secret client de l’intégration OAuth]** | Obligatoire lorsque vous sélectionnez **[!UICONTROL Saisir nouveau]**. Secret client de la même intégration OAuth. Les membres ne saisissent jamais ces informations d’identification. |
     | **[!UICONTROL Rôle]** | Facultatif. Rôle utilisé par chaque session, demandé via le `session:role:ROLE_NAME` d’étendue OAuth. Le rôle doit être accordé à vos membres et ils doivent avoir accès au serveur MCP. Laissez le champ vide pour utiliser le rôle par défaut de chaque membre. |

     Un collègue dérive les points d’entrée OAuth de l’URL du compte et demande un jeton d’actualisation. Configurez l’intégration OAuth pour émettre des jetons d’actualisation. La portée demandée seule ne remplace pas la configuration de l’intégration.

     Collègue convertit le nom du rôle en majuscules. Les rôles créés avec un nom en minuscules entre guillemets ne peuvent pas être utilisés. Si l’intégration OAuth bloque le rôle ou si un membre ne dispose pas du rôle, la connexion ou l’accès peut échouer.

1. Sous **[!UICONTROL Outils disponibles pour les utilisateurs]**, sélectionnez les outils que les membres peuvent utiliser. Chaque serveur MCP [!DNL Snowflake] définit ses propres outils. Par conséquent, la boîte de dialogue n’affiche pas de liste fixe. Entrez les noms d&#39;outils tels que définis dans votre serveur MCP, et non les types d&#39;outils tels que `CORTEX_ANALYST_MESSAGE`. Pour afficher les noms des outils, exécutez `DESCRIBE MCP SERVER` dans [!DNL Snowflake].

   ![Boîte de dialogue Connecter Snowflake présentant le champ Rôle Snowflake, la section Outils disponibles pour les utilisateurs avec les champs Noms d’outils autorisés et Noms d’outils bloqués , l’avis d’accès et d’autorisations et un résumé avec l’authentification OAuth (intégration client), la connexion HTTP et un délai d’expiration de l’outil de 300 secondes.](./assets/snowflake/org-tools.png){width="500" zoomable="yes"}

   | Paramètre | Description |
   | --- | --- |
   | **[!UICONTROL Noms d’outils autorisés]** | Outils que les membres peuvent utiliser. Séparez les noms par des virgules ou des espaces. Laissez le champ vide pour autoriser chaque outil exposé par le serveur, à l’exception des outils bloqués. |
   | **[!UICONTROL Noms d’outils bloqués]** | Les outils que les membres ne peuvent jamais utiliser. Séparez les noms par des virgules ou des espaces. Les outils bloqués restent indisponibles même si vous les autorisez également. |

   >[!IMPORTANT]
   >
   >Si vous laissez le champ **[!UICONTROL Noms d’outils autorisés]** vide, les membres peuvent utiliser chaque outil, y compris tout outil d’exécution SQL. Les outils d’exécution SQL exécutent SQL en tant qu’identité connectée. Passez en revue les définitions d’outils sur votre serveur et autorisez uniquement les outils dont votre entreprise a besoin.

   Les descriptions des outils ne remplacent pas les privilèges [!DNL Snowflake] ou d’autres contrôles d’accès. Pour [!DNL Cortex Analyst] outils, configurez une vue sémantique et les octrois requis, y compris le rôle de base de données `SNOWFLAKE.CORTEX_USER`. Pour les outils [!DNL Cortex Agent], configurez des outils en lecture seule et désactivez l’exécution du code dans [!DNL Snowflake]. Les membres ne peuvent pas modifier la sélection d’outils.

1. Vérifiez **[!UICONTROL Accès et autorisations]**, puis sélectionnez **[!UICONTROL Enregistrer la connexion]**. La carte **[!UICONTROL Snowflake Cortex AI]** affiche **[!UICONTROL Configuration enregistrée]**.

   Sélectionnez **[!UICONTROL Afficher la configuration]** pour consulter l’URL du serveur, le type d’authentification et la stratégie de l’outil. Sélectionnez ensuite **[!UICONTROL Tester la connexion]** pour vérifier l’accès et découvrir les outils du serveur.

   Les nouvelles connexions [!DNL Snowflake] utilisent un délai d’expiration d’outil de 300 secondes. Une connexion plus ancienne sans délai d’expiration enregistré peut utiliser la valeur par défaut de 60 secondes. Vérifiez le délai d’expiration affiché pour une connexion existante.

Un test réussi ne confirme pas que chaque outil ou objet de [!DNL Snowflake] est disponible pour chaque membre.

## Utiliser le connecteur en tant que membre {#use-as-member}

Une fois qu’un administrateur a configuré le connecteur, ouvrez-le à partir de votre propre vue **[!UICONTROL Personnalisations]**.

1. Ouvrez **[!UICONTROL Personnalisations]**, sélectionnez **[!UICONTROL Utilisateur]**, puis **[!UICONTROL Connecteurs externes]**.

   Si la carte **[!UICONTROL Snowflake Cortex AI]** s’affiche **[!UICONTROL Non configuré]**, demandez à votre administrateur de [configurer le connecteur](#configure-organization).

1. Ouvrez **[!UICONTROL Snowflake Cortex AI]**. Les détails du connecteur sont en lecture seule pour les membres. Vous ne pouvez pas modifier l’URL du serveur, les informations d’identification ou la sélection d’outils.

1. Si la connexion utilise un compte de service d’organisation, les requêtes utilisent l’identité de l’organisation. Vous n’avez pas besoin de vous connecter. Ne saisissez ou ne partagez jamais le PAT.

1. Si la connexion utilise la connexion par personne, démarrez la connexion et authentifiez-vous avec le compte [!DNL Snowflake] prévu. Effectuez toutes les étapes d’authentification unique (SSO) ou d’authentification multifacteur (MFA) requises. Confirmez l’organisation, l’application et le rôle demandés, le cas échéant.

1. Si nécessaire, sélectionnez **[!UICONTROL Tester la connexion]**. Un test réussi indique **[!UICONTROL Connexion réussie]** et le nombre d’outils disponibles.

   ![Détails du connecteur Snowflake affichant un statut Connecté, un message de réussite de la connexion avec cinq outils disponibles, un avis indiquant que l’administrateur a configuré le connecteur et l’URL du serveur, l’option de connexion, l’authentification, la connexion et le délai d’expiration de l’outil.](./assets/snowflake/member-details.png){width="700" zoomable="yes"}

   Avant un test réussi, les détails peuvent n’afficher que les noms d’outils autorisés par votre administrateur ou vous inviter à exécuter le test. Après le test, chaque outil apparaît avec sa description.

   ![Détails du connecteur Snowflake affichant le type de connexion, le délai d’expiration de l’outil, le statut de connexion, les boutons Se déconnecter et Actualiser, ainsi que cinq exemples d’outils activés par l’administrateur.](./assets/snowflake/member-tools.png){width="700" zoomable="yes"}

Les outils de cet exemple sont définis par un serveur MCP [!DNL Snowflake]. Les outils affichés dépendent de votre serveur et de la sélection d’outils de votre administrateur.

Les détails d’authentification de la connexion indiquent si elle utilise un PAT, un OAuth de machine ou un OAuth par personne. Pour déconnecter votre compte [!DNL Snowflake], sélectionnez **[!UICONTROL Se déconnecter]**.

Un statut **[!UICONTROL Connecté]** ne garantit pas l’accès à un outil ou à un objet de données spécifique. [!DNL Snowflake] subventions, les politiques et le rôle sélectionné s&#39;appliquent toujours.

## Résolution des problèmes d’accès {#troubleshoot-access}

Si la configuration, la connexion ou l’accès échoue, vérifiez les points suivants auprès de votre administrateur :

| Problème | Éléments à vérifier |
| --- | --- |
| L’URL du serveur est refusée | L’URL utilise HTTPS ainsi que le chemin d’accès `/api/v2/databases/<database>/schemas/<schema>/mcp-servers/<server-name>` complet. Le nom d’hôte du compte n’a pas de traits de soulignement et l’URL n’a pas d’informations d’identification. |
| Le chemin d’accès ne peut pas être créé ni utilisé | La politique réseau, la politique d’authentification, l’expiration du jeton et le rôle du compte de service. Si vous utilisez un secret existant, vérifiez qu’il contient la valeur complète de l’en-tête `Authorization`. |
| L’URL de redirection OAuth ne correspond pas. | L’intégration OAuth [!DNL Snowflake] possède l’URL de redirection exacte à partir du même environnement Coworker. |
| La connexion réussit, mais les requêtes échouent | Le rôle est accordé au membre et autorisé par l’intégration OAuth. L’intégration génère des jetons d’actualisation et l’identifiant client et le secret appartiennent à l’intégration prévue. |
| Un outil est manquant ou refusé | Les paramètres **[!UICONTROL Noms d’outils autorisés]** et **[!UICONTROL Noms d’outils bloqués]**, la disponibilité de l’outil sur le serveur MCP et les autorisations [!DNL Snowflake] sur le serveur, l’outil et les objets sous-jacents. |
| Un appel d’outil expire | La **[!UICONTROL expiration de l’outil]** dans les détails du connecteur. Les nouvelles connexions utilisent 300 secondes. Les connexions plus anciennes sans temporisation enregistrée peuvent utiliser 60 secondes. |
