---
title: Connecteur externe Microsoft Work IQ
description: Découvrez comment configurer le connecteur externe Microsoft Work IQ dans CX Enterprise Coworker avec votre application Entra et connectez-vous pour utiliser les données Microsoft 365 dans la conversation.
role: Admin, User
level: Beginner
badgeBeta: label="Beta" type="Informative" tooltip="Ce connecteur est en version bêta."
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
hide: true
source-git-commit: f87c1b3ac9c344a07cdc8d0861593c34c97cfc3e
workflow-type: tm+mt
source-wordcount: '1648'
ht-degree: 1%
---

# Connecteur externe Microsoft Work IQ {#microsoft-work-iq}

Utilisez le connecteur externe [!DNL Microsoft Work IQ] pour travailler avec vos données [!DNL Microsoft 365] dans Adobe CX Enterprise Coworker. Une fois que vous avez configuré le connecteur, demandez à vos collaborateurs de rechercher vos e-mails, fichiers, réunions et messages [!DNL Microsoft Teams], de passer en revue les événements de calendrier, etc. Le connecteur est un serveur MCP (Model Context Protocol) hébergé par [!DNL Microsoft].

>[!AVAILABILITY]
>
>Le connecteur externe [!DNL Microsoft Work IQ] est en version bêta. La documentation et les fonctionnalités peuvent changer.

## Configuration du connecteur {#connector-configuration}

Le processus de configuration du connecteur comprend deux parties distinctes :

* **Configuration de l’organisation :** un administrateur configure le connecteur une seule fois pour l’ensemble de l’organisation. L’administrateur connecte une application [!DNL Microsoft Entra] et sélectionne les outils que les membres peuvent utiliser.
* **Connexion au membre :** chaque membre se connecte avec son propre compte professionnel [!DNL Microsoft]. Les membres ne peuvent accéder qu’aux données auxquelles leur compte peut accéder.

L’enregistrement de la configuration de l’organisation ne connecte aucun membre et n’accorde aucune autorisation [!DNL Microsoft 365] supplémentaire. Chaque membre doit se connecter séparément.

La carte **[!UICONTROL Microsoft Work IQ]** mentionne une application OAuth partagée, disponible uniquement lorsque votre déploiement en configure une. Ne supposez pas qu’une application est déjà fournie. Cette page décrit comment connecter votre propre application [!DNL Microsoft Entra].

## Conditions préalables {#prerequisites}

Avant de commencer, vérifiez que vous disposez des éléments suivants :

* **Pour la configuration d’organisation :** compte autorisé à gérer les connecteurs d’organisation dans Coworker.
* **Pour l’application [!DNL Microsoft Entra] :** un administrateur [!DNL Microsoft Entra] qui peut enregistrer une application web et accorder le consentement administrateur.
* **Pour votre client [!DNL Microsoft] :** activé pour [!DNL Work IQ] client.
* **Pour la connexion du membre :** compte professionnel [!DNL Microsoft] éligible avec accès aux données que vous prévoyez d’utiliser.

## Configuration du connecteur pour votre organisation {#configure-organization}

Les administrateurs rendent le connecteur [!DNL Microsoft Work IQ] disponible pour tous les membres de l’organisation. Les modifications apportées à la page d’organisation s’appliquent à tous les utilisateurs de votre organisation.

1. Ouvrez **[!UICONTROL Personnalisations]**, sélectionnez **[!UICONTROL Organisation]**, puis **[!UICONTROL Connecteurs externes]**. Sur la carte **[!UICONTROL Microsoft Work IQ]**, sélectionnez **[!UICONTROL Configurer]**.

1. Dans la boîte de dialogue **[!UICONTROL Configurer Microsoft Work IQ pour votre organisation]**, passez en revue l’**[!UICONTROL URL du serveur]**, `https://workiq.svc.cloud.microsoft/mcp`. Préparez ensuite votre application [!DNL Microsoft Entra]. Pour connaître les exigences [!DNL Microsoft], sélectionnez **[!UICONTROL Instructions de configuration de Microsoft]** dans la boîte de dialogue.

   1. Enregistrez une application web dans [!DNL Microsoft Entra] ou utilisez-en une existante.
   1. Copiez l’**[!UICONTROL URL de redirection]** de la boîte de dialogue et enregistrez cette valeur exacte en tant qu’URI de redirection web sur l’application. L’URL de redirection diffère selon les environnements, alors copiez-la toujours à partir de la boîte de dialogue.
   1. Créez un secret client ou confirmez que le secret client existant est toujours valide. Vous avez besoin de la valeur secrète, pas de l’identifiant secret.
   1. Accordez le consentement administrateur pour l’autorisation `WorkIQAgent.Ask` déléguée et confirmez que [!DNL Work IQ] est activé pour votre client.

   Dans **[!UICONTROL Microsoft Entra tenant ID]**, saisissez votre tenant ID. Dans [!DNL Microsoft Entra], recherchez cette valeur dans **[!UICONTROL Aperçu]** > **[!UICONTROL ID de répertoire (client)]**.

   ![Boîte de dialogue Configurer Microsoft Work IQ pour votre organisation affichant l’URL du serveur, les champs « Avant d’enregistrer les exigences », l’URL de redirection, le champ « Identifiant du client Microsoft Entra » et les champs « Nouvelles informations d’identification ».](./assets/microsoft-work-iq/org-configure.png){width="500" zoomable="yes"}

1. Sous **[!UICONTROL D’où proviennent les informations d’identification]** sélectionnez l’une des options suivantes :

   * **[!UICONTROL Saisissez new]:** Dans **[!UICONTROL ID client de l’application OAuth]**, saisissez l’ID d’application (client) de votre application [!DNL Microsoft Entra]. Dans **[!UICONTROL Secret client de l’application OAuth]**, saisissez la valeur secrète. Coworker stocke la valeur secrète en tant que secret d’organisation.
   * **[!UICONTROL Utiliser un secret existant] :** dans **[!UICONTROL Secret contenant l’ID client]** et **[!UICONTROL Secret contenant le secret client]**, sélectionnez les secrets d’organisation enregistrés pour votre application. Si les bons secrets ne sont pas disponibles, sélectionnez **[!UICONTROL Saisir nouveau]** à la place. Vous devez toujours saisir l’ID client séparément.

   L’ID client, l’ID client et le secret client doivent tous appartenir à la même application et au même client. Si vous réutilisez des secrets enregistrés, vérifiez que le secret client n’a pas expiré. Ces informations d’identification d’application sont distinctes des mots de passe [!DNL Microsoft] que les membres utilisent pour se connecter.

   ![Utilisez une option de secret existant sélectionnée, avec les secrets d’organisation sélectionnés pour l’ID client et le secret client.](./assets/microsoft-work-iq/org-existing-secret.png){width="500" zoomable="yes"}

1. Sous **[!UICONTROL Outils disponibles pour les utilisateurs]**, sélectionnez les outils dont votre entreprise a besoin. Pour plus d’informations, voir [&#x200B; Outils disponibles &#x200B;](#available-tools). Vérifiez **[!UICONTROL Accès et autorisations]**, ce qui confirme que chaque personne se connecte séparément, puis sélectionnez **[!UICONTROL Enregistrer la configuration]**.

   ![Boîte de dialogue Configuration complète de Microsoft Work IQ pour votre organisation , avec les outils en lecture seule sélectionnés sous Outils disponibles pour les utilisateurs, l’outil de tâche et les outils de modification des données effacés, et l’avertissement Chaque personne se connecte séparément sous Accès et autorisations.](./assets/microsoft-work-iq/org-tools.png){zoomable="yes"}

1. Vérifiez les détails enregistrés du connecteur **[!UICONTROL workiq]**. Si vous le souhaitez, sélectionnez **[!UICONTROL Test]** pour vérifier que Coworker peut découvrir les outils de connecteur. Pour modifier les outils après l’enregistrement, voir [Modifier la sélection d’outils](#change-tool-selection).

   | Paramètre | Description |
   | --- | --- |
   | **[!UICONTROL Source]** | Le serveur MCP [!DNL Work IQ], `https://workiq.svc.cloud.microsoft/mcp`. |
   | **[!UICONTROL Authentification]** | La méthode d’authentification, `workiq_login`. |
   | **[!UICONTROL Délai d’expiration de l’outil]** | Temporisation de l’outil pour le connecteur. |
   | **[!UICONTROL Connexion]** | Votre propre statut de connexion. |

   ![Détails du connecteur workiq enregistrés affichant la source, la méthode d’authentification, le délai d’expiration de l’outil, le statut Non connecté et les outils sélectionnés.](./assets/microsoft-work-iq/org-details.png){width="500" zoomable="yes"}

Le statut **[!UICONTROL Non connecté]** sur les détails du connecteur fait référence à votre propre connexion et non à l’organisation. Pour utiliser le connecteur vous-même, sélectionnez **[!UICONTROL Se connecter]** et suivez les étapes décrites dans [Se connecter en tant que membre](#sign-in-as-a-member).

Pour arrêter de proposer le connecteur à votre organisation, sélectionnez **[!UICONTROL Supprimer]** sur la page des détails du connecteur.

### Outils disponibles {#available-tools}

Le connecteur [!DNL Microsoft Work IQ] fournit les outils suivants :

| Outil | Description |
| --- | --- |
| `search_paths` | Identifiez les fonctionnalités de [!DNL Microsoft 365] disponibles et comment y remédier. |
| `get_schema` | Consultez les champs qu’une demande prise en charge accepte ou renvoie. |
| `list_agents` | Affichez les agents [!DNL Microsoft 365 Copilot] disponibles pour votre compte, sans les exécuter. |
| `fetch` | Lisez [!DNL Microsoft 365] éléments auxquels votre compte peut accéder, tels que des messages, des événements, des fichiers et des personnes. Ne modifie pas les données. |
| `call_function` | Calculer les résultats à partir des données auxquelles votre compte peut accéder, telles qu’une vue de calendrier ou des modifications récentes. Ne modifie pas les données. |
| `retrieve` | Effectuez des recherches dans vos e-mails, fichiers, réunions, messages [!DNL Microsoft Teams], personnes et sources connectées, avec des liens vers chaque source. |
| `fetch_blob` | Téléchargez un fichier, tel qu’un document, une image ou une photo de profil, jusqu’à 4 Mo. Ne modifie pas les données. |
| `ask` | Demandez à [!DNL Microsoft 365 Copilot] ou à l’un de ses agents des informations sur vos e-mails, réunions, fichiers et autres données [!DNL Microsoft 365]. |
| `delete_entity` | Supprimez un élément de [!DNL Microsoft 365], tel qu’un message ou un événement. Modifie les données. |
| `do_action` | Exécutez une action [!DNL Microsoft 365], telle que l’envoi d’un courrier ou le déplacement d’un élément. Modifie les données. |
| `create_entity` | Créez un élément de [!DNL Microsoft 365], tel qu’un événement ou un brouillon de message. Modifie les données. |
| `update_entity` | Modifier un élément de [!DNL Microsoft 365] existant, tel qu’un événement ou un contact. Modifie les données. |

>[!IMPORTANT]
>
>Les outils `delete_entity`, `do_action`, `create_entity` et `update_entity` modifient les données dans [!DNL Microsoft 365]. Examinez attentivement ces outils et sélectionnez uniquement ceux que votre organisation prévoit que les membres utilisent.

Les outils que le serveur ajoute ultérieurement restent désactivés jusqu’à ce que vous les sélectionniez.

### Modification de la sélection d’outils {#change-tool-selection}

Pour modifier les outils disponibles pour les membres après l’enregistrement, utilisez la section **[!UICONTROL Outils]** de la page des détails du connecteur.

1. Sélectionnez ou effacez des outils individuels, ou utilisez **[!UICONTROL Tout sélectionner]** ou **[!UICONTROL Effacer]**.

1. Sélectionnez **[!UICONTROL Enregistrer la sélection d’outils]**.

>[!CAUTION]
>
>Sélectionner **[!UICONTROL Afficher chaque outil]** efface la sélection en cours. Les membres peuvent ensuite utiliser chaque outil que la politique n’exclut pas, jusqu’à ce que vous enregistriez une nouvelle sélection. Ne sélectionnez pas **[!UICONTROL Afficher chaque outil]** uniquement pour afficher la liste des outils.

## Se connecter en tant que membre {#sign-in-as-a-member}

Une fois qu’un administrateur a configuré le connecteur, chaque membre se connecte avec son propre compte professionnel [!DNL Microsoft]. Vous n’avez pas besoin du secret client de l’application pour vous connecter.

1. Ouvrez **[!UICONTROL Personnalisations]**, sélectionnez **[!UICONTROL Utilisateur]**, puis **[!UICONTROL Connecteurs externes]**.

1. Sur la carte **[!UICONTROL Microsoft Work IQ]**, sélectionnez **[!UICONTROL Se connecter]**.

   Si la carte indique **[!UICONTROL Non configuré]** ou si le connecteur n’est pas disponible, demandez à votre administrateur de [configurer le connecteur](#configure-organization).

1. Sur l’écran [!DNL Microsoft] **[!UICONTROL Choisir un compte]**, sélectionnez le compte professionnel de votre organisation ou sélectionnez **[!UICONTROL Utiliser un autre compte]**.

   Votre navigateur peut mémoriser plusieurs comptes, y compris des comptes d’autres clients. Le compte déjà connecté n’est pas toujours le bon. Choisissez le compte avec l’accès [!DNL Microsoft 365] dont vous avez besoin.

   ![Microsoft Sélectionnez un écran de compte répertoriant deux comptes aux noms et adresses électroniques flous, ainsi que l’option Utiliser un autre compte &#x200B;](./assets/microsoft-work-iq/member-pick-account.png){width="400" zoomable="yes"}.

1. Suivez les étapes de connexion à votre compte, telles qu’un mot de passe, l’authentification unique (SSO), la connexion sans mot de passe, l’authentification multifacteur (MFA) ou d’autres vérifications.

   Saisissez vos informations d’identification [!DNL Microsoft] uniquement dans le flux de connexion approuvé par votre organisation. Ne les saisissez jamais dans les champs d’application OAuth du connecteur.

   ![Microsoft Saisissez l&#39;écran du mot de passe d&#39;un compte professionnel avec une adresse e-mail floue et le bouton Se connecter.](./assets/microsoft-work-iq/member-password.png){width="400" zoomable="yes"}

1. Si [!DNL Microsoft] demande le consentement, vérifiez la demande.

   >[!IMPORTANT]
   >
   >Continuez uniquement si vous reconnaissez l’application et que votre organisation approuve l’accès demandé.

1. Une fois que [!DNL Microsoft] vous êtes revenu à Coworker, ouvrez les détails du connecteur **[!UICONTROL workiq]**. Vérifiez que le connecteur affiche **[!UICONTROL Connecté]** et **[!UICONTROL Connecté]**.

   ![détails du connecteur workiq affichant un statut Connecté , une connexion signée et les outils activés par l’administrateur.](./assets/microsoft-work-iq/member-connected.png){width="700" zoomable="yes"}

1. Consultez **[!UICONTROL Outils activés par votre administrateur]** pour afficher les outils que vous pouvez utiliser.

À partir des détails du connecteur, vous pouvez également effectuer les opérations suivantes :

* **[!UICONTROL Test] :** vérifier que Coworker peut découvrir les outils du connecteur.
* **[!UICONTROL Déconnexion] :** déconnectez votre compte [!DNL Microsoft] du connecteur.

Les détails du connecteur affichent également le paramètre **[!UICONTROL Délai d’expiration de l’outil]** et une commande **[!UICONTROL Actualiser]**.

Un statut **[!UICONTROL Connecté]** ne confirme pas que vous pouvez accéder à chaque ressource [!DNL Microsoft 365] ou que chaque outil s’exécute correctement. Pour confirmer votre accès, [vérifiez votre accès à Microsoft 365](#check-access).

## Vérifier l’accès à Microsoft 365 {#check-access}

Pour confirmer que le connecteur peut lire vos données, démarrez une conversation et saisissez une invite en lecture seule.

Exemple d’invite :

* « Retrouvez mes réunions de demain et insérez des liens vers les sources. Ne créez, ne mettez pas à jour, n’envoyez ou ne supprimez rien. »

Pour que cette invite fonctionne, votre administrateur doit activer un outil capable de lire les données du calendrier, et votre compte doit avoir accès aux données.

## Résolution des problèmes d’accès {#troubleshoot-access}

Si la connexion ou l’accès échoue, vérifiez les points suivants auprès de votre administrateur :

| Zone | Éléments à vérifier |
| --- | --- |
| compte [!DNL Microsoft] | Vous vous êtes connecté avec le compte professionnel approprié pour le client prévu. |
| [!DNL Work IQ] la disponibilité | [!DNL Work IQ] est activé pour votre client [!DNL Microsoft]. |
| URI de redirection | L’application [!DNL Microsoft Entra] dispose de l’URL de redirection exacte de la boîte de dialogue enregistrée en tant qu’URI de redirection web. |
| Consentement administrateur | Un administrateur a accordé le consentement administrateur pour l’autorisation `WorkIQAgent.Ask` déléguée. |
| Secret client | Le secret client n’a pas expiré et le connecteur utilise la valeur secrète, et non l’ID secret. |
| Secrets enregistrés | Les deux secrets d’organisation sélectionnés appartiennent à l’application [!DNL Microsoft Entra] prévue. |
| Sélection d’outil | Si un seul outil échoue, votre administrateur l’a activé. |
| [!DNL Microsoft 365] des autorisations | Votre compte a l’autorisation d’accéder aux données demandées. |
