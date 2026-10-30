# 童俊杰 · Qin

**AI 应用工程师 / Agent 工程师** —— 做端到端交付：界面、API、模型接入三层都自己打通。

深圳 · 正在找 AI 应用 / Agent 方向的机会 · [itong.asia](https://itong.asia) · [简历](https://itong.asia/resume) · [开发日志](https://itong.asia/devlog)

---

## 在做什么

过去一年做完了三个能上线的 AI 系统，都是我一个人从界面写到模型接入：

| 项目 | 规模 | 状态 |
| --- | --- | --- |
| [Nexus · AI 应用开发平台](https://itong.asia/projects/ai-agent-system) | 285 个 REST 端点 / 981 次提交 | 个人项目，后被公司业务线采用 |
| [节点式 AI 创作画布](https://itong.asia/projects/creative-canvas) | 前端 6.33 万行 / 24 种节点类型 / 55 端点 | 公司项目 |
| [电商客服 RAG Agent](https://itong.asia/projects/rag-agent) | 78 端点 + 2 WebSocket / 5.34 万行 | 已上线，服务真实店铺与买家 |

**几个我自己最在意的点：**

- **Agent 用清单定义，不用代码** —— `agent.yaml` 声明工具与插件，运行时由注册表组装。这是把「第一天写的 13 个 agent 类」全撤掉换来的 —— 那批里有 6 个文件各只有 6 行，什么也没做。
- **LLM 前缀缓存 30.7% → 99%** —— 关键不是开 `cache_control`，而是让请求前缀逐字节一致。我先按 Anthropic 的做法加缓存断点，命中率反而从 96% 掉到 8%，因为断点位置把稳定前缀切碎了。
- **编辑器单文件 4,510 行 → 695 行** —— 4 步渐进式提交。但真正治住重渲染的不是拆文件，是把高频 state（视口，每 140ms 提交一次）从页面订阅里摘出去。
- **ComfyUI 不改编排改注入** —— 走 HTTP API，媒体槽用文件名字符串而不是 `LoadImage` 节点，注入只需写一个字符串，不用重建整张图。

细节都写在 [devlog](https://itong.asia/devlog) 里，按「问题 → 怎么解的 → 学到什么」记，**走错撤回的那 8 条也留着**。

---

## Tech Stack

### AI / Agent

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![LangChain](https://img.shields.io/badge/LangChain-1C3C3C?style=flat-square)
![Milvus](https://img.shields.io/badge/Milvus-00A1EA?style=flat-square)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white)
![MCP](https://img.shields.io/badge/MCP-6E56CF?style=flat-square)
![RAG](https://img.shields.io/badge/RAG-Dense%2BSparse%20%2B%20RRF%20%2B%20Rerank-orange?style=flat-square)
![Tool Calls](https://img.shields.io/badge/Tool%20Calls-ReAct%20loop-green?style=flat-square)
![SSE](https://img.shields.io/badge/SSE%20%2F%20WebSocket-streaming-blue?style=flat-square)

### 模型服务 / 媒体

![ComfyUI](https://img.shields.io/badge/ComfyUI-workflow%20orchestration-8B5CF6?style=flat-square)
![MiniMax H3](https://img.shields.io/badge/MiniMax%20H3-video%20generation-EC4899?style=flat-square)
![BGE](https://img.shields.io/badge/BGE--M3%20%2F%20Reranker-retrieval-0EA5E9?style=flat-square)
![ffmpeg](https://img.shields.io/badge/ffmpeg-007808?style=flat-square&logo=ffmpeg&logoColor=white)
![TTS](https://img.shields.io/badge/faster--whisper%20%2F%20Qwen3--TTS-speech-purple?style=flat-square)

### 前端

![Next.js](https://img.shields.io/badge/Next.js%2016-000000?style=flat-square&logo=next.js&logoColor=white)
![React](https://img.shields.io/badge/React%2019-61DAFB?style=flat-square&logo=react&logoColor=black)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![Tailwind](https://img.shields.io/badge/Tailwind%204-06B6D4?style=flat-square&logo=tailwindcss&logoColor=white)
![Zustand](https://img.shields.io/badge/Zustand-764ABC?style=flat-square)
![React Flow](https://img.shields.io/badge/React%20Flow-controlled%20mode-FF4154?style=flat-square)

### 后端 / 工程

![Node.js](https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=node.js&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![pytest](https://img.shields.io/badge/pytest-3%2C179%20cases-0A9EDC?style=flat-square&logo=pytest&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub%20Actions-CI%20matrix-2088FF?style=flat-square&logo=githubactions&logoColor=white)

### 编辑器 / 可视化

![Monaco](https://img.shields.io/badge/Monaco%20Editor-1F2937?style=flat-square)
![Tiptap](https://img.shields.io/badge/Tiptap-3EAF92?style=flat-square)
![Mermaid](https://img.shields.io/badge/Mermaid-8D4D63?style=flat-square)
![KaTeX](https://img.shields.io/badge/KaTeX-EF1A1A?style=flat-square)
![Recharts](https://img.shields.io/badge/Recharts-22B8CF?style=flat-square)

---

## 其他项目

- **[可视化工作流编排平台](https://flow.itong.asia)** —— 节点拖拽、SVG 贝塞尔连线、Kahn 拓扑排序执行引擎，已上线。
- **[Tolaria 知识库 Web 版](https://itong.asia/projects/tolaria-web)** —— 把 Tauri 桌面端 1:1 复刻到浏览器：写 `mock-tauri` 桥接层让业务组件一行不改，自研构建期 vendor 补丁机制替代 `patch-package`。855 文件 / 16.9 万行。
- **[个人站 just-me](https://github.com/osinone/just-me)** —— Next.js 16 + React 19 自建，带 devlog 系统与项目架构图。
- **Linkfans** —— 类 Linktree 的链接聚合平台，拖拽编辑、多租户 RBAC、图片优化（体积 −70%），1,065 次提交。

---

## 怎么工作

- **英文文档是第一信息源**。选型和排障基本靠读原始文档、源码和 issue，不靠二手博客。
- **用 `AGENTS.md` / `CLAUDE.md` 沉淀 AI 编码规范**，日常用 Claude Code / Opencode 做代码生成、方案规划与调试。
- **失败也留档**。devlog 里 127 条有 8 条是 `reverted` —— 走错了、撤回了、为什么撤，都写下来。

---

## Contact

- 📧 3213709735@qq.com
- 🌐 https://itong.asia
- 💻 https://github.com/osinone

<details>
<summary>GitHub Stats</summary>

<p align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=osinone&show_icons=true&theme=transparent&hide_rank=true" height="170" alt="stats" />
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=osinone&layout=compact&theme=transparent&langs_count=8" height="170" alt="languages" />
</p>

</details>
