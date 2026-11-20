---
title: Connecteur externe Slack
description: Découvrez comment configurer le connecteur externe Slack dans CX Enterprise Coworker avec votre propre application Slack et connectez-vous pour utiliser vos conversations Slack dans la conversation.
role: Admin, User
level: Beginner
badgeBeta: label="Beta" type="Informative" tooltip="Ce connecteur est en version bêta."
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
hide: true
source-git-commit: 877954880bf6fda5151dcb343af92888db21cef4
workflow-type: tm+mt
source-wordcount: '2268'
ht-degree: 0%
---

# Connecteur externe Slack {#slack}

Utilisez le connecteur externe [!DNL Slack] pour travailler avec vos [!DNL Slack] conversations dans Adobe CX Enterprise Coworker. Après avoir configuré le connecteur, demandez à Coworker de rechercher des messages et des fichiers, de lire les canaux et les threads et de trouver des personnes. Vous pouvez également envoyer des messages et des réponses, si votre administrateur active ces outils. Le connecteur utilise le serveur MCP (Model Context Protocol) distant officiel hébergé par [!DNL Slack].

>[!AVAILABILITY]
>
>Le connecteur externe [!DNL Slack] est en version bêta. La documentation et les fonctionnalités peuvent changer.

## Configuration du connecteur {#connector-configuration}

Le processus de configuration du connecteur comprend trois parties distinctes :

* Préparation de l’application **[!DNL Slack]:** le propriétaire d’une application [!DNL Slack] prépare une application éligible, enregistre l’URL de redirection de Coworker et définit les portées utilisateur. Adobe ne fournit pas d’application [!DNL Slack] gérée.
* **Configuration de l’organisation :** Un administrateur Collègue configure le connecteur une seule fois pour l’ensemble de l’organisation. L’administrateur saisit les informations d’identification de l’application et choisit les portées OAuth de l’utilisateur et les outils que les membres peuvent utiliser.
* **Connexion du membre :** Chaque membre se connecte avec son propre compte [!DNL Slack]. Les membres ne peuvent accéder qu&#39;au contenu auquel leur compte [!DNL Slack] peut accéder.

Le connecteur n&#39;utilise pas de robot partagé ou d&#39;identité partagée [!DNL Slack]. Un collègue envoie des messages et des réponses en tant que membre connecté. L&#39;enregistrement de la configuration de l&#39;organisation ne permet pas de connecter des membres ou d&#39;accorder un accès [!DNL Slack] supplémentaire. Chaque membre doit se connecter séparément.

## Conditions préalables {#prerequisites}

Avant de commencer, vérifiez que vous disposez des éléments suivants :

* **Accès des collaborateurs :** compte autorisé à gérer les connecteurs d&#39;organisation, dans une organisation où le connecteur [!DNL Slack] est disponible.
* **Une application [!DNL Slack] :** une application interne ou une application [!DNL Slack Marketplace] approuvée pour votre espace de travail. Vous avez également besoin d’un propriétaire d’application qui peut confirmer les portées d’utilisateur approuvées et modifier les paramètres de l’application.
* **Informations d’identification de l’application :** l’identifiant client et le secret client de l’application, partagés via votre processus approuvé pour le traitement des informations d’identification.
* **Un outil et une décision de portée :** les outils de lecture, de messagerie et de brouillon que votre organisation prévoit d’activer, ainsi que les portées OAuth de l’utilisateur qu’elle prévoit de demander.
* **Un espace de travail ou un canal de test :** Un emplacement pour vérifier la connexion avec les membres qui acceptent de le tester. N’envoyez pas de messages de test dans les canaux client ou de production.

>[!IMPORTANT]
>
>Ne partagez jamais de secrets clients, de jetons d’accès ou d’autres informations d’identification dans des captures d’écran, des conversations ou des tickets d’assistance. Saisissez les informations d’identification uniquement dans les champs sécurisés de la boîte de dialogue de configuration.

## Préparation de l’application Slack {#prepare-slack-app}

Avant de configurer le connecteur dans Coworker, le propriétaire de l’application prépare l’application [!DNL Slack]. Un administrateur ou une administratrice d’application d’organisation ou d’espace de travail peut également devoir l’approuver. Pour connaître la configuration requise pour [!DNL Slack], consultez [Serveur MCP Slack](https://docs.slack.dev/ai/slack-mcp-server/) dans la documentation du développeur [!DNL Slack].

### Choisir une application éligible {#choose-eligible-app}

[!DNL Slack] prend en charge son serveur MCP uniquement pour les applications personnalisées internes et les applications publiées dans le [!DNL Slack Marketplace]. Les applications non répertoriées distribuées en dehors de votre organisation ne peuvent pas utiliser le serveur MCP [!DNL Slack]. Activer la distribution publique seule ne rend pas une application éligible.

1. Sélectionnez l’espace de travail ou l’organisation qui possédera l’application, ainsi que le propriétaire de l’application.
1. Dans [Slack app management](https://api.slack.com/apps), créez une application dans cet espace de travail. Pour réutiliser une application éligible existante, commencez par obtenir l’approbation de son propriétaire.
1. Dans les paramètres de l&#39;application, sélectionnez **[!UICONTROL Informations de base]** > **[!UICONTROL Informations d&#39;identification de l&#39;application]**. Notez les valeurs suivantes : **[!UICONTROL ID client]** et **[!UICONTROL Secret client]**.

   Saisissez uniquement ces deux valeurs dans Collègue. N’utilisez pas l’ID d’application, le secret de signature, un jeton de robot ou un jeton au niveau de l’application.

### Enregistrer l’URL de redirection {#register-redirect-url}

Enregistrez l’URL de redirection de Coworker dans votre application [!DNL Slack] :

1. Dans Coworker, ouvrez la boîte de dialogue **[!UICONTROL Connecter Slack]**, comme décrit dans [Configurer le connecteur pour votre organisation](#configure-organization). Copiez la valeur complète de l’URL de **[!UICONTROL redirection]**.

   Vous pouvez ouvrir la boîte de dialogue pour copier l’URL avant de terminer ou d’enregistrer la configuration.

1. Dans les paramètres de l’application [!DNL Slack], sélectionnez **[!UICONTROL OAuth et autorisations]**. Sous **[!UICONTROL URL de redirection]**, ajoutez l’URL de redirection complète, puis enregistrez.

Copiez toujours l’URL de redirection de la boîte de dialogue Collègue dans l’environnement que vous configurez. Enregistrez le schéma exact, le nom d’hôte, le port, le cas échéant, et le chemin d’accès. Ne créez pas l’URL vous-même et ne réutilisez pas une URL de redirection à partir d’un autre environnement. Si vous utilisez plusieurs environnements, enregistrez séparément chaque URL de redirection.

### Définition des portées d’utilisateurs {#set-user-scopes}

Le connecteur utilise les portées OAuth des utilisateurs, qui autorisent le compte de chaque membre. Il n’utilise pas les portées de robots.

1. Dans les paramètres de l’application [!DNL Slack], sélectionnez **[!UICONTROL OAuth et autorisations]** > **[!UICONTROL Étendues]** > **[!UICONTROL Étendues de jetons d’utilisateur]**.
1. Ajoutez les étendues d’utilisateurs approuvées par votre organisation. Comparez-les aux [portées par défaut](#review-scopes) dans Coworker et ajoutez uniquement les portées que vous prévoyez de demander.

   Les étendues par défaut sont l&#39;ensemble de fonctionnalités par défaut de Coworker, et non le minimum requis par [!DNL Slack]. Utilisez les portées `search:read.*` granulaires, et non l’ancienne portée `search:read`. Dans un manifeste d&#39;application, les portées d&#39;utilisateur appartiennent à `oauth_config.scopes.user`, et non à `oauth_config.scopes.bot`.

L&#39;étendue de l&#39;utilisateur `chat:write` permet à Coworker d&#39;envoyer des messages en tant que membre connecté. Si votre organisation ne prévoit pas d’envoyer de messages, laissez-la de côté.

Votre espace de travail ou votre organisation [!DNL Slack] Entreprise peut nécessiter l’approbation de l’application et la révision de la portée. L’approbation de l’application ne remplace pas le consentement de chaque membre. Une politique qui autorise uniquement les applications [!DNL Slack Marketplace] à bloquer une application interne. Pour plus d&#39;informations, voir [Gérer l&#39;approbation des applications pour votre espace de travail](https://slack.com/help/articles/222386767-Manage-app-approval-for-your-workspace).

Si votre application utilise des restrictions d&#39;adresses IP autorisées, [!DNL Slack] les applique également aux requêtes MCP. Contactez votre représentant Adobe pour confirmer les adresses à autoriser. Ne devinez pas les plages d’adresses IP. Certaines fonctionnalités, telles que la recherche sémantique, peuvent dépendre de votre plan [!DNL Slack].

### Vérifier les paramètres irréversibles de l’application {#review-irreversible-settings}

Un collègue se connecte en tant que client OAuth confidentiel avec l’ID client et le secret client. Certains paramètres de l&#39;application [!DNL Slack] ne peuvent pas être inversés. Consultez les éléments suivants avant de les modifier :

* **Clé de vérification pour l’échange de code (PKCE) :** N’activez pas le paramètre PKCE [!DNL Slack] pour ce connecteur sans confirmation. [!DNL Slack] indique que ce paramètre transforme l’application en client public et que seule la prise en charge de [!DNL Slack] peut l’inverser. Pour plus d&#39;informations, voir [Utilisation de PKCE](https://docs.slack.dev/authentication/using-pkce/).
* Rotation des jetons **La rotation des jetons** [!DNL Slack] ne peut pas être désactivée après son activation. Contactez votre représentant Adobe avant de l’activer pour cette application. Pour plus d&#39;informations, voir [Utilisation de la rotation de jeton](https://docs.slack.dev/authentication/using-token-rotation/).

### Fonctionnalités de robots non requises {#bot-features-not-required}

Le connecteur n’a pas besoin des deux fonctionnalités. Vous n’avez pas besoin de portées de jeton de robot, d’une URL de requête [!DNL Events API], d’une URL de requête d’interactivité, de webhooks entrants, de commandes à barre oblique, de [!DNL Socket Mode] ou de jetons au niveau de l’application. Si une application existante utilise ces fonctionnalités à d’autres fins, conservez-les.

Le serveur MCP [!DNL Slack] ne prend pas en charge l&#39;enregistrement client dynamique ou les événements envoyés par le serveur (SSE). Coworker utilise votre application enregistrée et le transport HTTP en flux continu.

## Configuration du connecteur pour votre organisation {#configure-organization}

Les administrateurs rendent le connecteur [!DNL Slack] disponible pour tous les membres de l’organisation. Les modifications apportées à la page d’organisation s’appliquent à tous les utilisateurs de votre organisation. Terminez [Préparer votre application Slack](#prepare-slack-app) avant la connexion des membres.

1. Ouvrez **[!UICONTROL Personnalisations]**, sélectionnez **[!UICONTROL Org]**, puis **[!UICONTROL Connecteurs externes]**. Sur la carte **[!UICONTROL Slack]**, sélectionnez **[!UICONTROL Configurer]**.

   La boîte de dialogue **[!UICONTROL Connecter Slack]** s’ouvre. Le connecteur utilise l’URL fixe [!DNL Slack] du serveur MCP, `https://mcp.slack.com/mcp`. Utilisez l’étendue de l’organisation pour cette configuration, et non une connexion personnelle.

1. Assurez-vous que l’**[!UICONTROL URL de redirection]** sous **[!UICONTROL l’application Slack]** est enregistrée dans votre application, comme décrit dans la section [Enregistrement de l’URL de redirection](#register-redirect-url). Saisissez ensuite l’**[!UICONTROL ID client]** et le **[!UICONTROL Secret client]** de votre application. Les deux champs sont obligatoires.

   Ne saisissez pas l’ID de l’application, le secret de signature ou un jeton de robot. Coworker stocke les informations d’identification comme des secrets, et non comme des paramètres de connecteur en texte brut.

   ![Boîte de dialogue Connecter Slack présentant la section de l’application Slack avec une URL de redirection expurgée, des champs d’ID client et de secret client vides, les portées OAuth par défaut de l’utilisateur et les premiers outils disponibles pour les utilisateurs.](./assets/slack/org-configure.png){width="500" zoomable="yes"}

1. Vérifiez les **[!UICONTROL portées OAuth de l’utilisateur]**. Pour plus d’informations, consultez [Vérification des portées OAuth de l’utilisateur](#review-scopes).

1. Sous **[!UICONTROL Outils disponibles pour les utilisateurs]**, supprimez tous les outils que les membres ne doivent pas utiliser. Au moins un outil doit rester. Pour plus d&#39;informations, voir [Outils disponibles](#available-tools).

1. Vérifiez les **[!UICONTROL accès et autorisations]**, puis sélectionnez **[!UICONTROL Enregistrer la connexion]**. La carte **[!UICONTROL Slack]** affiche la configuration **[!UICONTROL enregistrée]**.

   La boîte de dialogue affiche également la méthode **[!UICONTROL Authentification]**, le type **[!UICONTROL Connexion]** et le délai d’expiration de l’outil ****. Un collègue n’enregistre pas la configuration lorsqu’un champ d’informations d’identification ou la liste d’étendue est vide.

   Rechargez la page, sélectionnez **[!UICONTROL Afficher la configuration]** et confirmez que la configuration et votre sélection d&#39;outils sont enregistrées avant la connexion des membres.

   ![Boîte de dialogue Connecter Slack présentant les portées OAuth de l’utilisateur, les 16 outils disponibles pour les utilisateurs, l’avis d’accès et d’autorisations, ainsi que les paramètres d’authentification OAuth, de connexion HTTP et de délai d’expiration de l’outil de 60 secondes.](./assets/slack/org-scopes-tools.png){width="500" zoomable="yes"}

L&#39;enregistrement ne vous connecte pas, vous ou un membre, à [!DNL Slack]. Pour vérifier la connexion, connectez-vous en tant que vous-même, comme décrit dans [Connexion en tant que membre](#sign-in-as-a-member).

### Vérifier les portées OAuth de l’utilisateur {#review-scopes}

Le champ **[!UICONTROL Portées OAuth de l’utilisateur]** est obligatoire. Séparez les portées par des espaces ou des virgules et faites correspondre les portées utilisateur approuvées pour votre application. Par défaut, le champ contient les 22 portées suivantes :

```text
search:read.public search:read.private search:read.im search:read.mpim search:read.files search:read.users channels:history groups:history im:history mpim:history channels:read groups:read im:read mpim:read users:read users:read.email files:read canvases:read lists:read emoji:read reactions:read chat:write
```

Votre espace de travail peut ne pas approuver toutes les portées par défaut. Examinez les portées demandées avec le propriétaire de l’application.

>[!IMPORTANT]
>
>Les portées par défaut incluent le contenu privé, tel que les canaux privés, les messages de groupe et les messages directs. Ils incluent également `chat:write`, qui permet à un collègue d&#39;envoyer des messages et des réponses en tant que membre connecté. Décidez explicitement si votre organisation active les outils d’envoi de messages. La suppression d’un outil ne supprime pas ses portées OAuth. Si vous ne souhaitez pas que les membres envoient des messages, supprimez l’outil `slack_send_message` et la portée `chat:write`.

La sélection d’outils et les portées OAuth sont indépendantes. Lorsque vous restreignez l’accès, passez en revue la liste d’outils et le champ de l’étendue. Un outil activé ne donne pas à un membre un accès [!DNL Slack] supérieur à celui de son compte.

### Outils disponibles {#available-tools}

Le connecteur [!DNL Slack] fournit les 16 outils suivants. Par défaut, ils sont tous disponibles pour les membres.

| Fonctionnalité | Outil |
| --- | --- |
| Rechercher | `slack_search_public` |
| Rechercher | `slack_search_public_and_private` |
| Rechercher | `slack_search_channels` |
| Rechercher | `slack_search_users` |
| Lire les conversations | `slack_read_channel` |
| Lire les conversations | `slack_read_thread` |
| Lire les conversations | `slack_list_channel_members` |
| Lire les conversations | `slack_list_user_channels` |
| Lecture de contenu et de profils | `slack_read_canvas` |
| Lecture de contenu et de profils | `slack_read_user_profile` |
| Lecture de contenu et de profils | `slack_read_file` |
| Lecture de contenu et de profils | `slack_read_list` |
| Emoticônes et réactions | `slack_search_emojis` |
| Emoticônes et réactions | `slack_get_reactions` |
| Messages et brouillons | `slack_send_message` |
| Messages et brouillons | `slack_send_message_draft` |

Le connecteur n’est pas en lecture seule. Les membres peuvent envoyer des messages et des réponses, sauf si vous supprimez l&#39;outil `slack_send_message`. La création de canal, les messages planifiés, les chargements de fichiers, l’ajout de réactions et les modifications de la zone de travail ou de la liste ne sont pas inclus.

## Se connecter en tant que membre {#sign-in-as-a-member}

Une fois qu’un administrateur a configuré le connecteur, chaque membre se connecte avec son propre compte [!DNL Slack]. Vous n’avez pas besoin du secret client pour vous connecter.

1. Ouvrez **[!UICONTROL Personnalisations]**, sélectionnez **[!UICONTROL Utilisateur]**, puis **[!UICONTROL Connecteurs externes]**.

1. Recherchez la carte **[!UICONTROL Slack]**. Si la carte indique **[!UICONTROL Non configuré]** et **[!UICONTROL Pas encore disponible. Votre administrateur doit configurer ceci.]**, demandez à votre administrateur de [configurer le connecteur](#configure-organization).

   Ne demandez pas et ne copiez pas le secret client de l’organisation.

1. Une fois que votre administrateur a configuré le connecteur, la carte **[!UICONTROL Slack]** affiche **[!UICONTROL Connexion requise]**. Sélectionnez **[!UICONTROL Se connecter]** sur la carte.

   Vous pouvez également ouvrir les détails du connecteur **[!UICONTROL Slack]**. Avant de vous connecter, la section **[!UICONTROL Connexion]** affiche **[!UICONTROL Non connecté]**, avec un bouton **[!UICONTROL Se connecter]**.

   ![Détails du connecteur Slack pour un membre, affichant le statut Connexion requise, le bouton Tester la connexion, l&#39;URL du serveur, Chaque utilisateur se connecte, un lien Non connecté à l&#39;aide d&#39;un bouton Se connecter et les outils activés par votre administrateur.](./assets/slack/member-details.png){width="700" zoomable="yes"}

1. Complétez l’autorisation [!DNL Slack] avec le compte [!DNL Slack] et l’espace de travail que vous prévoyez d’utiliser. Passez en revue les autorisations demandées et les exigences d’approbation de Workspace.

   >[!IMPORTANT]
   >
   >Continuez uniquement si vous reconnaissez l’application et que votre organisation approuve l’accès demandé.

1. Revenez à Coworker et vérifiez le statut de la connexion. Sélectionnez **[!UICONTROL Tester la connexion]**, puis [vérifier l’accès à Slack](#check-access) avant de vous fier à la connexion.

1. Examinez attentivement les actions de messagerie. Un collègue envoie des messages et des réponses en tant que compte [!DNL Slack].

En tant que membre, vous pouvez tester la connexion ou vous déconnecter, mais vous ne pouvez pas modifier les paramètres d’organisation. Vous ne pouvez accéder qu&#39;au contenu autorisé par [!DNL Slack] et les étendues accordées. Ce contenu inclut les conversations privées uniquement lorsque votre propre compte [!DNL Slack] peut y accéder.

Pour déconnecter votre compte [!DNL Slack] du connecteur, sélectionnez **[!UICONTROL Se déconnecter]**.

## Vérifier l’accès à Slack {#check-access}

Pour confirmer que le connecteur peut lire votre contenu [!DNL Slack], démarrez une conversation et saisissez une invite en lecture seule. Vérifiez que votre administrateur a activé l’outil `slack_list_user_channels`.

Exemple d’invite :

* « Avec Slack, répertoriez jusqu’à cinq canaux auxquels j’appartiens. Afficher uniquement les noms de canal. N’envoyez pas de messages, ne créez pas de brouillons et ne modifiez rien. »

Si votre entreprise active des outils de messagerie, testez l’envoi uniquement dans un canal réservé à des fins de test et avec approbation. Demandez à un second membre de se connecter séparément et confirmez que chaque membre ne voit que son propre contenu [!DNL Slack].

## Résolution des problèmes d’accès {#troubleshoot-access}

Si la configuration, la connexion ou l’accès échoue, vérifiez les points suivants auprès de votre administrateur :

| Problème | Éléments à vérifier |
| --- | --- |
| Impossible d’enregistrer la configuration | Saisissez l’ID client et le secret client, conservez au moins une portée OAuth d’utilisateur et conservez au moins un outil. Ne saisissez pas d’ID d’application, de secret de signature ou de jeton de robot. |
| L&#39;URL de redirection **[!UICONTROL URL]** est manquante ou [!DNL Slack] signale une incohérence de redirection | Comparez l’URL de redirection complète de la boîte de dialogue Collègue, y compris le schéma, l’hôte, le port et le chemin d’accès, aux **[!UICONTROL URL de redirection]** enregistrées dans l’application [!DNL Slack]. Si l’URL est manquante ou si les valeurs sont différentes, contactez votre représentant Adobe. |
| Échec de la connexion ou des requêtes à [!DNL Slack] | Vérifiez l&#39;approbation de l&#39;application, les portées utilisateur accordées, le compte [!DNL Slack] et l&#39;espace de travail avec lesquels vous vous êtes connecté, ainsi que toute restriction d&#39;adresse IP sur l&#39;application. Si les requêtes continuent d’échouer, déconnectez-vous, puis reconnectez-vous. |
| Une action de lecture ou d’envoi n’est pas disponible | Vérifiez la sélection d’outils de votre organisation, les portées demandées et accordées, ainsi que les autorisations [!DNL Slack] du membre. Ces paramètres sont indépendants. |
| Un membre ne peut pas modifier les paramètres de l’application | Ce comportement est prévu pour une connexion gérée par l’organisation. Demandez à l’administrateur. Les membres ne saisissent jamais le secret client de l’organisation. |
