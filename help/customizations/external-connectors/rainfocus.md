---
title: Connecteur externe RainFocus
description: Découvrez comment configurer le connecteur externe RainFocus dans CX Enterprise Coworker pour votre organisation et connectez-vous avec RainFocus pour utiliser les outils de données d’événement dans le chat.
role: Admin, User
level: Beginner
badgeBeta: label="Beta" type="Informative" tooltip="Ce connecteur est en version bêta."
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
hide: true
source-git-commit: e65f811f1e9c27de372ce924301b68f20ab9c1a6
workflow-type: tm+mt
source-wordcount: '2116'
ht-degree: 0%
---

# Connecteur externe RainFocus {#rainfocus}

Utilisez le connecteur externe [!DNL RainFocus] pour travailler avec vos données d’événement [!DNL RainFocus] dans Adobe CX Enterprise Coworker. Une fois que vous avez configuré le connecteur, interrogez votre collègue sur les sessions, les participants et les attributs personnalisés auxquels votre compte [!DNL RainFocus] peut accéder. Le connecteur utilise un profil MCP [!DNL RainFocus], un serveur MCP (Model Context Protocol) hébergé par [!DNL RainFocus].

>[!AVAILABILITY]
>
>Le connecteur externe [!DNL RainFocus] est en version bêta. La documentation et les fonctionnalités peuvent changer.

## Configuration du connecteur {#connector-configuration}

Le processus de configuration du connecteur comprend trois parties distinctes :

* Préparation de **[!DNL RainFocus]:** un administrateur [!DNL RainFocus] met en service un profil MCP, active ses outils et fournit l’URL du profil. Chaque membre a besoin d’un compte [!DNL RainFocus] doté du rôle approprié.
* **Configuration de l’organisation :** Un administrateur de collègues enregistre l’URL de profil MCP une seule fois pour l’ensemble de l’organisation. Le connecteur active une liste fixe d’outils de lecture.
* **Connexion du membre :** Chaque membre se connecte avec son propre compte [!DNL RainFocus]. Les membres ne peuvent accéder qu&#39;aux données autorisées par leur rôle [!DNL RainFocus] et le profil.

L’enregistrement de la configuration de l’organisation ne permet pas de connecter les membres, d’accorder les autorisations [!DNL RainFocus] ou d’exécuter un outil de données [!DNL RainFocus]. Chaque membre doit se connecter séparément.

## Conditions préalables {#prerequisites}

Avant de commencer, vérifiez que vous disposez des éléments suivants :

* **Accès d’un collègue :** compte administrateur d’un collègue avec paramètres d’organisation activé, dans une organisation où le connecteur [!DNL RainFocus] est disponible.
* **Un profil MCP :** Un profil MCP [!DNL RainFocus] fourni et son URL de profil HTTPS complète, fournie par votre administrateur [!DNL RainFocus]. Pour plus d&#39;informations, voir [Obtenir l&#39;URL du profil MCP](#get-profile-url).
* **Comptes membres :** pour chaque membre, un compte [!DNL RainFocus] doté d’un rôle de sécurité qui lui donne accès aux données dont il a besoin.

Vous ne saisissez pas d’ID client, de secret client ou de jeton d’accès dans Coworker. Chaque membre se connecte à [!DNL RainFocus] avec son propre compte.

## Préparer l&#39;accès à [!DNL RainFocus] {#prepare-rainfocus}

Avant de configurer le connecteur dans Coworker, préparez le profil MCP et l&#39;accès des membres dans [!DNL RainFocus]. [!DNL RainFocus] possède le profil, ses outils activés, les rôles des membres et les frais. Coworker stocke l’URL du profil et la liste des outils pour votre organisation, ainsi que la connexion de chaque membre.

### Obtenir l’URL du profil MCP {#get-profile-url}

[!DNL RainFocus] configure généralement les profils MCP pour ses clients en fonction de leurs besoins. Si votre administrateur [!DNL RainFocus] configure le profil, le processus est le suivant :

1. Dans [!DNL RainFocus], ouvrez **[!UICONTROL Suite d’intégration]** > **[!UICONTROL Profils actifs]** > **[!UICONTROL Profils MCP]**, puis créez un profil.
1. Activez uniquement les outils dont votre cas d’utilisation a besoin et laissez les autres outils désactivés.
1. Copiez l’URL du serveur MCP générée. L’URL est spécifique au profil.

Fournissez l’URL complète à l’administrateur ou l’administratrice Coworker qui configure le connecteur. Ne devinez pas le nom d’un profil et ne créez pas l’URL vous-même. Pour plus d’informations, consultez l’annonce [Profils MCP RainFocus](https://www.rainfocus.com/company/news-press/rainfocus-launches-ai-agent-connectivity-for-event-data-with-mcp-profiles/).

### Confirmer l’accès du membre {#confirm-member-access}

Chaque membre se connecte avec son propre compte [!DNL RainFocus]. Le rôle de sécurité du compte et les outils activés dans le profil contrôlent à quelles données un membre peut accéder. Demandez à votre administrateur [!DNL RainFocus] de confirmer que chaque membre dispose du rôle le moins privilégié pour ses tâches.

## Configuration du connecteur pour votre organisation {#configure-organization}

Les administrateurs rendent le connecteur [!DNL RainFocus] disponible pour tous les membres de l’organisation. Les modifications apportées à la page d’organisation s’appliquent à tous les utilisateurs de votre organisation. L’étendue **[!UICONTROL Org]** s’affiche uniquement pour les administrateurs dont les paramètres d’organisation sont activés.

1. Ouvrez **[!UICONTROL Personnalisations]**, sélectionnez **[!UICONTROL Org]**, puis **[!UICONTROL Connecteurs externes]**.
1. Recherchez la carte **[!UICONTROL RainFocus]**, qui a un libellé Beta et affiche **[!UICONTROL Non configuré]**. Sélectionnez **[!UICONTROL Configurer]**.

1. Dans la boîte de dialogue **[!UICONTROL Configurer RainFocus]**, saisissez l’**[!UICONTROL URL du profil de développement]**. Utilisez l’URL de profil MCP complète fournie par votre administrateur [!DNL RainFocus].

   L&#39;URL doit commencer par `https://`. Il ne peut pas contenir d&#39;espaces, de barres obliques inverses, de chaîne de requête (`?`), de fragment (`#`), de nom d&#39;utilisateur ou de mot de passe, de port autre que le port par défaut ou de segments de chemin `.` ou `..`. Si l’URL ne correspond pas à une règle, Collègue affiche un message qui décrit la règle. Mon collègue ne vérifie que le format de l’URL. Il ne vérifie pas que le profil existe ou que vous pouvez l’utiliser.

1. Examinez les sections **[!UICONTROL Accès et autorisations]** et **[!UICONTROL Outil de lecture fixe]**. Le connecteur active les 10 outils de lecture et vous ne pouvez pas les ajouter, les supprimer ni les modifier dans cette boîte de dialogue. Certains outils renvoient les données personnelles des participants ou les exportations en bloc. Pour plus d&#39;informations, voir [Outils disponibles](#available-tools).

   ![Configurez la boîte de dialogue RainFocus affichant le champ URL de profil de développement vide, la section Accès et autorisations, la liste autorisée fixe d&#39;outil de lecture avec 10 outils et le bouton Enregistrer la connexion.](./assets/rainfocus/org-configure.png){width="500" zoomable="yes"}

1. Sélectionnez **[!UICONTROL Enregistrer la connexion]**. Pendant que Coworker enregistre la connexion, vous ne pouvez pas modifier ni annuler le formulaire.

Si l’enregistrement échoue, la boîte de dialogue affiche **[!UICONTROL Impossible d’enregistrer la connexion]** et conserve l’URL que vous avez saisie. Certains paramètres peuvent être enregistrés même en cas d’échec de l’enregistrement. Ouvrez à nouveau la configuration et vérifiez-la avant de réessayer. Pour éviter les modifications en conflit, assurez-vous qu’un seul administrateur configure le connecteur à la fois.

### Vérifier la configuration enregistrée {#verify-configuration}

Après avoir enregistré la connexion, vérifiez la configuration :

1. Après l’enregistrement, la boîte de dialogue ouvre les détails du connecteur enregistrés. Revenez à la liste **[!UICONTROL Connecteurs externes]** et confirmez que la carte **[!UICONTROL RainFocus]** affiche **[!UICONTROL Configuration enregistrée]** et **[!UICONTROL Afficher la configuration]**.
1. Rechargez la page, puis sélectionnez **[!UICONTROL Afficher la configuration]**.
1. Confirmez les détails suivants :

   * **[!UICONTROL Source]** affiche l’URL de profil que vous avez saisie.
   * **[!UICONTROL L&#39;authentification]** est présente.
   * **[!UICONTROL Stratégie d’outil]** > **[!UICONTROL Les noms ou modèles d’outils autorisés]** répertorient les 10 mêmes outils que la section [Outils disponibles](#available-tools).

1. Pour vérifier votre propre connexion, sélectionnez **[!UICONTROL Tester]**. Si un collègue vous demande de vous connecter, utilisez votre propre compte [!DNL RainFocus], comme décrit dans la section [Connexion en tant que membre](#sign-in-as-a-member).

   **[!UICONTROL Test]** répertorie les outils du serveur et met à jour le nombre **[!UICONTROL Outils]**. Si le serveur ne renvoie aucun outil, les informations indiquent **[!UICONTROL 0 outils disponibles]**. Si le test échoue, les détails indiquent **[!UICONTROL Échec de la connexion]**.

   ![Détails du connecteur rainfocus enregistrés affichant une source expurgée, la méthode d&#39;authentification rainfocus_login, un bouton Non connecté associé à un bouton de connexion et les boutons Tester et Supprimer.](./assets/rainfocus/org-details.png){width="700" zoomable="yes"}

Les contrôles **[!UICONTROL Connexion]**, **[!UICONTROL Test]** et de connexion sur les détails du connecteur s&#39;appliquent uniquement à votre propre connexion. Lorsque vous vous connectez en tant qu’administrateur, aucun membre n’est connecté. Un test réussi répertorie uniquement les outils. Le test n&#39;exécute pas un outil de données [!DNL RainFocus] et ne confirme pas qu&#39;un membre peut accéder à des données spécifiques.

Les détails du connecteur n’ont pas la possibilité de modifier l’URL du profil. **[!UICONTROL Supprimer]** ouvre une confirmation, puis supprime la connexion pour l’ensemble de l’organisation. Traiter la suppression comme une décision délibérée de l’administrateur et non comme une étape de dépannage.

### Outils disponibles {#available-tools}

Le connecteur [!DNL RainFocus] active une liste fixe de 10 outils de lecture :

| Outil | Zone de données |
| --- | --- |
| `get_attendeeInfo` | Participants |
| `get_attendee_load` | Participants |
| `get_attendee_search` | Participants |
| `get_attribute_load` | Attributs personnalisés |
| `get_attribute_search` | Attributs personnalisés |
| `get_attributevalue_load` | Attributs personnalisés |
| `get_entityDataDump_attendee` | Participants, exportation en bloc |
| `get_entityDataDump_session` | Sessions, exportation en bloc |
| `get_session_load` | Sessions |
| `get_session_search` | Sessions |

Les outils qui ne figurent pas dans cette liste, y compris les outils que [!DNL RainFocus] ajoute ultérieurement, ne sont pas activés automatiquement. La liste ne remplace pas les [!DNL RainFocus] rôles de sécurité ou les paramètres d’outil du profil, qui contrôlent toujours l’accès aux données.

>[!IMPORTANT]
>
>Plusieurs outils peuvent renvoyer des données personnelles et des coordonnées sur les participants. Deux outils exportent des données en bloc et leurs résultats peuvent être volumineux. Les lectures peuvent également entraîner des frais en vertu de vos conditions [!DNL RainFocus]. Examinez ces outils avec vos propriétaires de gouvernance des données avant que les membres ne se connectent.

## Se connecter en tant que membre {#sign-in-as-a-member}

Une fois qu’un administrateur a configuré le connecteur, chaque membre se connecte avec son propre compte [!DNL RainFocus]. Vous n’avez pas besoin d’un ID client, d’un secret client ou d’un jeton d’accès pour vous connecter.

1. Ouvrez **[!UICONTROL Personnalisations]**, puis sélectionnez **[!UICONTROL Connecteurs externes]**. Les membres utilisent la portée **[!UICONTROL Utilisateur]** par défaut. Recherchez la carte **[!UICONTROL RainFocus]**.
1. Si la carte indique **[!UICONTROL Pas encore disponible. Votre administrateur doit configurer ceci.]**, demandez à votre administrateur de [configurer le connecteur](#configure-organization). Les membres ne peuvent pas saisir leur propre URL de profil.
1. Vérifiez le statut sur la carte. La carte indique **[!UICONTROL Connexion requise]**, **[!UICONTROL Connecté]**, **[!UICONTROL Configuré par votre administrateur]** ou un statut **[!UICONTROL Échec de la connexion]**.

   **[!UICONTROL Configuré par votre administrateur]** signifie que Coworker ne peut pas confirmer votre statut de connexion. Cela ne signifie pas que vous êtes connecté ou déconnecté.

1. Sélectionnez **[!UICONTROL Se connecter]**. Vous pouvez également ouvrir les détails de la carte et sélectionner **[!UICONTROL Se connecter]** dans la section **[!UICONTROL Connexion]**. Dans la fenêtre [!DNL RainFocus], effectuez la connexion, l’authentification unique (SSO), l’authentification multifacteur (MFA) et les invites de consentement. Vérifiez l’accès que vous approuvez.

   Si **[!UICONTROL L’autorisation Discover]** apparaît, Coworker lit les informations de connexion du serveur, et non ses outils. Si la détection échoue ou si le panneau demande un **[!UICONTROL identifiant client]** ou un **[!UICONTROL secret client]**, arrêtez-vous et contactez votre administrateur. Ne saisissez pas et ne supposez pas les informations d’identification.

   ![Détails du connecteur RainFocus pour un membre, affichant un statut de connexion obligatoire, une URL de serveur expurgée, chaque utilisateur se connecte, un lien Non connecté avec un bouton d&#39;autorisation Discover, et les 10 outils activés par votre administrateur.](./assets/rainfocus/member-details.png){width="700" zoomable="yes"}

1. Revenez à Coworker et confirmez que le statut indique **[!UICONTROL Connecté]**. Une fenêtre de connexion fermée seule ne confirme pas le succès. Si vous fermez la fenêtre trop tôt, rien ne change et vous pouvez réessayer.
1. Ouvrez les détails de la carte pour vérifier la configuration auprès de votre administrateur. Vous pouvez afficher l’**[!UICONTROL URL du serveur]**, les **[!UICONTROL outils de connexion]**, d’**[!UICONTROL authentification]** et d’**[!UICONTROL activés par votre administrateur]**.
1. Sélectionnez **[!UICONTROL Tester]** sur la carte ou **[!UICONTROL Tester la connexion]** dans les détails, pour vérifier la connexion à votre compte.

   Un test réussi indique que [!DNL RainFocus] a répondu à l&#39;aide de votre compte, avec le nombre d&#39;outils disponibles. Le test répertorie uniquement les outils. Il n’exécute pas d’outil de données et ne confirme pas l’accès à des événements ou enregistrements spécifiques. Pour renouveler votre connexion et répertorier à nouveau les outils, sélectionnez **[!UICONTROL Actualiser]**. Si Coworker ne peut pas renouveler votre connexion, le bouton affiche **[!UICONTROL Recharger les outils]** à la place, ce qui ne fait que répertorier à nouveau les outils.

1. Si le test échoue, Coworker indique **[!UICONTROL Impossible de se connecter à RainFocus]**, avec **[!UICONTROL Réessayer]** et **[!UICONTROL Détails techniques]**. Si vous êtes déconnecté, reconnectez-vous. Si le problème persiste, contactez votre administrateur.

Les membres peuvent se connecter, se déconnecter, tester, actualiser et afficher les outils activés. Les membres ne peuvent pas modifier ni supprimer la connexion à l’organisation, modifier l’URL du profil ou modifier les outils. Chaque membre qui ouvre les détails peut afficher l’URL du profil. Lorsqu’un administrateur se connecte, les autres membres ne sont pas connectés.

Pour déconnecter votre compte [!DNL RainFocus] du connecteur, sélectionnez **[!UICONTROL Se déconnecter]**. Vous pouvez vous reconnecter à tout moment.

## Vérifier l’accès aux données d’événement {#check-event-access}

Pour confirmer que vous pouvez utiliser les données [!DNL RainFocus], exécutez une vérification en lecture seule avec une requête étroite. Utilisez un événement pour lequel vous avez l’autorisation d’utiliser et évitez les outils qui renvoient des données de participant ou des exportations en bloc pour ce contrôle. Démarrez une conversation et saisissez une invite.

Exemple d’invite :

* « Avec RainFocus, trouvez jusqu’à cinq sessions auxquelles j’ai accès. Afficher uniquement le titre et l’ID de la session si ces champs sont renvoyés. N’exportez pas de données, ne renvoyez pas d’informations sur les participants et ne modifiez rien. »

Vérifiez que le résultat inclut les sessions attendues. Un résultat vide ne signifie pas toujours que le connecteur ne fonctionne pas. Vérifiez le compte [!DNL RainFocus] avec lequel vous vous êtes connecté, votre rôle de sécurité et les outils activés dans le profil. Si un résultat est volumineux de manière inattendue ou inclut des données sensibles, arrêtez et limitez votre requête.

## Résolution des problèmes d’accès {#troubleshoot-access}

Si vous ne pouvez pas accéder à vos données [!DNL RainFocus], vérifiez les points suivants auprès de votre administrateur :

| Problème | Éléments à vérifier |
| --- | --- |
| La carte **[!UICONTROL RainFocus]** est manquante | Vérifiez auprès de votre représentant Adobe que le connecteur est disponible pour votre organisation. |
| La portée **[!UICONTROL Org]** est manquante | Vérifiez que vous êtes un administrateur et que les paramètres d’organisation sont activés pour votre organisation. |
| Un collègue rejette l’URL du profil | Suivez la règle du message. Utilisez l&#39;URL de profil complète de votre administrateur [!DNL RainFocus] et ne devinez pas de nom de profil. |
| **[!UICONTROL Impossible d&#39;enregistrer la connexion]** apparaît | Certains paramètres peuvent être enregistrés. Ouvrez à nouveau la configuration et vérifiez-la avant de réessayer. Assurez-vous qu’un seul administrateur configure le connecteur à la fois. |
| La carte indique **[!UICONTROL Pas encore disponible. Votre administrateur doit configurer ceci.]** | La configuration de l’organisation est manquante. Demandez à votre administrateur de [configurer le connecteur](#configure-organization). |
| La connexion demande un **[!UICONTROL ID client]** ou un **[!UICONTROL secret client]** ou la découverte échoue | Arrêtez et contactez votre administrateur. Ne saisissez pas ou ne devinez pas les informations d’identification, et n’enregistrez pas d’application. |
| La connexion échoue après votre approbation de l&#39;accès dans [!DNL RainFocus] | Vérifiez le compte [!DNL RainFocus] et le rôle de sécurité que vous avez utilisés. Demandez à votre représentant Adobe et à [!DNL RainFocus] de vérifier la configuration de connexion pour votre environnement. Ne partagez pas l’URL de connexion. |
| **[!UICONTROL Le test]** réussit, mais les requêtes de données échouent | **[!UICONTROL Test]** répertorie uniquement les outils. Vérifiez votre rôle de sécurité [!DNL RainFocus], les outils activés dans le profil et les filtres dont l&#39;outil a besoin. |
| **[!UICONTROL Impossible de se connecter à RainFocus]** s&#39;affiche lorsque vous êtes connecté | Sélectionnez **[!UICONTROL Réessayer]**. Si le problème persiste, contactez votre administrateur. |
| Le résultat est volumineux de manière inattendue ou contient des données sensibles. | Arrêtez et limitez votre requête. Ne collez pas de données d’événement brutes dans les tickets ou les chats. |

Lorsque vous contactez l’assistance, incluez uniquement le texte de l’erreur, l’heure de l’erreur et votre environnement. Ne partagez pas de détails techniques, d’URL de profil, de captures de connexion, de mots de passe, de jetons ou de codes d’autorisation.
