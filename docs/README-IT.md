<div align="center">

![Intro](./assets/xpack/intro-bg.png)

[![GitHub license](https://img.shields.io/badge/License-Apache_2.0-blue.svg?labelColor=%20%239b8afb&color=%20%237a5af8)](https://github.com/TEN-framework/TEN-Agent/blob/main/LICENSE) [![XPack](https://img.shields.io/badge/XPack-Try%20it%20now!-blue?logo=googlechrome&logoColor=white)](https://xpack.ai)

[English](../README.md) | [简体中文](README-CN.md) | [日本語](README-JP.md) | [한국어](README-KR.md) | [Español](README-ES.md) | [Français](README-FR.md) | [Italiano](README-IT.md)

</div>

<br>


## Introduzione

TEN + XPack rappresenta la prossima generazione dello sviluppo di agenti IA, combinando le potenti capacità di agenti IA multimodali in tempo reale con l'integrazione di strumenti di livello enterprise. Questa integrazione consente agli sviluppatori di costruire agenti IA sofisticati che interagiscono senza problemi con sistemi esterni, API e strumenti tramite il Model Context Protocol (MCP).

## Cos'è TEN?

**TEN** è un ecosistema open source completo per creare, personalizzare e distribuire agenti IA conversazionali in tempo reale con capacità multimodali, incluse interazioni vocali, visive e avatar.

TEN include [TEN Framework](https://github.com/ten-framework/ten-framework), [TEN Turn Detection](https://github.com/ten-framework/ten-turn-detection), [TEN VAD](https://github.com/ten-framework/ten-vad), [TEN Agent](https://github.com/TEN-framework/ten-framework/tree/main/ai_agents/demo), [TMAN Designer](https://github.com/TEN-framework/ten-framework/tree/main/core/src/ten_manager/designer_frontend), [TEN Portal](https://github.com/ten-framework/portal). Per maggiori dettagli, consulta [🌍 Ecosistema TEN](#-ecosistema-ten).


## Cos'è XPack?

**XPack** è una piattaforma di sviluppo IA completa che fornisce strumenti e integrazioni di livello enterprise per costruire applicazioni IA avanzate. XPack si specializza nel collegare agenti IA a sistemi esterni tramite protocolli standardizzati come MCP (Model Context Protocol).

**Caratteristiche principali:**
- **Hub di Integrazione Strumenti**: Integrazioni pre-costruite con API e servizi popolari
- **Supporto Model Context Protocol (MCP)**: Modo standardizzato per collegare modelli IA a strumenti esterni
- **Sicurezza Enterprise**: Funzionalità di sicurezza avanzate per distribuzioni in produzione
- **Infrastruttura Scalabile**: Architettura cloud-native per applicazioni ad alte prestazioni
- **Esperienza Sviluppatore**: Strumenti intuitivi e documentazione completa

## Perché TEN + XPack?

La combinazione di TEN e XPack crea un ecosistema potente per lo sviluppo di agenti IA:

1. **Esperienza di Sviluppo Unificata**: Costruisci agenti IA multimodali con integrazione di strumenti senza problemi
2. **Capacità in Tempo Reale**: Elabora più flussi di dati mantenendo le connessioni degli strumenti
3. **Livello Enterprise**: Infrastruttura pronta per la produzione con sicurezza e scalabilità
4. **Piattaforma Estensibile**: Facile integrazione di strumenti e servizi personalizzati
5. **Sviluppo Visuale**: Interfaccia drag-and-drop per prototipazione e sviluppo rapido

## Avvio Rapido

### Prerequisiti

Prima di iniziare con TEN + XPack, assicurati di avere:

| Categoria | Requisiti |
| --- | --- |
| **Chiavi** | • Agora [App ID](https://docs.agora.io/en/video-calling/get-started/manage-agora-account?platform=web#create-an-agora-project) e [App Certificate](https://docs.agora.io/en/video-calling/get-started/manage-agora-account?platform=web#create-an-agora-project) (con quota gratuita mensile)<br>• Chiave API [OpenAI](https://openai.com/index/openai-api/) (LLM compatibile OpenAI)<br>• [Deepgram](https://deepgram.com/) ASR (crediti gratuiti disponibili alla registrazione)<br>• [Elevenlabs](https://elevenlabs.io/) TTS (crediti gratuiti disponibili alla registrazione)|
| **Installazione** | • [Docker](https://www.docker.com/) / [Docker Compose](https://docs.docker.com/compose/)<br>• [Node.js(LTS) v18](https://nodejs.org/en) |
| **Requisiti Minimi di Sistema** | • CPU >= 2 core<br>• RAM >= 4 GB |

<br>

> \[!NOTE]
>
> **macOS: Configurazione Docker su Apple Silicon**
>
> Deseleziona "Use Rosetta for x86/amd64 emulation" nelle impostazioni Docker. I tempi di build potrebbero essere più lenti su ARM, ma le prestazioni saranno normali quando distribuito su server x64.

<br>


### Avviare ed Eseguire TEN Agent

#### Clonare e Configurare

```bash
# Clonare il repository
git clone https://github.com/xpack-ai/ten-framework.git
cd ai_agents

# Configurare variabili d'ambiente
cp .env.example .env
# Modificare .env con chiavi API (OpenAI, Agora, ecc.)
```

**Configurare Agora App ID e App Certificate in .env:**

1. Ottenere Agora App ID e App Certificate da [Agora Console](https://console.agora.io/)
2. Aggiungere al file `.env`:
   ```
   AGORA_APP_ID=your_agora_app_id
   AGORA_APP_CERTIFICATE=your_agora_app_certificate
   ```

#### Iniziare con Docker

```bash
# Avviare container di sviluppo dell'agente
docker compose up -d

# Entrare nel container
docker exec -it ten_agent_dev bash

# Costruire l'agente (richiede ~5-8 minuti)
task use

# Avviare server web
task run
```

#### Accedere al TEN Agent Playground

Apri il tuo browser e vai a [localhost:3000](http://localhost:3000) per accedere al TEN Agent Playground.

### Configurazione XPack MCP

L'integrazione del Model Context Protocol (MCP) di XPack consente a TEN di connettersi a strumenti e servizi esterni, espandendo significativamente le capacità dell'agente.

#### Ottenere Chiave di Autenticazione XPack:

1. Visita [XPack.AI](https://xpack.ai/) e registra un account
2. Genera una chiave di autenticazione dal dashboard XPack

![XPack.ai Dashboard](./assets/xpack/xpack-dashboard.png)

#### Nella Configurazione del TEN Playground

##### 1. Selezionare il grafico `voice_assistant`
- Entra nel [TEN Agent Playground](http://localhost:3000)
- Nel pannello di destra:
   - Trova il menu a discesa **`Select Graph`**
   - Seleziona l'opzione **`voice_assistant`**

![select graph](./assets/ui-mcp-config-1.png)

##### 2. Aggiungere estensione MCP
- Clicca su **`Extension Icon Button`**
- Nel drawer che appare:
   - Trova la sezione **`LLM (Large Language Model)`**
   - Clicca sul **pulsante icona strumenti** accanto ad esso
- Nel menu a discesa:
   - Passa il mouse su **`Add Tools`** per mostrare il sottomenu
   - Seleziona **`mcp_client_python`**
- Clicca su **`Save changes`**

![add mcp extension](./assets/ui-mcp-config-2.png)


##### 3. Configurare client MCP
- Clicca su **`Setting Icon Button`**
- Nel pannello di configurazione:
   - Seleziona **`mcp_client_python`** dal menu a discesa **`Extension`**
   - Inserisci nel campo URL: `https://api.xpack.ai/v1/mcp?apikey={YOUR_XPACK_AUTH_KEY}`
- Clicca su **`Save changes`**

![add mcp extension](./assets/ui-mcp-config-3.png)

### Verifica

1. **Clicca sul pulsante `Connect`**: per iniziare la conversazione nel playground
2. **Verifica la riga di comando `task run`**: assicurati che le informazioni stampate indichino verifiche riuscite

![add mcp extension](./assets/ui-mcp-config-4.png)


## Esempi di Attività Popolari

Per collegare TEN a XPack, devi configurare un server MCP. Questo consente a TEN di scoprire e utilizzare gli strumenti disponibili tramite XPack.

### Query Meteo di Viaggio al Monte Tai

Verifica facilmente le condizioni meteorologiche e gli orari di alba/tramonto della tua destinazione di viaggio per aiutare con la pianificazione del viaggio.

```
Voglio viaggiare al Monte Tai in Cina il 15 luglio 2025. Per favore dimmi gli orari di alba/tramonto per quel giorno.
```
![ask weather](./assets/xpack/demo-weather.png)


### Query Prezzo Oro in Tempo Reale

Verifica rapidamente il prezzo attuale dell'oro e comprendi i fattori chiave che potrebbero influenzare le tendenze future dei prezzi.

```
Verifica il prezzo attuale dell'oro in tempo reale e dimmi i fattori specifici che potrebbero influenzare il prezzo futuro.
```

![ask the current real-time price of gold](./assets/xpack/demo-gold-real-time.png)

### Query Informazioni Volo

Cerca comodamente informazioni sui voli per rotte e orari specifici per aiutare con la pianificazione del viaggio.

```
Verifica i voli disponibili da Guangzhou a Pechino il 15 luglio 2025.
```
![ask flight information](./assets/xpack/demo-flight-info.png)
