---
description: Découvrez les améliorations et correctifs apportés aux fonctionnalités dans les notes de mise à jour des campagnes Adobe CX Enterprise Coworker .
title: Notes de mise à jour des campagnes CX Enterprise Coworker
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
feature_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: ee66c1cc95ef1dd8c5e45c1fcb699547e63b9c8a
workflow-type: tm+mt
source-wordcount: '3590'
ht-degree: 0%
---
# Notes de mise à jour des campagnes Adobe CX Enterprise Coworker {#release-notes}

Les versions des campagnes Coworker fonctionnent sur un modèle de diffusion continu qui permet une approche plus évolutive et plus progressive du déploiement des fonctionnalités.

## Septembre 2026 {#sep-2026}

**Date de publication : 17 septembre 2026**

* Connecter un espace de travail des briques de données hébergé sur Azure, GCP ou un domaine personnalisé
* Les campagnes ne peuvent plus être lancées tant que leur workflow n’est pas entièrement configuré
* Les modèles de campagne ont été actualisés avec du contenu mis à jour
* Choisir un connecteur directement lors du chargement de votre liste de contacts au format CSV
* Correction d’un crash qui pouvait se produire après un défilement d’une longue liste d’inscriptions à des essais
* Correction d’un problème en raison duquel le chargement d’un fichier CSV d’audience avec des en-têtes vides ou dupliqués pouvait bloquer la page
* Correction d’un texte d’espace réservé dans une invite de campagne qui s’affichait vide après résolution
* Correction d’un blocage de la page Compétences dû à un gradient de couleur manquant
* Correction du blocage d&#39;une conversation qui répétait la même question après que vous y ayez déjà répondu
* Les réponses de conversation n’affichent plus de préfixe d’ID errant devant votre réponse sélectionnée
* La discussion suggère désormais des réponses rapides à l’étape suivante, que vous pouvez appuyer pour remplir la zone de composition
* Les modèles de campagne s’ouvrent désormais dans une vue intégrée rationalisée à la page, au lieu d’une boîte de dialogue distincte
* La barre de progression étendue de la conversation défile désormais en interne au lieu de pousser votre conversation hors de vue
* Les paramètres de Campaign reflètent désormais plus précisément les derniers détails du panorama
* La boîte de dialogue du plan de mise à niveau adopte désormais une apparence plus cohérente
* Suppression d&#39;un indicateur de statut redondant de l&#39;en-tête du plan de campagne pour un aspect plus épuré
* Les modifications rapides d’e-mails sont désormais enregistrées ensemble en tant qu’entrée historique de version unique au lieu d’en nombreuses
* Correction de titres de kits de marque qui disparaissaient parfois lors de la génération d’un brouillon
* Modification d’une image avec Adobe Express directement depuis la barre d’outils image
* Les données d’audience de base de l’agent restent désormais synchronisées sur le tableau de campagne sans actualisation manuelle
* Les logos des marques sur le tableau de la campagne sont recadrés plus précisément pour s’adapter à leur espace
* Transfert visuel plus fluide lorsque votre plan de campagne passe sur le tableau de campagne

**Date de publication : 3 septembre 2026**

* Copiez n’importe quel message de conversation et notez les réponses de l’IA avec les pouces vers le haut ou vers le bas, directement à partir du message lui-même
* La liste des tâches du plan de campagne reste désormais épinglée au-dessus de l’entrée de conversation pendant l’exécution de votre campagne, afin que vous puissiez suivre la progression sans faire défiler l’écran
* Connecter un entrepôt de données SQL Databricks comme nouvelle source de données pour vos campagnes
* L’ancien éditeur d’e-mail basé sur les conversations a été remplacé par le nouvel éditeur de ressources d’e-mail
* L’administration des utilisateurs d’évaluation vous permet désormais d’exclure les utilisateurs d’Adobe, ce qui facilite la consultation des inscriptions à des évaluations réelles
* Correction d’un problème en raison duquel les suggestions de campagnes similaires ne se chargeaient pas
* Les messages de conversation ont désormais un espacement plus étroit et plus cohérent

**Date de publication : 1er septembre 2026**

* Les e-mails de campagne volumineux s’affichent désormais entièrement dans l’éditeur au lieu d’être coupés
* Pour plus de clarté, le bouton de lancement du tableau de campagne est désormais intitulé « Vérifier et lancer »
* La connexion à un compte Salesforce n’affiche plus de message d’erreur Marketo incorrect
* Salesforce a désormais son propre logo dans la liste des connecteurs
* Les connecteurs disponibles sont désormais répertoriés avant ceux à venir
* L’intégration affiche désormais un indicateur de progression au chargement de votre kit de marque
* Les aperçus d’audience et de source de connaissances disposent désormais d’un bouton de fermeture et peuvent s’ouvrir en plein écran
* Les cartes de plan de campagne ne sont plus bloquées et affichent « création » une fois que votre campagne commence à s’exécuter
* Le chat ne conserve plus de messages de progression temporaires (comme « Exploration... ») dans votre historique de conversation
* Les commandes de barre d’outils se verrouillent désormais correctement lorsque des suggestions d’image ou de texte d’IA sont appliquées
* Correction d’un problème qui entraînait le remplacement incorrect d’une image dans l’éditeur de ressources

## Août 2026 {#aug-2026}

**Date de publication : 26 août 2026**

* Cliquer n’importe où sur une carte de modèle de campagne ouvre désormais son aperçu, pas seulement son titre
* L’espace réservé de la barre d’invite de campagne réapparaît correctement après avoir effacé votre entrée, avec une prise en charge plus claire des lecteurs d’écran
* La suggestion « Aide pour m’inviter » remplace désormais correctement le texte existant dans la barre d’invite de la campagne
* Le téléchargement des désabonnements au format CSV reflète désormais uniquement l’exécution de la campagne que vous visionnez
* La comparaison des plans d’évaluation affiche désormais les campagnes Launch et les informations sur les campagnes en tant que fonctionnalités incluses
* Les audiences créées sans workflow complet s’affichent désormais correctement sur la carte Audience du tableau de campagne
* Les commentaires à l’état vide invitent à lire plus naturellement dans l’application

**Date de publication : 25 août 2026**

* La connexion à un onglet du navigateur synchronise désormais automatiquement les autres, ce qui corrige les erreurs de compte entre les onglets
* Cliquez sur Générer maintenant pour faire avancer votre plan de manière fiable au lieu de le générer à nouveau de temps à autre
* Les diagrammes de workflow dans la conversation affichent davantage de zones de travail afin que les commandes de zoom ne couvrent plus les étapes
* L’aspect des onglets Détails de la campagne est actualisé et plus cohérent
* L’enregistrement ou la suppression d’un domaine d’envoi dans Domaines et expéditeurs est désormais plus rapide et plus fiable

**Date de publication : 24 août 2026**

* Afficher la stratégie de campagne générée directement sur le tableau de campagne
* Remplacer votre audience directement à partir de la boîte de dialogue de validation de la campagne
* Les exports PDF et Word de Campaign incluent désormais votre vrai diagramme de workflow
* L’onglet Insights reste visible avec un état vide utile juste après le lancement
* Ajouter ou supprimer des points de contact lors de la vérification des champs de votre campagne
* La barre d’outils du panorama Campaign est plus simple et les boutons inutiles sont supprimés
* L’assistant Domaines et expéditeurs nettoie les sous-domaines et guide la première configuration avec un coachmark
* L’assistant Domaines et expéditeurs affiche les erreurs de validation de sous-domaine en ligne lorsque vous saisissez du texte
* Le call-to-action de campagne post-épreuve a été supprimé pour un flux plus épuré
* Les noms des langues chinoises s’affichent désormais correctement dans le sélecteur de langue
* Les miniatures de variantes générées par l’IA se chargent de manière fiable sans libellés en double
* Les campagnes nouvellement créées s’affichent désormais immédiatement dans votre liste de campagnes récentes sur l’Accueil
* Les informations sur toutes les campagnes incluent désormais un résumé généré par l’IA des performances de la campagne de votre organisation
* Le fait de fournir l’entrée demandée dans une conversation de workflow ne la laisse plus bloquée
* L’intégration d’évaluation ne fait plus clignoter un écran de chargement supplémentaire lors de la recherche d’un kit de marque existant
* Les exemples de sources d’audience obsolètes sont maintenant effacés automatiquement de votre workflow
* La disposition, le thème et les polices s’affichent désormais correctement dans le shell Experience Cloud unifié
* Les suggestions de campagne similaires n’affichent plus de champ de canal inutile

**Date de publication : 14 août 2026**

* Supprimer les brouillons de domaines dont vous n’avez plus besoin dans Domaines et expéditeurs
* Voir Statut de vérification DNS pour chaque enregistrement lors de la configuration du domaine
* Les détails du domaine affichent désormais l’expéditeur d’e-mail configuré
* Les valeurs d’enregistrement DNS sont parfaitement tronquées avec une info-bulle pour le texte intégral
* Formater plusieurs blocs de texte d’e-mail à la fois avec une sélection multiple
* Obtenez des suggestions de campagne similaires lors de la création d’une campagne
* Portée des informations de campagne à une seule exécution d’une campagne récurrente
* Choisissez la langue de votre choix dans le menu de profil
* Obtenir un coup de pouce lorsque les descriptions des modèles de campagne nécessitent plus de détails
* Les notes de mise à jour sont plus faciles à parcourir avec une navigation et une pagination améliorées
* Réduisez la liste des campagnes récentes de la barre latérale pour gagner de l’espace
* La vue d’inventaire de votre campagne reste maintenant telle que vous l’avez laissée
* Réorganiser les filtres d’exécution et accéder à une période à partir d’un sélecteur de calendrier
* Prévisualiser les détails de l’audience même sur les cartes d’audience en lecture seule
* Correction de flashs d’écran de flux d’évaluation de l’intégration et d’un problème de délai de connexion
* La poignée de redimensionnement du rail de conversation ne bloque plus la barre de défilement de la liste de messages
* La création du kit de marque indique désormais la véritable raison de l’échec d’un enregistrement

**Date de publication : 6 août 2026**

* Campaign Insights affiche désormais les désabonnements avec un fichier CSV téléchargeable indiquant qui s’est désabonné
* Un tableau de répartition des performances par e-mail se trouve désormais dans l’onglet Insights
* Voir votre carte des parcours de campagne directement sur l’onglet Insights
* Les étapes d’attente basées sur la durée sont désormais visibles dans la vue de workflow du parcours
* Les branches de parcours pondérées s’affichent dans la vue d’édition du workflow
* Les listes de contacts sont désormais connectées aux données actives
* Les campagnes récurrentes affichent 0 envoi immédiat au lieu de « insights en attente »
* Modifier le texte d’invite de remix directement autour des puces d’espace réservé
* Amélioration du coachmark et des puces d&#39;espace réservé plus propres dans l&#39;éditeur de remix
* Les cartes des workflows Campaign affichent désormais un état vide utile lorsque rien n’est en cours d’exécution
* Le bouton Plan de mise à niveau n’encombre plus l’en-tête des détails de la campagne
* Les cartes de workflow ont une disposition plus simple, sans nom ni description de parcours

## Juillet 2026 {#july-2026}

**Date de publication : 30 juillet 2026**

* Les informations sur toutes les campagnes correspondent désormais à la disposition des informations sur chaque campagne, ainsi qu’à un nouveau graphique de performances quotidiennes
* Arrêter une campagne active directement à partir de la page de campagne
* La duplication d’une campagne ne demande désormais qu’un nouveau nom
* Modifier des modèles d’e-mail directement à partir de la liste des modèles
* Filtrer la vue du parcours de la campagne récurrente par exécution
* Ajouter une image de marque directement à partir du tableau de campagne
* La table d’administration d’évaluation prend désormais en charge la recherche d’e-mails, la pagination et l’exportation CSV complète
* Le bouton « Surprenez-moi » répond désormais instantanément, sans délai d&#39;animation
* Suppression des paramètres de désabonnement des e-mails de la campagne pendant que nous retravaillons cette fonctionnalité
* Modifier le planning d’une campagne une fois qu’il a été défini, sans recommencer
* Ouvrez l’éditeur de style d’écriture dans le menu de débordement pour accélérer l’accès
* Appuyer sur Entrée entraîne désormais une soumission cohérente dans chaque barre d’invite de l’application

**Date de publication : 23 juillet 2026**

* Planifiez des campagnes à envoyer immédiatement, une fois par choix ou de manière récurrente.
* Gérer des listes de désabonnement à partir des listes de contacts et définir les paramètres de désabonnement dans les paramètres d’e-mail de campagne
* Créer et gérer des formulaires avec un nouvel inventaire et un nouvel éditeur de formulaires
* La configuration du connecteur fournit des conseils plus clairs lorsque les informations d’identification échouent, notamment lors de la mise à jour d’une connexion existante
* Les connexions Marketo prennent désormais en charge les URL Experience Cloud
* L’assistant Domaines et expéditeurs détecte d’autres problèmes d’enregistrement DNS avant la mise en ligne de votre domaine
* Ajouter des connecteurs directement à partir du menu Ajouter des entrées de la campagne
* Les pages d’inventaire affichent des états vides illustrés plus conviviaux lorsque rien ne s’affiche pour le moment
* Les informations sur Campaign indiquent la source de données qui alimente chaque mesure
* Les éditeurs de marque sont désormais intégrés à l’intégration pour une première configuration plus fluide
* Prévisualisez un exemple d’audience avant de vous engager dans votre campagne
* Les campagnes de collègues sont désormais intégrées à l’interface de navigation unifiée d’Experience Cloud
* Suppression de la barre d’info-bulles flottante pour un panorama de campagne plus propre
* Diverses améliorations des performances et de la fiabilité dans

**Date de publication : 14 juillet 2026**

* Déploiement des domaines et des expéditeurs, progression du workflow en direct et informations réelles sur les campagnes
* La configuration Domaines et expéditeurs est désormais entièrement disponible, et votre choix d’expéditeur est enregistré automatiquement
* Choisissez ou mettez à jour l’expéditeur d’e-mail de votre campagne directement à partir des paramètres de la campagne
* L’onglet Expéditeurs reste consultable avant même la vérification d’un domaine
* Les brouillons d’e-mails ajoutés en milieu de conversation apparaissent désormais de manière fiable sur le tableau de campagne
* L’aide et les commentaires sont combinés dans une fenêtre contextuelle rationalisée
* Démarrer une nouvelle conversation n&#39;affiche plus les messages restants de la dernière conversation
* Les conversations à plusieurs tours n’affichent plus d’invites obsolètes dans le tiroir de réponse
* Les listes numérotées des messages de conversation conservent leur ordre correct
* La configuration du connecteur HubSpot demande désormais une clé de service, correspondant à la terminologie de HubSpot
* Le tableau d’administration d’évaluation affiche un nombre d’utilisateurs et n’extrait plus la dernière ligne
* Diverses améliorations des performances et de la fiabilité dans

**Date de publication : 9 juillet 2026**

* Une bannière et une boîte de dialogue de maintenance vous avertissent désormais des temps d’arrêt planifiés
* Domaines et expéditeurs comporte un assistant de configuration guidé pour vérifier les domaines et ajouter des expéditeurs
* Les brouillons de campagne vous invitent désormais à terminer la configuration des e-mails et des canaux avant d’envoyer
* La validation du domaine et de l’expéditeur détecte plus de problèmes, y compris les cas de périphérie d’enregistrements DNS
* Le menu Profil a été déplacé vers la barre latérale pour un accès plus rapide
* Les documents Source PDF s’affichent désormais sous forme de pilule sur les détails du kit de marque
* Diverses améliorations des performances et de la fiabilité dans

**Date de publication : 26 juin 2026**

* Un nouveau tableau de bord d’informations affiche les KPI de performances de la campagne : envois, ouvertures, clics, bounces, etc
* Les campagnes affichent un badge de statut actif sur le panorama afin que vous puissiez voir les envois actifs en un coup d’œil
* Des conseils contextuels s’affichent dans le tableau de bord de la campagne pour vous guider tout au long des étapes suivantes
* L’intégration des nouveaux utilisateurs utilise vos données de marque réelles pour personnaliser l’expérience de configuration
* Le sélecteur de couleurs de marque gère les codes hexadécimaux et s’ouvre dans une fenêtre contextuelle propre
* Les paramètres UTM et la limitation des messages peuvent désormais être configurés à partir des paramètres de l’application
* Les liens d’aide permettent désormais d’accéder au contenu le plus récent directement sur Experience League
* Diverses améliorations des performances et de la fiabilité dans

**Date de publication : 24 juin 2026**

* Le lancement d’une campagne déclenche désormais une célébration des confettis
* Les campagnes affichent un badge de statut et le panorama se verrouille en lecture seule une fois lancé
* La présentation de la marque s’adapte à votre écran avec des invites vides et un meilleur affichage du logo
* La validation affiche une boîte de dialogue claire même lorsqu’un type d’erreur inattendu est renvoyé
* Le contenu d’e-mail généré utilise l’objectif de votre campagne pour des résultats plus pertinents

## Juin 2026 {#june-2026}

**Date de publication : 23 juin 2026**

* Une étape de validation vérifie que votre campagne est prête avant votre lancement
* Découvrez pourquoi chaque variante d’e-mail a été créée avec une nouvelle justification de variation
* La vue Plan de campagne affiche un rail de progression jalonné actif en tant que flux de tâches dans
* L’intégration des nouveaux utilisateurs utilise vos données de marque réelles pour personnaliser l’expérience de configuration
* Le sélecteur de couleurs de marque gère les codes hexadécimaux et s’ouvre dans une fenêtre contextuelle propre
* Les paramètres UTM et la limitation des messages peuvent désormais être configurés à partir des paramètres de l’application
* Les liens d’aide permettent désormais d’accéder au contenu le plus récent directement sur Experience League
* Diverses améliorations des performances et de la fiabilité dans

**Date de publication : 19 juin 2026**

* Vérifier la compatibilité du client de messagerie pour chaque élément avant d’envoyer
* Parcourez et restaurez les versions précédentes de votre e-mail avec un nouveau panneau d’historique des versions
* Modifiez les couleurs de la marque à l’aide d’un sélecteur hexadécimal et d’une modification sur la page de marque.
* La bibliothèque de marques charge automatiquement plus de marques au fur et à mesure que vous la faites défiler
* Le menu Profil a été déplacé vers la barre latérale pour un accès plus rapide
* Les documents Source PDF s’affichent désormais sous forme de pilule sur les détails du kit de marque
* Diverses améliorations des performances et de la fiabilité dans

**Date de publication : 12 juin 2026**

* Parcourir l’aide et les guides du produit sans quitter l’application
* Les plans de campagne s’affichent section par section au fur et à mesure de leur génération
* Reprenez les conversations de campagne là où vous vous êtes arrêté de manière plus fiable.
* Lancez des campagnes à partir d’une boîte de dialogue dédiée lorsque votre plan est prêt à l’emploi.
* L’intégration utilise un nom de produit plus clair et des conseils d’invite d’accueil
* La configuration du connecteur affiche les champs appropriés pour les connexions de clé API et de connexion
* Les réponses de conversation hors champ suggèrent les questions suivantes avec des invites en un clic
* Les exportations PDF de Campaign affichent de manière fiable les icônes, l’image de marque du produit et une étiquette de marque
* Parlez à un expert et les flux de mise à niveau chargent vos détails d’évaluation de manière plus fiable
* Les balises de style d’écriture s’étendent pour afficher le texte intégral et le lien vers votre page de marque
* Démarrer une marque à partir de l’état de bibliothèque vide avec des catégories utiles
* Reconnectez-vous sans problème à l’expiration de votre session
* L’application réside désormais sur coworker-campaigns.adobe.com avec la même expérience
* L’inscription d’essai vous dirige vers l’étape suivante appropriée après la création de votre compte
* Diverses améliorations des performances et de la fiabilité dans

**Date de publication : 11 juin 2026**

* Les pages à venir affichent un espace réservé propre sans encombrement en arrière-plan
* Les barres d’outils de l’éditeur d’e-mail s’affichent à droite dans le thème clair
* La suppression d’une image d’e-mail efface la sélection afin que la barre d’outils disparaisse
* Les importations d’audiences CSV n’affichent plus de liste en double dans la carte d’audience
* L’élément Conversations dans la barre latérale se met en surbrillance lorsque vous démarrez une nouvelle conversation
* L’en-tête de l’application affiche désormais uniquement l’objet de l’e-mail (ou « Brouillon ») lors de la modification d’un e-mail, supprimant le préfixe numérique « E-mail N : » pour un titre plus ordonné
* Le menu Profil a été déplacé vers la barre latérale pour un accès plus rapide
* Les documents Source PDF s’affichent désormais sous forme de pilule sur les détails du kit de marque
* Diverses améliorations des performances et de la fiabilité dans

**Date de publication : 10 juin 2026**

* L’application s’appelle désormais Campagnes collaborateur avec un nom mis à jour dans
* Une première visite d’intégration vous guide tout au long de la création d’une marque de démonstration
* Lancez des campagnes à partir d’une boîte de dialogue dédiée lorsque votre plan est prêt à l’emploi.
* Connectez HubSpot à l’aide d’une clé API du catalogue d’intégrations
* Parcourez les conversations avec une liste de conversations repensée et des états vides plus clairs
* Annuler et rétablir des modifications d’e-mail avec des raccourcis clavier familiers
* Réessayez d’enregistrer lorsque l’éditeur d’e-mail rencontre une erreur temporaire
* Remplacer les images d’e-mail par un dimensionnement correct et des dimensions Adobe Express
* Chargez les listes d’audience depuis un fichier CSV en utilisant une boîte de dialogue d’importation plus claire dans la conversation
* Les balises de style d’écriture s’étendent pour afficher le texte intégral et le lien vers votre page de marque
* Démarrer une marque à partir de l’état de bibliothèque vide avec des catégories utiles
* Reconnectez-vous sans problème à l’expiration de votre session
* Diverses améliorations des performances et de la fiabilité dans

**Date de publication : 9 juin 2026**

* Comparer les options d’utilisation d’essai et de mise à niveau dans une boîte de dialogue de plan repensée
* Parcourez et gérez les connecteurs de données à partir d’un catalogue dynamique dans l’application
* Renseignez les paramètres généraux et les préférences de notification dans Paramètres .
* Votre connexion reste actualisée avec une invite claire à l’expiration de votre session
* Votre adresse e-mail apparaît automatiquement lors de l’envoi d’un e-mail de test
* Confirmer avant de faire d’un kit de marque votre kit par défaut
* Les chargements de kits de marque respectent désormais une limite de taille de fichier de 100 Mo
* Modifier le nom de votre campagne directement sur le tableau de la campagne
* Prévisualiser les modèles et confirmer l’opération avant d’envoyer une campagne
* Diverses améliorations des performances et de la fiabilité dans

**Date de publication : 4 juin 2026**

* Les conversations récentes s’affichent dans la barre latérale et vous pouvez les renommer en ligne
* Ouvrez la page Conversations pour rechercher et poursuivre les conversations passées
* Les workflows d’accueil sont désormais des modèles de campagne avec un flux de remix plus simple
* Les modèles de bibliothèque utilisent un tableau plus clair avec des descriptions et des filtres de canal
* Les kits de marque affichent d’abord votre valeur par défaut et filtrent par publié ou brouillon
* Après avoir publié un brouillon de marque, vous accédez automatiquement au kit de marque dynamique
* Le chargement des données de la campagne et de la marque est plus fiable dès la connexion
* Diverses améliorations des performances et de la fiabilité dans

## Mai 2026 {#may-2026}

**Date de publication : 29 mai 2026**

* Générez des variantes d’image et choisissez parmi vos propres images directement dans l’éditeur d’e-mail.
* Ajoutez des images depuis votre ordinateur à l’aide d’un sélecteur de fichier local dans la barre d’outils image
* Décrivez ce que vous souhaitez et laissez AI générer l’image parfaite pour votre e-mail.
* Exportez l’e-mail terminé en tant que fichier HTML à partir du menu Plus .
* Les suggestions de Smart Copy s’affichent désormais dans la barre d’outils de l’e-mail lorsque vous modifiez du texte
* Cliquez sur une marque sur le tableau de campagne pour afficher instantanément les détails de la marque
* Définissez votre kit de marque par défaut directement à partir de la bibliothèque
* Les e-mails dans l’éditeur suivent désormais la séquence de workflow pour un ordre plus clair
* Les pièces jointes de l’écran d’accueil sont désormais limitées aux PDF pour un traitement fiable
* La navigation au clavier, la prise en charge des lecteurs d’écran et les préférences de mouvement sont plus cohérentes dans l’application
* Les libellés à venir marquent les pages en cours de création
* Diverses améliorations des performances et de la fiabilité dans

**Date de publication : 21 mai 2026**

* Modifier des images d&#39;email avec Adobe Express sans quitter l&#39;éditeur
* Créer des marques avec une progression claire pendant l’extraction et la publication des ressources
* Gérer les domaines et les expéditeurs à partir de la section Personnes
* Parcourir et gérer les listes de contacts à partir de la section Personnes
* Changement de modèles de ressources lors de l’utilisation de ressources marketing
* Télécharger des plans de campagne sous forme de fichiers Word avec des diagrammes de workflow
* Les listes des campagnes, compétences et workflows partagent une disposition plus claire
* Diverses améliorations des performances et de la fiabilité dans

**Date de publication : 14 mai 2026**

* La bibliothèque rassemble Assets, les modèles et les marques au même endroit
* La barre latérale et la navigation facilitent l’accès aux audiences et à votre kit de marque par défaut
* Télécharger votre plan de campagne as a PDF directement à partir des détails de la campagne
* La modification des marques ouvre des panneaux plus clairs pour la présentation, le style d’écriture et les couleurs
* Le compte à rebours d’essai apparaît dans l’en-tête pour que les jours restants restent visibles
* Les workflows marketing sportifs sont prêts lorsque votre brief correspond à cette catégorie
* La configuration manuelle de la version d’essai gère plus facilement les adresses des sites Web des entreprises
* Diverses améliorations des performances et de la fiabilité dans

**Date de publication : 8 mai 2026**

* La conversation Campaign offre une tentative claire lorsqu’une vérification de tâche en arrière-plan échoue
* Les mises à jour du statut des tâches et la disposition plein écran sont plus fluides sur les tableaux Campaign
* L’application démarre plus rapidement en chargeant les itinéraires et les traductions selon vos besoins
* Les données de la campagne et de la marque restent cohérentes dans l&#39;application
* Annuler et rétablir les modifications d’e-mail fonctionnent de manière plus prévisible
* Réessayez d’enregistrer lorsque l’éditeur d’e-mail rencontre une erreur temporaire
* Remplacer les images d’e-mail par un dimensionnement correct et des dimensions Adobe Express
* Chargez les listes d’audience depuis un fichier CSV en utilisant une boîte de dialogue d’importation plus claire
* Les balises de style d’écriture s’étendent pour afficher le texte intégral et le lien vers votre page de marque
* Diverses améliorations des performances et de la fiabilité dans

**Date de publication : 6 mai 2026**

* Les tableaux et listes de Campaign restent alignés sur les derniers détails pendant que vous travaillez
* Une clause de non-responsabilité générée par l’IA apparaît dans le chat de campagne et le créateur d’agents
* Les coordonnées de l’assistance utilisent désormais l’adresse e-mail dédiée aux campagnes CX Coworker
* La page d’accueil marketing supprime la section de liste d’attente et affiche plus clairement la vidéo principale
* Davantage d’écrans respectent automatiquement votre langue et les formats de date locaux
* Diverses améliorations des performances et de la fiabilité dans

## Avril 2026 {#apr-2026}

**Date de publication : 28 avril 2026**

* Les listes et tableaux de Campaign restent synchronisés et se sentent plus accrochés lorsque vous ouvrez ou mettez à jour une campagne
* Les workflows d’accueil sont désormais des modèles de campagne avec un flux de remix plus simple
* Les thèmes sombres et clairs utilisent le style Spectrum rafraîchi pour un aspect plus cohérent dans l&#39;application
* La discussion gère le contenu vide de l’assistant de manière élégante, avec des animations de statut plus fluides et plus claires
* Les conversations restaurées s’ouvrent sans clignotement du rail de conversation vierge et le fait de changer de variante d’e-mail ne fait plus scintiller le rail
* Les contrôles de chargement de fichier s’effacent après l’envoi ou la poursuite de la conversation
* « Aidez-moi à écrire » ne récupère des idées de message qu’après avoir ouvert la fenêtre contextuelle
* Les mises à jour de statut n’affichent une commande de développement que lorsqu’une liste doit être affichée
* Les cartes des campagnes, compétences et workflows partagent une disposition plus cohérente
* Les listes Campaign et les données de marque se chargent de manière plus fiable juste après votre connexion
* Diverses améliorations des performances et de la fiabilité dans

**Date de publication : 19 avril 2026**

* L’en-tête de l’application affiche désormais uniquement l’objet de l’e-mail (ou « Brouillon ») lors de la modification d’un e-mail, supprimant le préfixe numérique « E-mail N : » pour un titre plus ordonné
* Le menu Profil a été déplacé vers la barre latérale pour un accès plus rapide
* Les documents Source PDF s’affichent désormais sous forme de pilule sur les détails du kit de marque
* Le menu Profil a été déplacé vers la barre latérale pour un accès plus rapide
* Diverses améliorations des performances et de la fiabilité dans

**Date de publication : 18 avril 2026**

* L’entrée de la campagne de la page d’accueil dispose désormais d’un anneau lumineux animé et d’un dégradé de héros plus haut et plus lumineux
* « Surprenez-moi » déclenche un scintillement de dégradé coloré sur la bordure d’entrée
* L’application prend désormais en charge une mise en page plus cohérente sur les pages de produits
* Les liens vers la documentation ouvrent désormais le contenu le plus récent directement dans un nouvel onglet
* Diverses améliorations des performances et de la fiabilité dans
