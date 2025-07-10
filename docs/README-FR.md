<div align="center">

![Intro](./assets/xpack/intro-bg.png)

[![GitHub license](https://img.shields.io/badge/License-Apache_2.0-blue.svg?labelColor=%20%239b8afb&color=%20%237a5af8)](https://github.com/TEN-framework/TEN-Agent/blob/main/LICENSE) [![XPack](https://img.shields.io/badge/XPack-Try%20it%20now!-blue?logo=googlechrome&logoColor=white)](https://xpack.ai)

[English](../README.md) | [简体中文](README-CN.md) | [日本語](README-JP.md) | [한국어](README-KR.md) | [Español](README-ES.md) | [Français](README-FR.md) | [Italiano](README-IT.md)

</div>

<br>


## Introduction

TEN + XPack représente la prochaine génération du développement d'agents IA, combinant les puissantes capacités d'agents IA multimodaux en temps réel avec l'intégration d'outils de niveau entreprise. Cette intégration permet aux développeurs de construire des agents IA sophistiqués qui interagissent de manière transparente avec des systèmes externes, des APIs et des outils via le Protocole de Contexte de Modèle (MCP).

## Qu'est-ce que TEN ?

**TEN** est un écosystème open source complet pour créer, personnaliser et déployer des agents IA conversationnels en temps réel avec des capacités multimodales, incluant les interactions vocales, visuelles et d'avatar.

TEN inclut [TEN Framework](https://github.com/ten-framework/ten-framework), [TEN Turn Detection](https://github.com/ten-framework/ten-turn-detection), [TEN VAD](https://github.com/ten-framework/ten-vad), [TEN Agent](https://github.com/TEN-framework/ten-framework/tree/main/ai_agents/demo), [TMAN Designer](https://github.com/TEN-framework/ten-framework/tree/main/core/src/ten_manager/designer_frontend), [TEN Portal](https://github.com/ten-framework/portal). Pour plus de détails, consultez [🌍 Écosystème TEN](#-écosystème-ten).


## Qu'est-ce que XPack ?

**XPack** est une plateforme de développement IA complète qui fournit des outils et intégrations de niveau entreprise pour construire des applications IA avancées. XPack se spécialise dans la connexion d'agents IA à des systèmes externes via des protocoles standardisés comme MCP (Protocole de Contexte de Modèle).

**Caractéristiques clés :**
- **Hub d'Intégration d'Outils** : Intégrations pré-construites avec des APIs et services populaires
- **Support du Protocole de Contexte de Modèle (MCP)** : Façon standardisée de connecter les modèles IA aux outils externes
- **Sécurité Entreprise** : Fonctionnalités de sécurité avancées pour les déploiements en production
- **Infrastructure Évolutive** : Architecture cloud-native pour les applications haute performance
- **Expérience Développeur** : Outils intuitifs et documentation complète

## Pourquoi TEN + XPack ?

La combinaison de TEN et XPack crée un écosystème puissant pour le développement d'agents IA :

1. **Expérience de Développement Unifiée** : Construisez des agents IA multimodaux avec une intégration d'outils transparente
2. **Capacités Temps Réel** : Traitez plusieurs flux de données tout en maintenant les connexions d'outils
3. **Niveau Entreprise** : Infrastructure prête pour la production avec sécurité et évolutivité
4. **Plateforme Extensible** : Intégration facile d'outils et services personnalisés
5. **Développement Visuel** : Interface glisser-déposer pour le prototypage et développement rapide

## Démarrage Rapide

### Prérequis

Avant de commencer avec TEN + XPack, assurez-vous d'avoir :

| Catégorie | Exigences |
| --- | --- |
| **Clés** | • Agora [App ID](https://docs.agora.io/en/video-calling/get-started/manage-agora-account?platform=web#create-an-agora-project) et [App Certificate](https://docs.agora.io/en/video-calling/get-started/manage-agora-account?platform=web#create-an-agora-project) (avec quota gratuit mensuel)<br>• Clé API [OpenAI](https://openai.com/index/openai-api/) (LLM compatible OpenAI)<br>• [Deepgram](https://deepgram.com/) ASR (crédits gratuits disponibles à l'inscription)<br>• [Elevenlabs](https://elevenlabs.io/) TTS (crédits gratuits disponibles à l'inscription)|
| **Installation** | • [Docker](https://www.docker.com/) / [Docker Compose](https://docs.docker.com/compose/)<br>• [Node.js(LTS) v18](https://nodejs.org/en) |
| **Exigences Système Minimales** | • CPU >= 2 cœurs<br>• RAM >= 4 GB |

<br>

> \[!NOTE]
>
> **macOS : Configuration Docker sur Apple Silicon**
>
> Décochez "Use Rosetta for x86/amd64 emulation" dans les paramètres Docker. Les temps de construction peuvent être plus lents sur ARM, mais les performances seront normales lors du déploiement sur des serveurs x64.

<br>


### Lancer et Exécuter TEN Agent

#### Cloner et Configurer

```bash
# Cloner le dépôt
git clone https://github.com/xpack-ai/ten-framework.git
cd ai_agents

# Configurer les variables d'environnement
cp .env.example .env
# Éditer .env avec les clés API (OpenAI, Agora, etc.)
```

**Configurer Agora App ID et App Certificate dans .env :**

1. Obtenir Agora App ID et App Certificate depuis [Agora Console](https://console.agora.io/)
2. Ajouter au fichier `.env` :
   ```
   AGORA_APP_ID=your_agora_app_id
   AGORA_APP_CERTIFICATE=your_agora_app_certificate
   ```

#### Commencer avec Docker

```bash
# Démarrer le conteneur de développement de l'agent
docker compose up -d

# Entrer dans le conteneur
docker exec -it ten_agent_dev bash

# Construire l'agent (prend ~5-8 minutes)
task use

# Démarrer le serveur web
task run
```

#### Accéder au TEN Agent Playground

Ouvrez votre navigateur et allez à [localhost:3000](http://localhost:3000) pour accéder au TEN Agent Playground.

### Configuration XPack MCP

L'intégration du Protocole de Contexte de Modèle (MCP) de XPack permet à TEN de se connecter à des outils et services externes, étendant considérablement les capacités de l'agent.

#### Obtenir la Clé d'Authentification XPack :

1. Visitez [XPack.AI](https://xpack.ai/) et créez un compte
2. Générez une clé d'authentification depuis le tableau de bord XPack

![XPack.ai Dashboard](./assets/xpack/xpack-dashboard.png)

#### Dans la Configuration du TEN Playground

##### 1. Sélectionner le graphique `voice_assistant`
- Entrez dans le [TEN Agent Playground](http://localhost:3000)
- Dans le panneau de droite :
   - Trouvez le menu déroulant **`Select Graph`**
   - Sélectionnez l'option **`voice_assistant`**

![select graph](./assets/ui-mcp-config-1.png)

##### 2. Ajouter l'extension MCP
- Cliquez sur **`Extension Icon Button`**
- Dans le tiroir qui apparaît :
   - Trouvez la section **`LLM (Large Language Model)`**
   - Cliquez sur le **bouton icône d'outils** à côté
- Dans le menu déroulant :
   - Survolez **`Add Tools`** pour afficher le sous-menu
   - Sélectionnez **`mcp_client_python`**
- Cliquez sur **`Save changes`**

![add mcp extension](./assets/ui-mcp-config-2.png)


##### 3. Configurer le client MCP
- Cliquez sur **`Setting Icon Button`**
- Dans le panneau de configuration :
   - Sélectionnez **`mcp_client_python`** dans le menu déroulant **`Extension`**
   - Entrez dans le champ URL : `https://api.xpack.ai/v1/mcp?apikey={YOUR_XPACK_AUTH_KEY}`
- Cliquez sur **`Save changes`**

![add mcp extension](./assets/ui-mcp-config-3.png)

### Vérification

1. **Cliquez sur le bouton `Connect`** : pour commencer la conversation dans le playground
2. **Vérifiez la ligne de commande `task run`** : assurez-vous que les informations imprimées indiquent des vérifications réussies

![add mcp extension](./assets/ui-mcp-config-4.png)


## Exemples de Tâches Populaires

Pour connecter TEN à XPack, vous devez configurer un serveur MCP. Cela permet à TEN de découvrir et d'utiliser les outils disponibles via XPack.

### Requête Météo de Voyage au Mont Tai

Vérifiez facilement les conditions météorologiques et les heures de lever/coucher du soleil de votre destination de voyage pour aider à la planification du voyage.

```
Je veux voyager au Mont Tai en Chine le 15 juillet 2025. Veuillez me dire les heures de lever/coucher du soleil pour ce jour.
```
![ask weather](./assets/xpack/demo-weather.png)


### Requête du Prix de l'Or en Temps Réel

Vérifiez rapidement le prix actuel de l'or et comprenez les facteurs clés qui peuvent influencer les tendances futures des prix.

```
Vérifiez le prix actuel de l'or en temps réel et dites-moi les facteurs spécifiques qui pourraient influencer le prix futur.
```

![ask the current real-time price of gold](./assets/xpack/demo-gold-real-time.png)

### Requête d'Informations de Vol

Recherchez facilement des informations de vol pour des itinéraires et horaires spécifiques pour aider à la planification de voyage.

```
Vérifiez les vols disponibles de Guangzhou à Beijing le 15 juillet 2025.
```
![ask flight information](./assets/xpack/demo-flight-info.png)
