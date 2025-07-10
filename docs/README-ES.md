<div align="center">

![Intro](./assets/xpack/intro-bg.png)

[![GitHub license](https://img.shields.io/badge/License-Apache_2.0-blue.svg?labelColor=%20%239b8afb&color=%20%237a5af8)](https://github.com/TEN-framework/TEN-Agent/blob/main/LICENSE) [![XPack](https://img.shields.io/badge/XPack-Try%20it%20now!-blue?logo=googlechrome&logoColor=white)](https://xpack.ai)

[English](../README.md) | [简体中文](README-CN.md) | [日本語](README-JP.md) | [한국어](README-KR.md) | [Español](README-ES.md) | [Français](README-FR.md) | [Italiano](README-IT.md)

</div>

<br>


## Introducción

TEN + XPack representa la próxima generación del desarrollo de agentes de IA, combinando las poderosas capacidades de agentes de IA multimodales en tiempo real con integración de herramientas de nivel empresarial. Esta integración permite a los desarrolladores construir agentes de IA sofisticados que interactúan sin problemas con sistemas externos, APIs y herramientas a través del Protocolo de Contexto de Modelo (MCP).

## ¿Qué es TEN?

**TEN** es un ecosistema integral de código abierto para crear, personalizar y desplegar agentes de IA conversacionales en tiempo real con capacidades multimodales, incluyendo interacciones de voz, visuales y avatar.

TEN incluye [TEN Framework](https://github.com/ten-framework/ten-framework), [TEN Turn Detection](https://github.com/ten-framework/ten-turn-detection), [TEN VAD](https://github.com/ten-framework/ten-vad), [TEN Agent](https://github.com/TEN-framework/ten-framework/tree/main/ai_agents/demo), [TMAN Designer](https://github.com/TEN-framework/ten-framework/tree/main/core/src/ten_manager/designer_frontend), [TEN Portal](https://github.com/ten-framework/portal). Para más detalles, consulta [🌍 Ecosistema TEN](#-ecosistema-ten).


## ¿Qué es XPack?

**XPack** es una plataforma integral de desarrollo de IA que proporciona herramientas e integraciones de nivel empresarial para construir aplicaciones de IA avanzadas. XPack se especializa en conectar agentes de IA a sistemas externos a través de protocolos estandarizados como MCP (Protocolo de Contexto de Modelo).

**Características clave:**
- **Hub de Integración de Herramientas**: Integraciones preconstruidas con APIs y servicios populares
- **Soporte del Protocolo de Contexto de Modelo (MCP)**: Forma estandarizada de conectar modelos de IA a herramientas externas
- **Seguridad Empresarial**: Características de seguridad avanzadas para despliegues de producción
- **Infraestructura Escalable**: Arquitectura nativa en la nube para aplicaciones de alto rendimiento
- **Experiencia del Desarrollador**: Herramientas intuitivas y documentación integral

## ¿Por qué TEN + XPack?

La combinación de TEN y XPack crea un ecosistema poderoso para el desarrollo de agentes de IA:

1. **Experiencia de Desarrollo Unificada**: Construye agentes de IA multimodales con integración perfecta de herramientas
2. **Capacidades en Tiempo Real**: Procesa múltiples flujos de datos mientras mantiene conexiones de herramientas
3. **Nivel Empresarial**: Infraestructura lista para producción con seguridad y escalabilidad
4. **Plataforma Extensible**: Integración fácil de herramientas y servicios personalizados
5. **Desarrollo Visual**: Interfaz de arrastrar y soltar para prototipado y desarrollo rápido

## Inicio Rápido

### Prerrequisitos

Antes de comenzar con TEN + XPack, asegúrate de tener:

| Categoría | Requisitos |
| --- | --- |
| **Claves** | • Agora [App ID](https://docs.agora.io/en/video-calling/get-started/manage-agora-account?platform=web#create-an-agora-project) y [App Certificate](https://docs.agora.io/en/video-calling/get-started/manage-agora-account?platform=web#create-an-agora-project) (con cuota gratuita mensual)<br>• Clave API de [OpenAI](https://openai.com/index/openai-api/) (LLM compatible con OpenAI)<br>• [Deepgram](https://deepgram.com/) ASR (créditos gratuitos disponibles al registrarse)<br>• [Elevenlabs](https://elevenlabs.io/) TTS (créditos gratuitos disponibles al registrarse)|
| **Instalación** | • [Docker](https://www.docker.com/) / [Docker Compose](https://docs.docker.com/compose/)<br>• [Node.js(LTS) v18](https://nodejs.org/en) |
| **Requisitos Mínimos del Sistema** | • CPU >= 2 núcleos<br>• RAM >= 4 GB |

<br>

> \[!NOTE]
>
> **macOS: Configuración de Docker en Apple Silicon**
>
> Desmarca "Use Rosetta for x86/amd64 emulation" en la configuración de Docker. Los tiempos de construcción pueden ser más lentos en ARM, pero el rendimiento será normal cuando se despliegue en servidores x64.

<br>


### Iniciar y Ejecutar TEN Agent

#### Clonar y Configurar

```bash
# Clonar el repositorio
git clone https://github.com/xpack-ai/ten-framework.git
cd ai_agents

# Configurar variables de entorno
cp .env.example .env
# Editar .env con claves API (OpenAI, Agora, etc.)
```

**Configurar Agora App ID y App Certificate en .env:**

1. Obtener Agora App ID y App Certificate de [Agora Console](https://console.agora.io/)
2. Agregar al archivo `.env`:
   ```
   AGORA_APP_ID=your_agora_app_id
   AGORA_APP_CERTIFICATE=your_agora_app_certificate
   ```

#### Comenzar con Docker

```bash
# Iniciar contenedor de desarrollo del agente
docker compose up -d

# Entrar al contenedor
docker exec -it ten_agent_dev bash

# Construir el agente (toma ~5-8 minutos)
task use

# Iniciar servidor web
task run
```

#### Acceder al TEN Agent Playground

Abre tu navegador y ve a [localhost:3000](http://localhost:3000) para acceder al TEN Agent Playground.

### Configuración de XPack MCP

La integración del Protocolo de Contexto de Modelo (MCP) de XPack permite que TEN se conecte a herramientas y servicios externos, expandiendo significativamente las capacidades del agente.

#### Obtener Clave de Autenticación de XPack:

1. Visita [XPack.AI](https://xpack.ai/) y registra una cuenta
2. Genera una clave de autenticación desde el panel de XPack

![XPack.ai Dashboard](./assets/xpack/xpack-dashboard.png)

#### En la Configuración del TEN Playground

##### 1. Seleccionar el gráfico `voice_assistant`
- Entra al [TEN Agent Playground](http://localhost:3000)
- En el panel derecho:
   - Encuentra el menú desplegable **`Select Graph`**
   - Selecciona la opción **`voice_assistant`**

![select graph](./assets/ui-mcp-config-1.png)

##### 2. Agregar extensión MCP
- Haz clic en **`Extension Icon Button`**
- En el cajón emergente:
   - Encuentra la sección **`LLM (Large Language Model)`**
   - Haz clic en el **botón de icono de herramientas** junto a él
- En el menú desplegable:
   - Pasa el cursor sobre **`Add Tools`** para mostrar el menú secundario
   - Selecciona **`mcp_client_python`**
- Haz clic en **`Save changes`**

![add mcp extension](./assets/ui-mcp-config-2.png)


##### 3. Configurar cliente MCP
- Haz clic en **`Setting Icon Button`**
- En el panel de configuración:
   - Selecciona **`mcp_client_python`** del desplegable **`Extension`**
   - Ingresa en el campo URL: `https://api.xpack.ai/v1/mcp?apikey={YOUR_XPACK_AUTH_KEY}`
- Haz clic en **`Save changes`**

![add mcp extension](./assets/ui-mcp-config-3.png)

### Verificación

1. **Haz clic en el botón `Connect`**: para comenzar la conversación en el playground
2. **Verifica la línea de comandos `task run`**: asegúrate de que la información impresa indique verificaciones exitosas

![add mcp extension](./assets/ui-mcp-config-4.png)


## Ejemplos de Tareas Populares

Para conectar TEN a XPack, necesitas configurar un servidor MCP. Esto permite que TEN descubra y utilice las herramientas disponibles a través de XPack.

### Consulta del Clima de Viaje al Monte Tai

Verifica fácilmente las condiciones climáticas y los horarios de amanecer/atardecer de tu destino de viaje para ayudar con la planificación del viaje.

```
Quiero viajar al Monte Tai en China el 15 de julio de 2025. Por favor, dime los horarios de amanecer/atardecer para ese día.
```
![ask weather](./assets/xpack/demo-weather.png)


### Consulta del Precio del Oro en Tiempo Real

Verifica rápidamente el precio actual del oro y comprende los factores clave que pueden influir en las tendencias futuras de precios.

```
Verifica el precio actual del oro en tiempo real y dime los factores específicos que podrían influir en el precio futuro.
```

![ask the current real-time price of gold](./assets/xpack/demo-gold-real-time.png)

### Consulta de Información de Vuelos

Busca convenientemente información de vuelos para rutas y horarios específicos para ayudar con la planificación de viajes.

```
Verifica los vuelos disponibles de Guangzhou a Beijing el 15 de julio de 2025.
```
![ask flight information](./assets/xpack/demo-flight-info.png)
