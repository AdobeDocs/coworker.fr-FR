---
title: Connecteur externe de stockage dans le cloud Google
description: Découvrez comment configurer le connecteur externe Google Cloud Storage dans CX Enterprise Coworker avec votre application OAuth Google et connectez-vous pour lire les données de compartiment dans la conversation.
role: Admin, User
level: Beginner
badgeBeta: label="Beta" type="Informative" tooltip="Ce connecteur est en version bêta."
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
hide: true
source-git-commit: 70782269f48e3ff87ca95a1341ee74b02da1d7f4
workflow-type: tm+mt
source-wordcount: '2408'
ht-degree: 1%
---

# Connecteur externe Google Cloud Storage {#google-cloud-storage}

Utilisez le connecteur externe [!DNL Google Cloud Storage] pour lire vos données [!DNL Cloud Storage] dans Adobe CX Enterprise Coworker. Après avoir configuré le connecteur, demandez à Coworker de répertorier les compartiments dans un projet connu, de répertorier les objets par préfixe, d’inspecter les métadonnées des compartiments et des objets et de lire les fichiers approuvés. Le connecteur est un serveur MCP (Model Context Protocol) hébergé par [!DNL Google].

>[!AVAILABILITY]
>
>Le connecteur externe [!DNL Google Cloud Storage] est en version bêta. La documentation et les fonctionnalités peuvent changer.

## Configuration du connecteur {#connector-configuration}

Le processus de configuration du connecteur comprend trois parties distinctes :

* Préparation de **[!DNL Google Cloud]:** un administrateur [!DNL Google Cloud] prépare la facturation, l’API [!DNL Cloud Storage] et les rôles de gestion des identités et des accès (IAM) pour les membres. L’administrateur prépare également un client OAuth qui appartient à votre organisation.
* **Configuration de l’organisation :** Un administrateur Collègue configure le connecteur une seule fois pour l’ensemble de l’organisation. L’administrateur enregistre l’URL de redirection de Coworker, saisit les informations d’identification du client OAuth et sélectionne les outils que les membres peuvent utiliser.
* **Connexion du membre :** Chaque membre se connecte avec son propre compte [!DNL Google]. Les membres ne peuvent accéder qu’aux compartiments et objets que l’IAM [!DNL Google Cloud] autorise pour leur compte.

Le connecteur est en lecture seule. Il demande la portée `https://www.googleapis.com/auth/devstorage.read_only` et offre uniquement des outils de lecture. Votre organisation fournit sa propre application OAuth [!DNL Google]. Il n’existe aucune application OAuth gérée par Adobe pour ce connecteur.

L&#39;enregistrement de la configuration de l&#39;organisation ne connecte aucun membre et n&#39;accorde aucune autorisation [!DNL Cloud Storage]. Chaque membre doit déjà disposer de l’accès IAM requis et doit se connecter séparément.

## Conditions préalables {#prerequisites}

Avant de commencer, vérifiez que vous disposez des éléments suivants :

* **Pour la préparation de [!DNL Google Cloud] :** un projet avec la facturation et l’API [!DNL Cloud Storage] activées, des compartiments contenant des données approuvées, des octrois IAM pour les membres et un client OAuth [!DNL Google] du type **[!UICONTROL Application web]**.
* **Pour la configuration de l&#39;organisation :** Un compte avec l&#39;autorisation de gérer les connecteurs d&#39;organisation dans Coworker. Vous avez également besoin de l’identifiant client OAuth et du secret client, ou des secrets d’organisation existants qui les contiennent.
* **Pour la connexion du membre :** un compte [!DNL Google] que l’audience de l’application OAuth et l’IAM [!DNL Google Cloud] autorisent tous deux.

Connaître l’ID du projet et les intervalles que les membres prévoient de lire. Le connecteur ne dispose d’aucun outil pour répertorier les projets. Le client OAuth peut appartenir à un projet différent des compartiments.

## Préparation de Google Cloud {#prepare-google-cloud}

Avant de configurer le connecteur dans Coworker, préparez votre projet [!DNL Google Cloud] et l’accès des membres. Une connexion réussie à [!DNL Google] n&#39;accorde pas d&#39;autorisations de stockage.

### Préparation du projet et de l’IAM {#prepare-project-iam}

Un administrateur [!DNL Google Cloud] effectue les étapes suivantes :

1. Sélectionnez ou créez un projet dans la [console Google Cloud](https://console.cloud.google.com/).
1. Liez un compte de facturation sur chaque projet qui contient des compartiments.

   L&#39;accès en lecture seule n&#39;est pas gratuit. Des frais de stockage, d’exploitation, de récupération et de réseau peuvent toujours s’appliquer. Pour plus d&#39;informations, consultez la section [Tarification du Cloud Storage](https://cloud.google.com/storage/pricing).

1. Activez l’API **[!UICONTROL Cloud Storage]** dans chaque projet approprié. Si le client OAuth appartient à un projet distinct, activez l’API dans ce projet également.
1. Accordez aux membres les rôles les moins privilégiés dans le tableau suivant. Privilégiez un groupe géré aux comptes individuels.

| Rôle | Lieu d’octroi | Rôle |
| --- | --- | --- |
| [!UICONTROL Utilisateur De L’Outil MCP] (`roles/mcp.toolUser`) | Projet utilisé pour les appels MCP | Effectuer des appels d&#39;outil MCP (`mcp.tools.call`). |
| [!UICONTROL Visionneuse de compartiment de stockage] (`roles/storage.bucketViewer`) ou un rôle personnalisé en lecture seule | Projet contenant les intervalles | Répertorier les compartiments et lire les métadonnées de compartiment (`storage.buckets.list` et `storage.buckets.get`). |
| [!UICONTROL Visionneuse D&#39;Objets De Stockage] (`roles/storage.objectViewer`) | Chaque regroupement autorisé, ou le projet si les membres peuvent lire tous ses regroupements | Répertorier les objets, lire les métadonnées des objets et lire le contenu des objets (`storage.objects.list` et `storage.objects.get`). |

N’accordez pas [!UICONTROL Administrateur de stockage] uniquement aux compartiments de liste. Les membres non autorisés à répertorier les compartiments peuvent toujours lire un compartiment autorisé lorsqu’ils indiquent son nom. Pour plus d’informations, voir [Rôles IAM pour l’espace de stockage dans le cloud](https://docs.cloud.google.com/storage/docs/access-control/iam-roles) dans la documentation [!DNL Google Cloud].

[!DNL Google] propose également une politique de refus IAM facultative qui bloque les outils MCP de lecture-écriture pour d&#39;autres clients MCP. Le connecteur Coworker utilise déjà une sélection d’outils en lecture seule et une portée en lecture seule. Examinez les effets à l’échelle du projet avec votre administrateur [!DNL Google Cloud] avant d’appliquer la politique. Pour plus d&#39;informations, voir [Empêcher l&#39;utilisation de l&#39;outil MCP lecture-écriture](https://docs.cloud.google.com/mcp/prevent-read-write-tool-use).

### Paramètres de connexion {#connection-settings}

Coworker utilise les paramètres de connexion suivants. Vous ne saisissez pas ces valeurs dans la boîte de dialogue de configuration.

| Paramètre | Valeur |
| --- | --- |
| URL du serveur MCP | `https://storage.googleapis.com/storage/mcp` (point d’entrée global uniquement) |
| Transport | HTTP diffusable en continu |
| Serveur d’autorisation | `https://accounts.google.com/` |
| Portée demandée | `https://www.googleapis.com/auth/devstorage.read_only` |

Pour plus d’informations, consultez [Utilisation du serveur MCP distant de Cloud Storage](https://docs.cloud.google.com/storage/docs/use-cloud-storage-mcp) et [Authentification aux serveurs MCP de Google](https://docs.cloud.google.com/mcp/authenticate-mcp) dans la documentation [!DNL Google Cloud].

## Configuration du connecteur pour votre organisation {#configure-organization}

Les administrateurs rendent le connecteur [!DNL Google Cloud Storage] disponible pour tous les membres de l’organisation. Les modifications apportées à la page d’organisation s’appliquent à tous les membres de votre organisation.

1. Ouvrez **[!UICONTROL Personnalisations]**, sélectionnez **[!UICONTROL Org]**, puis **[!UICONTROL Connecteurs externes]**. Sur la carte **[!UICONTROL Google Cloud Storage]**, sélectionnez **[!UICONTROL Configurer]**.

   Si le connecteur est déjà configuré, ouvrez sa configuration enregistrée à la place.

1. Dans la boîte de dialogue **[!UICONTROL Configurer Google Cloud Storage pour votre organisation]**, sous **[!UICONTROL Votre application Google]**, copiez l’ensemble de l’**[!UICONTROL URL de redirection]**.

   L’URL de redirection diffère selon l’environnement et la région. Copiez toujours la valeur exacte de la boîte de dialogue. N’utilisez pas l’URL de la page Collègue dans votre navigateur, l’URL du serveur MCP ou une URL de redirection provenant d’un autre environnement.

1. Préparez le client OAuth pour votre organisation dans la [plateforme d’authentification Google](https://console.cloud.google.com/auth/overview) :

   1. Configurez l’**[!UICONTROL identité graphique]** et l’**[!UICONTROL audience]** pour votre organisation. Pour une application externe en cours de test, ajoutez les membres prévus en tant qu’utilisateurs et utilisatrices de test. Remplissez les exigences de publication et de vérification [!DNL Google] qui s&#39;appliquent avant une utilisation plus large.
   1. Dans **[!UICONTROL Data Access]**, incluez la portée `https://www.googleapis.com/auth/devstorage.read_only`. Le connecteur n’a pas besoin de portées de lecture-écriture ou de contrôle complet.
   1. Sous **[!UICONTROL Clients]**, créez ou sélectionnez un client OAuth dont le **[!UICONTROL type d’application]** est défini sur **[!UICONTROL application web]**.
   1. Ajoutez l’URL de redirection que vous avez copiée dans **[!UICONTROL les URI de redirection autorisés]**. Si un client diffuse plusieurs environnements, enregistrez l’URL de redirection de chaque environnement.
   1. Obtenez l’**[!UICONTROL ID client]** et le **[!UICONTROL Secret client]** par le biais du processus de gestion des secrets approuvé de votre organisation.

   Les membres autorisent cette application OAuth qui appartient à votre organisation. Conservez les informations d’identification hors des conversations, des tickets et de la documentation.

1. Sous **[!UICONTROL D&#39;où proviennent les informations d&#39;identification]**, sélectionnez l&#39;une des options suivantes :

   * **[!UICONTROL Saisissez le nouveau] :** saisissez l’**[!UICONTROL ID client OAuth Google]** et le **[!UICONTROL secret client OAuth Google]**. Coworker stocke les valeurs que vous saisissez comme secrets d’organisation.
   * **[!UICONTROL Utiliser un secret existant] :** Sélectionnez les secrets d’organisation enregistrés qui contiennent l’ID client et le secret client.

   N’utilisez pas de secrets personnels pour un connecteur d’organisation.

   ![Configurez le stockage dans le cloud Google pour la boîte de dialogue de votre organisation affichant une URL de redirection expurgée, les options Entrer un nouveau et Utiliser un secret existant, les champs d&#39;identifiant client OAuth et de secret client Google, ainsi que l&#39;avis Avant que les personnes puissent se connecter.](./assets/google-cloud-storage/org-configure.png){width="500" zoomable="yes"}

1. Développer **[!UICONTROL Parcourir et lire (5 sur 5)]**. Gardez les cinq outils sélectionnés ou sélectionnez uniquement les outils dont les membres ont besoin. Vous devez sélectionner au moins un outil. Pour plus d&#39;informations, voir [Outils disponibles](#available-tools).

   Sous **[!UICONTROL Accès et autorisations]**, passez en revue les avis **[!UICONTROL Accès en lecture seule]** et **[!UICONTROL Chaque personne se connecte séparément]**. Sélectionnez ensuite **[!UICONTROL Enregistrer la connexion]**.

   ![Section Outils disponibles pour les utilisateurs avec les cinq outils de navigation et de lecture sélectionnés, suivi de l&#39;accès en lecture seule et chaque personne se connecte séparément.](./assets/google-cloud-storage/org-tools.png){width="500" zoomable="yes"}

1. Vérifiez les détails du connecteur **[!UICONTROL google-cloud-storage]** enregistrés.

   | Paramètre | Description |
   | --- | --- |
   | **[!UICONTROL Source]** | URL du serveur MCP, `https://storage.googleapis.com/storage/mcp`. |
   | **[!UICONTROL Authentification]** | La méthode d&#39;authentification, `google-cloud-storage_login`. |
   | **[!UICONTROL Connexion]** | Votre propre statut de connexion. |
   | **[!UICONTROL Outils]** | Les outils sélectionnés pour les membres, avec **[!UICONTROL Sélection de tous]** et **[!UICONTROL Effacement]** les contrôles et un nombre d&#39;outils sélectionnés. |

   ![Détails du connecteur google-cloud-storage enregistrés indiquant la source, la méthode d&#39;authentification, un élément Non connecté associé à un bouton Se connecter et cinq outils sur cinq sélectionnés.](./assets/google-cloud-storage/org-details.png){width="700" zoomable="yes"}

Le statut **[!UICONTROL Non connecté]** sur les détails du connecteur fait référence à votre propre connexion, et non à l’organisation. L’enregistrement de la configuration de l’organisation ne vous connecte pas, ni aucun membre, et ne confirme pas l’accès à un compartiment. Pour utiliser le connecteur vous-même, suivez les étapes de la section [Connexion en tant que membre](#sign-in-as-a-member).

Pour modifier les outils disponibles pour les membres ultérieurement, mettez à jour la sélection sur la page des détails du connecteur, puis sélectionnez **[!UICONTROL Enregistrer la sélection d&#39;outils]**. Les membres ne peuvent pas modifier la sélection d’outils.

Pour arrêter de proposer le connecteur à votre organisation, sélectionnez **[!UICONTROL Supprimer]** sur la page des détails du connecteur.

### Outils disponibles {#available-tools}

Le connecteur [!DNL Google Cloud Storage] fournit les outils en lecture seule suivants dans le groupe **[!UICONTROL Parcourir et lire]** :

| Outil | Description | Autorisation requise |
| --- | --- | --- |
| `list_buckets` | Répertorier les compartiments dans un projet [!DNL Google Cloud] connu, avec filtrage par préfixe et pagination. | `storage.buckets.list` sur le projet |
| `list_objects` | Répertorier les objets et les préfixes dans un compartiment autorisé. La liste n’est pas récursive par défaut. | `storage.objects.list` dans le compartiment |
| `get_bucket_metadata` | Lire la configuration du compartiment, telle que l’emplacement, la classe de stockage, la rétention et le contrôle de version. | `storage.buckets.get` |
| `get_object_metadata` | Lire la taille de l’objet, le type de contenu, la date et l’heure, la génération et les métadonnées personnalisées. | `storage.objects.get` |
| `read_object` | Lecture de texte ou contenu binaire pris en charge, jusqu’à 8 MiB par objet. | `storage.objects.get` |

Chaque appel d’outil nécessite également l’autorisation `mcp.tools.call`, généralement via le rôle [!UICONTROL Utilisateur de l’outil MCP] sur le projet approprié.

Le connecteur ne propose pas l’outil `read_text` obsolète ou les outils `write_text`, `create_bucket`, `delete_object` et `delete_bucket`. Il n’existe aucune option permettant d’activer les outils d’écriture. Les outils que [!DNL Google] ajoute ultérieurement au serveur ne sont pas automatiquement disponibles, même lorsque vous sélectionnez les cinq outils.

## Se connecter en tant que membre {#sign-in-as-a-member}

Une fois qu’un administrateur a configuré le connecteur, chaque membre se connecte avec son propre compte [!DNL Google]. Vous n’avez pas besoin du secret client OAuth pour vous connecter.

1. Ouvrez **[!UICONTROL Personnalisations]**, sélectionnez **[!UICONTROL Utilisateur]**, puis **[!UICONTROL Connecteurs externes]**. Sur la vignette **[!UICONTROL Google Cloud Storage]**, sélectionnez **[!UICONTROL Se connecter]**.

   Avant de vous connecter, la carte indique **[!UICONTROL Non connecté]**. Si la carte indique **[!UICONTROL Non configuré]**, demandez à votre administrateur de [configurer le connecteur](#configure-organization).

1. Sur l’écran [!DNL Google] **[!UICONTROL Choisir un compte]**, sélectionnez le compte disposant de l’accès IAM requis ou sélectionnez **[!UICONTROL Utiliser un autre compte]**. Effectuez toutes les étapes de connexion requises par votre organisation, telles que l’authentification unique (SSO) ou l’authentification multifacteur (MFA).

   Ce compte peut différer du compte que vous utilisez pour vos collègues.

   ![Google Choisissez un écran de compte avec les comptes supprimés et l’option Utiliser un autre compte .](./assets/google-cloud-storage/member-choose-account.png){width="500" zoomable="yes"}

1. Si [!DNL Google] affiche **[!UICONTROL Google n&#39;a pas vérifié cette application]**, confirmez l&#39;application et son propriétaire auprès de votre administrateur.

   Si votre organisation approuve l’utilisation de cette application, sélectionnez **[!UICONTROL Continuer]**. Sinon, sélectionnez **[!UICONTROL Retour à la sécurité]** et demandez au propriétaire de l&#39;application de résoudre les exigences en matière d&#39;audience, de publication ou de vérification.

   ![Écran Google indiquant que Google n&#39;a pas vérifié cette application, car elle est en cours de test, avec les options Continuer et Retour à la sécurité.](./assets/google-cloud-storage/member-unverified-app.png){width="500" zoomable="yes"}

   Vérifiez le nom de l&#39;application et l&#39;accès demandé dans l&#39;écran de consentement, puis sélectionnez **[!UICONTROL Continuer]**. Le connecteur demande **[!UICONTROL Afficher vos données dans Google Cloud Storage]**, qui correspond à la portée en lecture seule.

   Dans les captures d’écran, l’application est nommée adobe.io. L’application de votre entreprise affiche son propre nom. Ce nom ne signifie pas qu’Adobe fournit l’application OAuth.

   >[!IMPORTANT]
   >
   >Continuez uniquement si vous reconnaissez l’application et que votre organisation approuve l’accès demandé.

   ![Écran de consentement de Google sur lequel un exemple d’application nommé adobe.io demande l’accès pour afficher vos données dans Google Cloud Storage, avec un compte supprimé et les boutons Annuler et Continuer.](./assets/google-cloud-storage/member-consent.png){width="500" zoomable="yes"}

1. Revenez à votre collègue et confirmez que la connexion est terminée. Consultez **[!UICONTROL Outils activés par votre administrateur]** dans les détails du connecteur. Vous ne pouvez utiliser que les outils activés par votre administrateur.

Si votre connexion se termine ou si votre session expire, reconnectez-vous. Lorsqu’un administrateur se connecte, les autres membres ne sont pas connectés.

## Vérifier l’accès au compartiment {#check-bucket-access}

Une connexion réussie ou une liste d’outils ne confirme pas que vous pouvez accéder à un compartiment spécifique. [!DNL Google] ne nécessite pas d&#39;authentification pour répertorier les outils du serveur. Pour confirmer votre accès, démarrez une nouvelle conversation et saisissez une invite en lecture seule. Remplacez les espaces réservés par les ressources approuvées.

Exemples d’invites :

* « Répertorier les intervalles dans le projet `YOUR_PROJECT_ID`. »
* « Répertoriez jusqu’à 25 objets sous `reports/` dans le compartiment `YOUR_BUCKET`. Vérifiez la taille et le type de contenu de `reports/example.txt`, puis lisez ses 4 096 premiers octets et résumez-les. »

Vérifiez que le résultat inclut le compartiment ou l’objet attendu. Pour répertorier des objets dans des préfixes imbriqués, demandez explicitement une liste récursive. Vérifiez les métadonnées de l’objet avant de lire un objet.

## Limites et gestion des données {#limits-data-handling}

Gardez à l’esprit les limites et considérations relatives à la gestion des données suivantes lorsque vous utilisez le connecteur :

* **ID de projet :** Indiquez un ID de projet dans votre demande. Le connecteur ne peut pas répertorier les projets.
* **Préfixes :** les préfixes d’objet sont des noms littéraux, et non de vrais dossiers. Les listes ne sont pas récursives par défaut et renvoient les résultats dans les pages.
* **Taille de page :** Une page de liste peut contenir jusqu&#39;à 1 000 éléments. Utilisez une page de petite taille, par exemple 25 à 100, et un préfixe étroit.
* **Taille de l&#39;objet :** La taille d&#39;objet maximale pour une lecture est de 8 MiB. La lecture d’une partie seulement d’un objet plus grand ne contourne pas cette limite. La prise en charge des fichiers binaires dépend du modèle et du client.
* **Coûts et quotas :** Des frais de stockage, de requête, de récupération et de réseau peuvent s&#39;appliquer. [!DNL Google] applique également des quotas au serveur MCP. Pour plus d&#39;informations, voir [Quotas MCP Cloud Storage](https://docs.cloud.google.com/storage/quotas#gcs-mcp).
* **Gestion des données :** le contenu, les noms et les métadonnées personnalisées de l&#39;objet entrent dans votre conversation avec un collègue. Utilisez uniquement des données approuvées.
* **Les journaux d&#39;audit :** [!DNL Cloud Storage] lectures apparaissent dans [!DNL Cloud Audit Logs] uniquement lorsque les journaux d&#39;accès aux données applicables sont activés.

Le connecteur ne peut pas charger, remplacer, créer ou supprimer des fichiers ou des compartiments. Il ne peut pas non plus enregistrer les résumés dans [!DNL Cloud Storage].

## Résolution des problèmes d’accès {#troubleshoot-access}

Si la connexion ou l’accès échoue, vérifiez les points suivants auprès de votre administrateur :

| Problème | Éléments à vérifier |
| --- | --- |
| La carte indique **[!UICONTROL Non configuré]** | Enregistrez la connexion d’organisation pour l’organisation active. |
| `redirect_uri_mismatch` | Enregistrez l’URL de **[!UICONTROL redirection]** exacte à partir de la boîte de dialogue Collègue sur le client OAuth **[!UICONTROL Application web]**. |
| `invalid_client` | Vérifiez le type de client, l’ID client et le secret client, ainsi que les secrets d’organisation sélectionnés. |
| `access_denied` ou un avertissement d&#39;application non vérifié | Vérifiez l&#39;audience de l&#39;application, testez l&#39;éligibilité de l&#39;utilisateur et le statut de vérification auprès du propriétaire de l&#39;application. N’approuvez pas une application inconnue. |
| HTTP 401, ou votre session s’est terminée | Reconnectez-vous. |
| `mcp.tools.call` est refusé | Vérifiez le rôle [!UICONTROL Utilisateur de l’outil MCP] et toutes les politiques de refus IAM qui s’appliquent. |
| La liste des compartiments est refusée, mais un compartiment connu est lisible | Vérifiez l&#39;autorisation `storage.buckets.list` pour le projet. Les autorisations d’objet seules ne vous permettent pas de répertorier les compartiments dans un projet. |
| Les métadonnées du compartiment sont refusées | Vérifiez l&#39;autorisation `storage.buckets.get`. |
| La liste ou la lecture des objets est refusée | Vérifiez le rôle [!UICONTROL Visionneuse d’objets de stockage] sur le compartiment et le compte [!DNL Google] avec lequel vous vous êtes connecté. |
| `SERVICE_DISABLED` | Activez l’API [!DNL Cloud Storage] dans le projet nommé dans l’erreur. |
| HTTP 403 qui nécessite la facturation | Vérifiez la facturation du projet qui contient les regroupements, y compris le projet dans votre demande `list_buckets`. |
| `OutOfRange` en lecture | L’objet dépasse la limite de 8 MiB. Utilisez une alternative approuvée en dehors de ce connecteur. |
| Il manque un outil | Cochez la sélection d’outils enregistrée par votre administrateur. Les outils obsolètes et d’écriture ne sont pas disponibles. |
| Échec d’une demande de chargement, de remplacement, de création ou de suppression | Le connecteur est en lecture seule et ne prend pas en charge ces actions. |
