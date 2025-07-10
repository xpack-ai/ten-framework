<div align="center">

![Intro](./assets/xpack/intro-bg.png)

[![GitHub license](https://img.shields.io/badge/License-Apache_2.0-blue.svg?labelColor=%20%239b8afb&color=%20%237a5af8)](https://github.com/TEN-framework/TEN-Agent/blob/main/LICENSE) [![XPack](https://img.shields.io/badge/XPack-Try%20it%20now!-blue?logo=googlechrome&logoColor=white)](https://xpack.ai)

[English](../README.md) | [简体中文](README-CN.md) | [日本語](README-JP.md) | [한국어](README-KR.md) | [Español](README-ES.md) | [Français](README-FR.md) | [Italiano](README-IT.md)

</div>

<br>


## 介绍

TEN + XPack 代表了 AI 智能体开发的下一代技术，结合了实时多模态 AI 智能体的强大功能和企业级工具集成能力。这种集成使开发者能够构建复杂的 AI 智能体，通过模型上下文协议 (MCP) 与外部系统、API 和工具无缝交互。

## 什么是 TEN？

**TEN** 是一个全面的开源生态系统，用于创建、定制和部署具有多模态功能的实时对话 AI 智能体，包括语音、视觉和虚拟形象交互。

TEN 包括 [TEN Framework](https://github.com/ten-framework/ten-framework)、[TEN Turn Detection](https://github.com/ten-framework/ten-turn-detection)、[TEN VAD](https://github.com/ten-framework/ten-vad)、[TEN Agent](https://github.com/TEN-framework/ten-framework/tree/main/ai_agents/demo)、[TMAN Designer](https://github.com/TEN-framework/ten-framework/tree/main/core/src/ten_manager/designer_frontend) 和 [TEN Portal](https://github.com/ten-framework/portal)。查看 [🌍 TEN 生态系统](#-ten-生态系统) 了解更多详情。


## 什么是 XPack？

**XPack** 是一个全面的 AI 开发平台，为构建复杂的 AI 应用程序提供企业级工具和集成。XPack 专门通过标准化协议（如 MCP（模型上下文协议））将 AI 智能体与外部系统连接。

**主要特性：**
- **工具集成中心**：与流行 API 和服务的预构建集成
- **模型上下文协议 (MCP) 支持**：将 AI 模型与外部工具连接的标准化方式
- **企业安全**：用于生产部署的高级安全功能
- **可扩展基础设施**：用于高性能应用程序的云原生架构
- **开发者体验**：直观的工具和全面的文档

## 为什么选择 TEN + XPack？

TEN 和 XPack 的结合为 AI 智能体开发创造了一个强大的生态系统：

1. **统一开发体验**：构建具有无缝工具集成的多模态 AI 智能体
2. **实时能力**：在保持工具连接的同时处理多个数据流
3. **企业级**：具有安全性和可扩展性的生产就绪基础设施
4. **可扩展平台**：轻松集成自定义工具和服务
5. **可视化开发**：用于快速原型设计和开发的拖放界面

## 快速开始

### 前置要求

在开始使用 TEN + XPack 之前，请确保您具备以下条件：

| 类别 | 要求 |
| --- | --- |
| **密钥** | • Agora [App ID](https://docs.agora.io/en/video-calling/get-started/manage-agora-account?platform=web#create-an-agora-project) 和 [App Certificate](https://docs.agora.io/en/video-calling/get-started/manage-agora-account?platform=web#create-an-agora-project)（每月免费分钟数）<br>• [OpenAI](https://openai.com/index/openai-api/) API 密钥（任何与 OpenAI 兼容的 LLM）<br>• [Deepgram](https://deepgram.com/) ASR（注册即可获得免费积分）<br>• [Elevenlabs](https://elevenlabs.io/) TTS（注册即可获得免费积分）|
| **安装** | • [Docker](https://www.docker.com/) / [Docker Compose](https://docs.docker.com/compose/)<br>• [Node.js(LTS) v18](https://nodejs.org/en) |
| **最低系统要求** | • CPU >= 2 核<br>• RAM >= 4 GB |

<br>

> \[!NOTE]
>
> **macOS：Apple Silicon 上的 Docker 设置**
>
> 在 Docker 设置中取消选中"使用 Rosetta 进行 x86/amd64 仿真"，这可能会导致 ARM 上的构建时间较慢，但部署到 x64 服务器时性能将正常。

<br>


### 启动并运行 TEN Agent

#### 克隆和设置

```bash
# 克隆仓库
git clone https://github.com/xpack-ai/ten-framework.git
cd ai_agents

# 设置环境变量
cp .env.example .env
# 使用您的 API 密钥编辑 .env（OpenAI、Agora 等）
```

**在 .env 中设置 Agora App ID 和 App Certificate：**

1. 从 [Agora Console](https://console.agora.io/) 获取您的 Agora App ID 和 App Certificate
2. 将它们添加到您的 `.env` 文件中：
   ```
   AGORA_APP_ID=your_agora_app_id
   AGORA_APP_CERTIFICATE=your_agora_app_certificate
   ```

#### 使用 Docker 启动

```bash
# 启动智能体开发容器
docker compose up -d

# 进入容器
docker exec -it ten_agent_dev bash

# 构建智能体（约 5-8 分钟）
task use

# 启动 Web 服务器
task run
```

#### 访问 TEN Agent Playground

打开浏览器并访问 [localhost:3000](http://localhost:3000) 来访问 TEN Agent Playground。

### 配置 XPack MCP

XPack 的模型上下文协议 (MCP) 集成使 TEN 能够连接外部工具和服务，大大扩展您的智能体功能。

#### 获取您的 XPack 认证密钥：

1. 访问 [XPack.AI](https://xpack.ai/) 并注册账户
2. 从您的 XPack 仪表板生成认证密钥

![XPack.ai Dashboard](./assets/xpack/xpack-dashboard.png)

#### 在 TEN Playground 配置中

##### 1. 选择 `voice_assistant` 图表
- 进入 [TEN Agent Playground](http://localhost:3000)
- 在右侧面板中：
   - 找到 **`Select Graph`** 下拉菜单
   - 选择 **`voice_assistant`** 选项

![select graph](./assets/ui-mcp-config-1.png)

##### 2. 添加 MCP 扩展
- 点击 **“扩展”图标按钮**
- 在弹出的抽屉中：
   - 找到 **`LLM (Large Language Model)`** 部分
   - 点击旁边的 **“工具”图标按钮**
- 在下拉菜单中：
   - 悬停在 **`Add Tools`** 上显示二级菜单
   - 选择 **`mcp_client_python`**
- 点击 **`Save changes`**

![add mcp extension](./assets/ui-mcp-config-2.png)


##### 3. 配置 MCP 客户端
- 点击 **“设置”图标按钮**
- 在配置面板中：
   - 从 **`Extension`** 下拉菜单中选择 **`mcp_client_python`**
   - 在 URL 字段中输入：`https://api.xpack.ai/v1/mcp?apikey={YOUR_XPACK_AUTH_KEY}`
- 点击 **`Save changes`**

![add mcp extension](./assets/ui-mcp-config-3.png)

### 验证

1. **点击 `Connect` 按钮**：在 playground 中开始对话
2. **检查 `task run` 命令行**：确认打印信息显示成功检查

![add mcp extension](./assets/ui-mcp-config-4.png)


## 热门任务示例

要将您的 TEN 连接到 XPack，您需要配置一个 MCP 服务器。这允许 TEN 发现和利用通过 XPack 提供的工具。

### 泰山旅行天气查询

轻松查看旅行目的地的天气状况和日出/日落时间，帮助您规划行程。

```
我想在 2025 年 7 月 15 日去中国泰山旅行。请帮我了解那天的日出/日落时间。
```
![ask weather](./assets/xpack/demo-weather.png)


### 实时黄金价格查询

快速查看当前黄金价格并了解可能影响未来价格趋势的关键因素。

```
请查看当前黄金的实时价格，并提供可能影响其未来价格的具体因素。
```

![ask the current real-time price of gold](./assets/xpack/demo-gold-real-time.png)

### 航班信息查询

方便地搜索特定路线和时间的航班信息，帮助您规划旅行。

```
请帮我查看 2025 年 7 月 15 日从广州到北京有哪些航班。
```
![ask flight information](./assets/xpack/demo-flight-info.png)
