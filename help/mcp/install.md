---
title: Installation de la passerelle CX Coworker Adobe
description: Découvrez comment connecter des clients compatibles MCP à la passerelle Adobe CX Coworker.
hide: true
source-git-commit: 6c126810936bea3e883d74e6ff685991cb40cd4a
workflow-type: tm+mt
source-wordcount: '1004'
ht-degree: 0%
---
# Installation de la passerelle CX Coworker Adobe {#mcp-install}

Lisez ce guide pour savoir comment connecter un client compatible MCP à la passerelle Adobe CX Coworker.  La passerelle CX Coworker utilise un point d’entrée pour tous les outils de produit documentés :

```
https://cx-coworker-gateway.adobe.io/mcp
```

Avant l’installation, vérifiez que votre organisation et votre compte utilisateur peuvent accéder aux outils de produit dont vous avez besoin. Voir [Accès aux outils de la passerelle CX Coworker](access.md).

## Fonctionnement de l’installation {#mcp-install-how}

La passerelle CX Coworker utilise un transport HTTP distant avec un flux de connexion Adobe basé sur un navigateur. Pour chaque client pris en charge, le modèle de configuration est le même :

1. Ajoutez l’URL du point d’entrée : `https://cx-coworker-gateway.adobe.io/mcp`.
2. Enregistrez ou activez la connexion.
3. Effectuez la connexion à Adobe à partir du navigateur la première fois que le client appelle un outil.
4. Définissez le contexte du produit pour la session si vos outils le demandent : organisation pour tous les produits, sandbox pour les outils basés sur Experience Platform et vue de données pour Customer Journey Analytics. Voir [Product Context pour les appels d’outils](#mcp-connect-params).

>[!NOTE]
>
>Aucune clé API, aucun jeton porteur, aucun secret client ou aucun en-tête supplémentaire n’est requis dans la configuration du client MCP. L’authentification est gérée via le flux de connexion Adobe lors de la première utilisation.

## Installation d’entreprise (gérée par l’administrateur) {#mcp-install-enterprise}

La plupart des plans client MCP d’équipe et d’entreprise nécessitent qu’un administrateur ajoute des connecteurs personnalisés pour l’organisation. Dans ces environnements, l’installation se fait en deux étapes :

1. Un administrateur ajoute le point d’entrée de la passerelle CX Coworker une fois pour l’organisation.
2. Chaque utilisateur active le connecteur et se connecte avec ses propres informations d’identification Adobe.

### Étape 1 : un administrateur ajoute le point d’entrée {#mcp-install-enterprise-admin}

L’administrateur ajoute `https://cx-coworker-gateway.adobe.io/mcp` en tant que connecteur personnalisé ou serveur MCP distant dans les paramètres d’organisation du client. L’emplacement exact dépend du client ou de la cliente.

#### Claude Équipe et Entreprise {#mcp-install-enterprise-claude}

Dans [!DNL Claude] plans Équipe et Entreprise, les connecteurs au niveau de l’organisation sont gérés par un espace de travail **Propriétaire** ou **Propriétaire de Principal**.

1. Connectez-vous à [!DNL Claude] en tant que **Propriétaire** ou **Propriétaire du Principal**.
2. Accédez à **Paramètres** > **Administration** > **Connecteurs**. Sur certains plans, il s’affiche sous la forme **Paramètres de l’organisation** > **Connecteurs**.
3. Sélectionnez **Ajouter un connecteur personnalisé**.
4. Saisissez `https://cx-coworker-gateway.adobe.io/mcp` comme URL du serveur et utilisez un nom reconnaissable, par exemple « Adobe for CX Coworker Gateway ».
5. Enregistrez le connecteur.

#### Équipe et entreprise ChatGPT {#mcp-install-enterprise-chatgpt}

Dans les espaces de travail [!DNL ChatGPT] Équipe et Entreprise, les connecteurs sont ajoutés par un administrateur d’espace de travail.

1. Connectez-vous à [!DNL ChatGPT] en tant qu’administrateur d’espace de travail.
2. Accédez à **Paramètres** > **Connecteurs**. Sur certains plans, il s’affiche sous la forme **Paramètres** > **Applications et connecteurs**.
3. Sélectionnez **Ajouter un connecteur**.
4. Saisissez `https://cx-coworker-gateway.adobe.io/mcp` comme URL du serveur.
5. Enregistrez le connecteur. Selon la configuration de votre espace de travail, cette étape peut nécessiter d’activer le mode Développeur ou d’accorder une approbation au niveau de l’espace de travail.

#### Autres clients gérés par l&#39;organisation {#mcp-install-enterprise-other}

Pour les autres clients qui prennent en charge les connecteurs distants gérés par l’organisation, ajoutez la passerelle CX Coworker en tant que serveur HTTP MCP distant à l’aide de `https://cx-coworker-gateway.adobe.io/mcp`. Laissez les en-têtes facultatifs, les champs de jeton porteur, les champs d’ID client et les champs secrets client vides, sauf si votre client nécessite une valeur d’espace réservé.

### Étape 2 : les utilisateurs activent le connecteur {#mcp-install-enterprise-user}

Lorsqu’un administrateur ajoute la passerelle CX Coworker, chaque utilisateur l’active pour son propre compte :

1. Ouvrez les paramètres du connecteur personnel, de l’application ou du MCP dans le client.
2. Recherchez et activez le connecteur de passerelle CX Coworker.
3. Démarrez une conversation, appelez l’un des outils Adobe et terminez la connexion à Adobe à l’aide du navigateur lorsque vous y êtes invité.
4. Définissez le contexte du produit pour la session si vos outils le demandent : organisation pour tous les produits, sandbox pour les outils basés sur Experience Platform et vue de données pour Customer Journey Analytics. Voir [Product Context pour les appels d’outils](#mcp-connect-params).

Les utilisateurs n’ont pas besoin de saisir eux-mêmes l’URL lorsqu’un administrateur a déjà ajouté le connecteur pour l’organisation.

## Installation individuelle (libre-service) {#mcp-install-individual}

Si vous utilisez un plan individuel, un client développeur configuré localement ou une organisation qui permet aux membres d’ajouter leurs propres connecteurs, ajoutez le point d’entrée directement dans vos propres paramètres client.

### Claude individuel {#mcp-install-individual-claude}

Pour `claude.ai` et [!DNL Claude] Desktop sur un plan individuel :

1. Ouvrez **Paramètres** > **Connecteurs**.
2. Sélectionnez **Ajouter un connecteur personnalisé**.
3. Saisissez `https://cx-coworker-gateway.adobe.io/mcp` comme URL du serveur.
4. Enregistrez et activez le connecteur, puis terminez le flux de connexion Adobe lors de la première utilisation.

### ChatGPT individuel {#mcp-install-individual-chatgpt}

1. Ouvrez **Paramètres** > **Connecteurs**. Sur certains plans, il s’affiche sous la forme **Paramètres** > **Applications et connecteurs**.
2. Sélectionnez **Ajouter un connecteur**.
3. Saisissez `https://cx-coworker-gateway.adobe.io/mcp` comme URL du serveur.
4. Enregistrez et activez le connecteur, puis terminez le flux de connexion Adobe lors de la première utilisation.

### Curseur {#mcp-install-individual-cursor}

1. Ouvrez **Paramètres** > **MCP**.
2. Sélectionnez **Ajouter un nouveau serveur**.
3. Saisissez `https://cx-coworker-gateway.adobe.io/mcp` comme URL du serveur.
4. Sélectionnez **Connexion** et terminez le flux de connexion Adobe.

Après la connexion, les outils Adobe for CX Coworker Gateway sont disponibles dans les modes Compositeur et Agent du curseur.

### Claude Code {#mcp-install-individual-claude-code}

Ajoutez le point d’entrée à partir du terminal :

```bash
claude mcp add --transport http cx-enterprise https://cx-coworker-gateway.adobe.io/mcp
```

Ensuite, lancez [!DNL Claude Code] et exécutez :

```text
/mcp
```

Sélectionnez le serveur `cx-enterprise` et terminez le flux de connexion Adobe dans votre navigateur.

### Codex {#mcp-install-individual-codex}

Ajoutez le point d’entrée à partir du terminal :

```bash
codex mcp add cx-enterprise --url https://cx-coworker-gateway.adobe.io/mcp
```

S’authentifier :

```bash
codex mcp login cx-enterprise
```

Vérifiez la configuration :

```bash
codex mcp list
```

Vous pouvez également ajouter le point d’entrée directement à `~/.codex/config.toml` :

```toml
[mcp_servers.cx-enterprise]
url = "https://cx-coworker-gateway.adobe.io/mcp"
```

### Configuration JSON générale {#mcp-install-individual-json}

Pour les clients qui acceptent une configuration de serveur MCP basée sur JSON, utilisez l’un des formats suivants selon que votre client prend en charge le protocole HTTP distant natif ou nécessite un pont local.

**Via `mcp-remote` pont**

```json
{
  "mcpServers": {
    "cx-enterprise": {
      "command": "npx",
      "args": [
        "mcp-remote",
        "https://cx-coworker-gateway.adobe.io/mcp"
      ]
    }
  }
}
```

**HTTP distant natif**

```json
{
  "mcpServers": {
    "cx-enterprise": {
      "url": "https://cx-coworker-gateway.adobe.io/mcp",
      "transport": "http"
    }
  }
}
```

### Autres clients {#mcp-install-individual-other}

Pour les autres clients de bureau ou web avec prise en charge de MCP à distance, ajoutez Adobe for CX Coworker Gateway en tant que serveur HTTP à distance à l’aide de `https://cx-coworker-gateway.adobe.io/mcp`. Laissez les en-têtes facultatifs, les champs de jeton porteur, les champs d’ID client et les champs secrets client vides, sauf si votre client nécessite une valeur d’espace réservé.

## Contexte de produit pour les appels d’outils {#mcp-connect-params}

Le MCP étend chaque appel d’outil à une organisation Adobe active. En outre, les exigences de contexte dépendent du produit :

- **Produits Experience Platform** — Les outils Real-Time CDP, Experience Platform et Journey Optimizer fonctionnent dans un sandbox Experience Platform. Définissez le sandbox une fois par session ; les trois le partagent.
- **Autres produits** — Les produits non créés sur Experience Platform n’utilisent pas le contexte sandbox. Les outils Adobe Analytics, Customer Journey Analytics, Workfront, Marketo et Target sont résolus par rapport à leurs propres ressources de produit, par exemple, les vues de données pour Customer Journey Analytics et les suites de rapports pour Adobe Analytics.

Définition du contexte une fois au début d’une session : les outils de produit individuels ne changent pas d’organisation, de sandbox ou de vues de données en milieu de session. Voir [Outils de contexte de session](context-tools.md) pour les outils qui définissent le contexte de l’organisation, du sandbox et de la vue de données.

Exemple:

> « Utilisez des `1234ABCD@AdobeOrg` d’organisation, des `prod` de sandbox et des `My Company — Global` de vue de données pour cette session. »

Si vous ne connaissez pas les valeurs requises, demandez à votre client MCP de répertorier les organisations, les sandbox ou les vues de données disponibles pour vos informations d’identification Adobe.