---
source-git-commit: e5bf2a0a2ee55513b32442f70d01dc5825ac9d6a
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 5%
---
# Documentation sur CX Enterprise Coworker

Source pour le jeu de documentation Adobe CX Enterprise Coworker.

## Configuration de la publication

Utiliser les workflows de validation et de mise en miroir d’articles partagés dans `.github/workflows/`.
Le workflow de validation s’exécute pour les demandes d’extraction et les envois vers `main`.
Le workflow de mise en miroir s’exécute lorsque vous effectuez une opération push sur `main`.

Utilisez des `markdownlint_custom.json` pour les remplacements de règles Markdown et `linkcheckexclude.json` par exemple les exclusions d’URL.
Le fichier `pipeline.opts` suit la configuration de vérification des liens dans `cx-enterprise-ai.en`.
Ajoutez des redirections d’URL à `redirects.csv` à l’aide des colonnes `source,dest` .
