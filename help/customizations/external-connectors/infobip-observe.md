---
title: Connecteur Externe Infobip Observe
description: Découvrez comment configurer le connecteur externe Infobip Observe dans CX Enterprise Coworker pour votre organisation et connectez-vous avec Infobip pour utiliser les outils d’observation.
role: Admin, User
level: Beginner
badgeBeta: label="Beta" type="Informative" tooltip="Ce connecteur est en version bêta."
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
hide: true
source-git-commit: 382a5f6fd629b8b10468c0cfe4d41f050a7f3725
workflow-type: tm+mt
source-wordcount: '1458'
ht-degree: 1%
---

# Connecteur externe Infobip Observe {#infobip-observe}

Utilisez le connecteur externe [!DNL Infobip Observe] pour passer en revue votre trafic et vos coûts [!DNL Infobip] dans Adobe CX Enterprise Coworker. Une fois que vous avez configuré le connecteur, interrogez votre collègue sur les mesures de trafic, l’utilisation de la facturation, les journaux de messages, ainsi que le statut et les codes d’erreur. Le connecteur est le serveur MCP (Model Context Protocol) [!DNL Observe] hébergé par [!DNL Infobip].

>[!AVAILABILITY]
>
>Le connecteur externe [!DNL Infobip Observe] est en version bêta. La documentation et les fonctionnalités peuvent changer.

## Configuration du connecteur {#connector-configuration}

Le processus de configuration du connecteur comprend deux parties distinctes :

* **Configuration de l’organisation :** un administrateur configure le connecteur une seule fois pour l’ensemble de l’organisation et approuve les outils que les membres peuvent utiliser.
* **Connexion du membre :** Chaque membre se connecte avec son propre compte [!DNL Infobip]. Les membres ne peuvent accéder qu&#39;aux données que leur compte [!DNL Infobip] est autorisé à utiliser.

Le connecteur n’a pas de connexion d’organisation partagée. Chaque membre qui utilise le connecteur se connecte séparément. L’enregistrement de la configuration de l’organisation ne connecte aucun membre et n’accorde aucune autorisation [!DNL Infobip] supplémentaire.

## Conditions préalables {#prerequisites}

Le connecteur fonctionne uniquement avec le serveur MCP [!DNL Infobip] [!DNL Observe]. Il ne se connecte pas aux serveurs MCP de messagerie, d&#39;approvisionnement ou de gestion de compte [!DNL Infobip].

Avant de commencer, vérifiez que vous disposez des éléments suivants :

* **Accès des collaborateurs :** compte autorisé à gérer les connecteurs d&#39;organisation, dans une organisation où le connecteur [!DNL Infobip Observe] est disponible.
* Compte **[!DNL Infobip]:** compte [!DNL Infobip] approuvé avec accès à [!DNL Observe] dans le centre de données prévu. [!DNL Infobip] offre [!DNL Observe] MCP en tant que fonctionnalité d’accès anticipé. Confirmez vos droits et la pertinence de votre compte avec [!DNL Infobip].
* **Identités des membres :** membres disposant de leurs propres comptes [!DNL Infobip] et de l’autorisation d’accéder aux données prévues.
* **Une étendue approuvée pour les tests :** Une étendue de test approuvée et des données non sensibles avant que vous ne demandiez des journaux de facturation, de trafic ou de messages.

Pour tester le connecteur, vous pouvez vous inscrire à un compte d’évaluation [!DNL Infobip] gratuit. Un compte d’évaluation ne garantit pas l’isolation des données ni un coût nul. Pour plus d&#39;informations, consultez [Utilisation des serveurs MCP Infobip](https://www.infobip.com/docs/mcp/using-mcp){target="_blank"} et [Observation de MCP](https://www.infobip.com/docs/mcp/observe-mcp){target="_blank"} dans la documentation [!DNL Infobip].

>[!IMPORTANT]
>
>Ne partagez jamais de mots de passe, clés API, jetons, codes d’autorisation ou URL de consentement et de rappel dans les captures d’écran, les conversations ou les tickets d’assistance.

## Modèle de connexion {#connection-model}

Coworker applique automatiquement les paramètres suivants. Vous ne créez pas d’application OAuth et ne saisissez pas d’informations d’identification d’application.

| Paramètre | Valeur |
| --- | --- |
| URL du serveur | `https://mcp.infobip.com/observe` |
| Transport | HTTP diffusable en continu |
| Découverte du serveur d’autorisation | `https://mcp.infobip.com/observe/.well-known/oauth-authorization-server` |
| Se connecter | Chaque membre se connecte avec OAuth, à l’aide de l’enregistrement client dynamique |
| Configuration OAuth | Découverte automatique. Les administrateurs ne saisissent pas d’ID client, de secret client, de portées ou de points d’entrée OAuth. |
| Sélection d’outil | Quatre outils approuvés. Les administrateurs peuvent limiter la sélection. |

[!DNL Infobip] la découverte et le consentement de chaque membre déterminent l&#39;accès que Coworker reçoit. [!DNL Infobip] documente les portées `billing:usage:view`, `metrics:manage`, `messages-api:manage` et `error-codes:read` pour le MCP [!DNL Observe]. Vérifiez l’accès demandé sur l’écran de consentement avant d’approuver.

[!DNL Infobip] prend également en charge l’authentification par clé API pour [!DNL Observe] MCP dans d’autres clients MCP. Coworker n’utilise pas de clés API pour ce connecteur. Les membres se connectent avec OAuth uniquement.

## Configuration du connecteur pour votre organisation {#configure-organization}

Les administrateurs rendent le connecteur [!DNL Infobip Observe] disponible pour tous les membres de l’organisation. Les modifications apportées à la page d’organisation s’appliquent à tous les utilisateurs de votre organisation. Les membres ne peuvent pas configurer la connexion d’organisation.

1. Ouvrez **[!UICONTROL Personnalisations]**, sélectionnez **[!UICONTROL Org]**, puis **[!UICONTROL Connecteurs externes]**.

1. Recherchez **[!UICONTROL Infobip Observe]**, puis sélectionnez **[!UICONTROL Configurer]**.

1. Dans la boîte de dialogue **[!UICONTROL Connecter Infobip Observe]**, passez en revue l&#39;**[!UICONTROL URL du serveur]** fixe, `https://mcp.infobip.com/observe`.

   Vous n’avez pas besoin de saisir d’ID client OAuth, de secret client ou de portées.

1. Sous **[!UICONTROL Outils disponibles pour les utilisateurs]**, passez en revue les quatre outils initialement sélectionnés. Supprimez tout outil que les membres de votre organisation ne doivent pas utiliser. Au moins un outil doit rester.

   Pour plus d&#39;informations, voir [Outils disponibles](#available-tools).

   ![Boîte de dialogue Connect Infobip Observe affichant l&#39;URL du serveur, les quatre outils disponibles pour les utilisateurs, l&#39;avis d&#39;accès et d&#39;autorisations, ainsi que les paramètres d&#39;authentification OAuth, de connexion HTTP et de temporisation de l&#39;outil de 60 secondes.](./assets/infobip-observe/org-configure.png){width="500" zoomable="yes"}

1. Sélectionnez **[!UICONTROL Enregistrer la connexion]**. Ouvrez à nouveau la configuration pour vérifier que votre sélection d’outils persiste.

L&#39;enregistrement ne vous connecte pas, vous ou un membre, à [!DNL Infobip]. Pour vérifier la connexion vous-même, connectez-vous comme décrit dans [Connexion en tant que membre](#sign-in-as-a-member).

Pour rendre à nouveau les quatre outils disponibles après en avoir supprimé un, sélectionnez **[!UICONTROL Restaurer tous les outils]**. Cette option restaure uniquement les quatre outils approuvés. Coworker n&#39;active pas les outils que [!DNL Infobip] ajoute ultérieurement. Vous ne pouvez pas enregistrer la configuration si aucun outil n’est sélectionné.

### Outils disponibles {#available-tools}

Le connecteur [!DNL Infobip Observe] fournit les outils suivants. [!DNL Infobip] pouvant modifier les limites de chaque outil, vérifiez la documentation [!DNL Infobip] avant de vous y fier.

| Outil | Rôle | Limites |
| --- | --- | --- |
| `get_traffic_performance_metrics` | Trafic agrégé, diffusion et mesures d’engagement. | Jusqu’à 366 jours de données. Les fenêtres horaires couvrent jusqu’à 14 jours et les fenêtres quotidiennes jusqu’à 93 jours. Renvoie les données du compte connecté par défaut. Incluez explicitement les sous-comptes. |
| `get_billing_usage_costs` | Utilisation et coûts alignés sur les factures. | Les deux mois civils en cours et précédents. Inclut la hiérarchie de compte complète par défaut. Les données d’un mois sont provisoires jusqu’au cinquième jour du mois suivant. |
| `get_message_logs` | Logs pour les messages individuels. | Les dernières 48 heures. Les journaux peuvent inclure les identifiants des destinataires, des informations personnelles et le contenu des messages. |
| `look_up_status_and_error_codes` | Descriptions des statuts connus et des noms des codes d’erreur. | Jusqu’à 50 noms par requête. [!DNL Infobip] peut omettre des noms inconnus dans les résultats. |

Les résultats sont limités à un centre de données [!DNL Infobip]. La sélection d&#39;outils contrôle les outils que les membres peuvent utiliser dans Coworker. Il ne limite pas l’accès [!DNL Infobip] que les membres accordent lors de la connexion, la hiérarchie de compte ou les autorisations que [!DNL Infobip] applique.

>[!IMPORTANT]
>
>Les logs de messages peuvent contenir des données personnelles, telles que les identifiants des destinataires et le contenu des messages. Les informations de facturation sont sensibles et couvrent par défaut l’ensemble de la hiérarchie des comptes. Activez ces outils uniquement lorsque votre organisation approuve leur utilisation. Utilisez des filtres de compte explicites et approuvés ainsi que des requêtes limitées.

## Se connecter en tant que membre {#sign-in-as-a-member}

Une fois qu’un administrateur a configuré le connecteur, chaque membre se connecte avec son propre compte [!DNL Infobip]. Votre connexion n&#39;appartient qu&#39;à vous. Les autres membres n’utilisent pas vos informations d’identification.

1. Ouvrez **[!UICONTROL Personnalisations]**, sélectionnez **[!UICONTROL Utilisateur]**, puis **[!UICONTROL Connecteurs externes]**. Trouvez **[!UICONTROL Infobip Observe]**.

   Si la carte indique **[!UICONTROL Non configuré]** et **[!UICONTROL Pas encore disponible. Votre administrateur doit configurer ceci.]**, demandez à votre administrateur de [configurer le connecteur](#configure-organization).

1. Sélectionnez **[!UICONTROL Se connecter]** et utiliser le compte [!DNL Infobip] prévu. Effectuez l’authentification unique (SSO), l’authentification multifacteur (MFA) et envoyez-vous les invites de consentement. Avant d’approuver, examinez l’accès demandé, le compte et le centre de données.

1. Revenez à Coworker et ouvrez les détails du connecteur. Examinez les outils activés par votre administrateur.

   Les membres peuvent afficher les outils, mais ne peuvent pas modifier la configuration de l’organisation.

1. Sélectionnez **[!UICONTROL Tester la connexion]**.

   Un test réussi confirme que Coworker peut se connecter et répertorier les outils. Cela ne confirme pas que tous les outils s’exécutent correctement.

1. Si vous êtes autorisé et que votre administrateur a activé l’outil `look_up_status_and_error_codes`, exécutez la recherche dans [Vérifiez votre connexion](#check-connection).

1. Pour déconnecter votre compte [!DNL Infobip] du connecteur, sélectionnez **[!UICONTROL Se déconnecter]**.

   La déconnexion ne révoque pas nécessairement l&#39;accès que vous avez accordé dans [!DNL Infobip].

## Vérifier votre connexion {#check-connection}

Pour confirmer que le connecteur fonctionne avec votre compte, exécutez une recherche en lecture seule. Vérifiez que votre administrateur a activé l’outil `look_up_status_and_error_codes`. Démarrez ensuite une conversation et saisissez une invite.

Exemple d’invite :

* « À l’aide d’Infobip Observe, recherchez le code d’état NO_ERROR et décrivez ce qu’il signifie. N’interrogez pas les mesures de trafic, la facturation ou les journaux de messages. »

Confirmez que le résultat comprend une description de `NO_ERROR` sans message d&#39;erreur. Une recherche réussie ne confirme pas que les outils de journalisation du trafic, de la facturation ou des messages fonctionnent pour votre compte. N’interrogez pas les journaux de facturation ou de messages uniquement pour tester la connexion.

## Résolution des problèmes d’accès {#troubleshoot-access}

Si vous ne pouvez pas accéder à vos données [!DNL Infobip], vérifiez les points suivants auprès de votre administrateur :

| Problème | Éléments à vérifier |
| --- | --- |
| Le connecteur **[!UICONTROL Infobip Observe]** est manquant | Vérifiez que le connecteur est disponible pour votre organisation et que vous êtes autorisé à gérer les connecteurs d’organisation. Contactez votre représentant Adobe si nécessaire. |
| Échec du consentement ou de la connexion | Vérifiez le compte [!DNL Infobip] que vous avez utilisé, vos droits [!DNL Observe] et le centre de données. Ne partagez pas l’URL de consentement, l’URL de rappel ou les codes d’autorisation lorsque vous demandez de l’aide. |
| La connexion réussit, mais un outil échoue | Vérifiez les autorisations [!DNL Infobip] en vigueur, le compte et le centre de données avec lesquels vous vous êtes connecté, ainsi que l’erreur renvoyée par [!DNL Infobip]. Une connexion réussie ne confirme pas qu’un outil s’exécute correctement. |
| Un outil n’est pas disponible | Vérifiez les outils activés par votre administrateur. Coworker n’active pas automatiquement les nouveaux outils [!DNL Infobip]. |
| Vous ne pouvez pas enregistrer la configuration | Conservez au moins un outil sélectionné. Pour arrêter de proposer le connecteur, supprimez-le à la place. |
| Les résultats de facturation incluent des comptes inattendus | Par défaut, les résultats de facturation incluent la hiérarchie complète des comptes. Arrêtez puis passez en revue les filtres et autorisations de compte approuvés. |
| Les logs de messages affichent les données sensibles | Arrêtez la requête et limitez les requêtes ultérieures aux données approuvées et non sensibles. Ne collez pas les journaux bruts dans les conversations ou les tickets d’assistance. |
| La recherche du code d’état réussit, mais une autre requête échoue | Examinez la requête ayant échoué séparément. Une recherche réussie ne confirme pas que chaque outil ou compte fonctionne. |
