---
# TEMPLATE ONLY. Delete this line and the "hide" line below when you copy this file.
hide: true

# TITLE AND DESCRIPTION (shared)
# Title: title case, 60 characters or fewer.
# Description: one or two sentences, about 150-160 characters. Start with "Learn how to..." for tasks or "Learn about..." for concepts.
title: Titre de la page en Title Case
description: Découvrez comment [effectuer la tâche] avec Adobe CX Enterprise Coworker. [Deuxième phrase qui invite à l'action.]

# VIDEO TEAM FIELDS (owned by the video team)
# Remove all four lines if the page has no video.
doc-type: Feature Video
duration: 180
last-substantial-update: 2026-01-01T00:00:00.000Z
jira: KT-00000

# DOCUMENTATION FIELDS (owned by the documentation team)
role: User
level: Beginner
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: a4755ee1df166cc6efd4ffddca90d395d9e8287c
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 2%
---
<!--
TEMPLATE GUIDANCE. Delete this comment block before you commit a new page.

PURPOSE
Use this layout when one page presents both a video and written documentation.
If a page is documentation only or video only, you do not need this template.

THE ONE RULE
Every H2 section has exactly one owner: Documentation or Video. Each section
starts with an "Owner" comment. Keep those comments in the finished page. Edit
only the sections you own. If you need a change in the other team's section,
ask the owner or leave a comment on the pull request.

HOW TO USE THIS FILE
1. Copy this file into the folder for your topic. Use a descriptive, lowercase,
   hyphenated file name, for example manage-data-lake-retention.md.
2. Delete the two "TEMPLATE ONLY" lines in the front matter.
3. Replace everything in [brackets]. Delete any section you do not need.
4. Keep the section order: intro, video, then documentation.
5. Add a TOC entry for the page, if it is meant to appear in the table of contents.

KEEPING CONTENT FROM BEING OVERWRITTEN
- Do not embed the video inside a documentation section, and do not put steps
  inside the video section. Keep each format under its own heading.
- Give every H2 an explicit anchor, such as {#before-you-begin}, so links stay
  stable when a heading is reworded.
- Make the documentation complete without the video. Steps must work for a reader
  who never presses play (accessibility, search, and localization depend on it).
- Do not restate the steps in the video summary. Summarize what the video shows.
- Updating the video (new video ID, new duration) changes the video section and
  the video fields in the front matter only. Updating the steps changes the
  documentation sections only. Make each kind of change in its own commit.
- Each team edits its own front matter fields (see the comments above).
-->

# Titre de la page en cas de phrase {#page-id}

<!-- Owner: Documentation -->

[Une ou deux phrases qui expliquent ce que le lecteur peut faire et pourquoi c’est important. Ne commencez pas la page par une note, une liste ou un avertissement.]

## Regarder la vidéo {#watch-the-video}

<!-- Owner: Video. Documentation: do not edit this section. -->

[Une ou deux phrases qui disent ce que la vidéo montre et à qui elle est destinée.]

<!--
Replace VIDEO_ID with the ID from the video team, and remove this comment wrapper.
Add {transcript=true} after the closing parenthesis if a transcript is available.

>[!VIDEO](https://video.tv.adobe.com/v/VIDEO_ID?learn=on)
-->

[Facultatif : une note sur ce que la vidéo ne couvre pas ou sur la version de l’interface qu’elle affiche.]

## Avant de commencer {#before-you-begin}

<!-- Owner: Documentation -->

[Indiquez ce dont le lecteur a besoin avant de commencer : les autorisations, les licences, l’accès à une application ou à un sandbox, ou à une page associée à lire en premier. Supprimez cette section si aucune condition préalable ne s’applique.]

* [Prérequis 1.]
* [Prérequis 2.]

## [En-tête de tâche utilisant un verbe impératif] {#task-heading}

<!-- Owner: Documentation -->

[Une phrase qui introduit la tâche ou explique le concept dont dépend la tâche.]

1. [Commencez chaque étape par une action et terminez-la par un point.]
1. [Libellés d’interface en gras, par exemple **[!UICONTROL Envoyer]**.]
1. [Conserver chaque étape pour environ trois clics ou décisions.]

   [Capture d’écran facultative sur la ligne après l’étape qui affiche l’interface. Utilisez la syntaxe d’image Markdown, avec un texte secondaire qui décrit l’objectif ou la fonctionnalité affiché.]

1. [Étape finale.]

### [En-tête facultatif de sous-tâche ou d’option] {#subtask-heading}

<!-- Owner: Documentation -->

[Utilisez un H3 uniquement lorsque le H2 comporte deux parties ou plus.]

## Exemples de prompts {#example-prompts}

<!-- Owner: Documentation. Delete this section if it does not apply. -->

* « [ Invite que le lecteur peut copier et adapter ] »
* « [Autre invite.] »

## Dépannage {#troubleshooting}

<!-- Owner: Documentation. Delete this section if it does not apply. -->

[Décrivez un problème que le lecteur pourrait rencontrer, puis comment le résoudre.]
