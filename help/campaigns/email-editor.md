---
description: description.
title: Comprendre l’éditeur d’e-mail
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
feature_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: 94cf399a48d13ee83c702804b50fdccd4baa9d71
workflow-type: tm+mt
source-wordcount: '476'
ht-degree: 0%
---
# Comprendre l’éditeur d’e-mail {#email-editor}

L’éditeur d’email permet d’affiner un email généré par l’IA directement sur le tableau de campagne. Modifiez l’objet et le pré-titre, mettez en forme le texte et les images sur la ligne ou remplacez-les dans un autre modèle.

La sélection d’une carte e-mail sur le panorama de la campagne ouvre l’éditeur d’e-mail sous forme de panneau latéral. À partir de là, l’utilisateur peut modifier l’objet et le pré-titre (avec des alternatives suggérées par l’IA), cliquer dans le corps de l’e-mail pour sélectionner et formater le texte ou les images, basculer entre des variantes générées par l’IA, échanger le modèle HTML, vérifier la compatibilité client-e-mail et envoyer un e-mail de test dans sa propre boîte de réception. Les modifications sont enregistrées automatiquement et les versions antérieures peuvent être examinées et restaurées.

## Accès

1. Ouvrez la campagne souhaitée et cliquez sur Ouvrir l’éditeur dans la carte d’e-mail.

CAPTURE D’ÉCRAN

1. Modifiez directement les champs **Objet** et **Pré-titre** ou cliquez sur **Suggestions intelligentes** en regard de pour accéder à des alternatives générées par l’IA.
1. Cliquez dans le corps de l’e-mail pour sélectionner un bloc de texte ou une image, puis utilisez la barre d’outils flottante qui s’affiche pour mettre en forme le texte ou gérer l’image.
1. Utilisez **Changer de modèle HTML** pour remplacer le corps de l’e-mail par un modèle différent.
1. Utilisez **Envoyer un e-mail de test**, saisissez l’adresse d’un destinataire et cliquez sur **Envoyer** pour envoyer un aperçu dynamique par e-mail à cette adresse.
1. Utilisez l’icône d’historique de versions pour prévisualiser et restaurer une version enregistrée antérieure.
1. Les modifications sont enregistrées automatiquement : aucune étape d’enregistrement manuel n’est requise.

### Comportements clés

- Les chargements d’images sont limités à 10 Mo ; les images de plus de 3 Mo sont automatiquement compressées, avec une note de qualité recommandant les images de moins de 3 Mo.
- Les champs Objet et Pré-titre offrent la possibilité d’obtenir des alternatives générées par l’IA via cette ICÔNE.
- Utilisez Ctrl+z (CMD+z pour Mac) pour « Annuler » et inverser votre dernière action. Utilisez Ctrl+Y (CMD+y pour Mac) pour « Rétablir » et inverser votre dernière annulation. KEITH CHECK STANDARD
- Les versions enregistrées précédentes peuvent être prévisualisées et restaurées à partir d’un panneau d’historique des versions via cette ICÔNE.
- Par défaut, nous générons deux variantes par e-mail ; vous pouvez sélectionner la variante souhaitée via leurs miniatures sur la droite.

## Ce que cette fonctionnalité ne fait pas

- Il ne s’agit pas d’un créateur de blocs par glisser-déposer : il n’y a pas de bibliothèque de blocs et les blocs de contenu ne peuvent pas être ajoutés, supprimés ou réorganisés ; la modification se fait directement sur l’email HTML existant.
- Actuellement, il ne prend pas en charge l’insertion de balises de personnalisation/fusion.
- Il ne fournit pas de champ de texte secondaire pour les images.
- Il n’impose pas de vérification de l’objet, du pré-titre ni d’autres vérifications au niveau du contenu avant qu’un e-mail ne soit considéré comme « prêt » ; les seules vérifications avant le lancement sont au niveau de la campagne (configuration de l’envoi, e-mail de test envoyé, audience réelle), et non pas des vérifications sur le contenu de l’e-mail lui-même.
- Le basculement de l’aperçu pour ordinateur/mobile n’est pas disponible dans la vue d’édition d’e-mail de Campaign standard. [ENTRÉES NÉCESSAIRES pour confirmer la portée]
- [ENTRÉES NÉCESSAIRES — à confirmer auprès de l’ingénieur : si l’éditeur devient entièrement en lecture seule (et pas seulement le champ expéditeur) une fois qu’une campagne a été activée/lancée.]
