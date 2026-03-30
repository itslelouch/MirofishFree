<div align="center">

<img src="./static/image/MiroFish_logo_compressed.jpeg" alt="MiroFish Logo" width="75%"/>

<a href="https://trendshift.io/repositories/16144" target="_blank"><img src="https://trendshift.io/api/badge/repositories/16144" alt="MiroFish | Trendshift" style="width: 250px; height: 55px;" width="250" height="55"/></a>

**A Simple and Universal Swarm Intelligence Engine — Predicting Anything**

<a href="https://www.shanda.com/" target="_blank"><img src="./static/image/shanda_logo.png" alt="Shanda" height="40"/></a>

[![GitHub Stars](https://img.shields.io/github/stars/666ghj/MiroFish?style=flat-square&color=DAA520)](https://github.com/666ghj/MiroFish/stargazers)
[![GitHub Forks](https://img.shields.io/github/forks/666ghj/MiroFish?style=flat-square)](https://github.com/666ghj/MiroFish/network)
[![License: AGPL-3.0](https://img.shields.io/badge/License-AGPL--3.0-blue?style=flat-square)](https://github.com/666ghj/MiroFish/blob/main/LICENSE)
[![Ask DeepWiki](https://deepwiki.com/badge.svg)](https://deepwiki.com/666ghj/MiroFish)

[![Discord](https://img.shields.io/badge/Discord-Join-5865F2?style=flat-square&logo=discord&logoColor=white)](http://discord.gg/ePf5aPaHnA)
[![X](https://img.shields.io/badge/X-Follow-000000?style=flat-square&logo=x&logoColor=white)](https://x.com/mirofish_ai)

</div>

---

> **⚠️ This is an unofficial English-translated fork of the original [MiroFish](https://github.com/666ghj/MiroFish) project.**
> All core code, architecture, and creative work belongs to the original authors.
> This fork provides a fully English-translated codebase and updated setup instructions for running locally with the **free Longcat.chat LLM API**.

---

## 📌 What Makes This Fork Different

| Feature | Original MiroFish | This Fork |
|---|---|---|
| UI & Code Language | Chinese | **Fully English** |
| LLM API | Alibaba Qwen (paid) | **Longcat.chat (free tier available)** |
| Comments & Docs | Chinese | **English** |
| Setup Guide | Chinese README | **This English README** |

All 14 frontend Vue files, all backend Python files, API modules, configuration files, and comments have been translated from Chinese to English. The project logic and architecture are **identical** to the original.

---

## ⚡ What is MiroFish?

**MiroFish** is a next-generation AI prediction engine powered by multi-agent simulation technology.

You upload **seed materials** (news reports, policy drafts, novel chapters, financial signals) and describe your **prediction goal** in plain language. MiroFish then:

1. Extracts entities and builds a knowledge graph (backed by Zep Cloud)
2. Generates thousands of AI agents with unique personalities and long-term memory
3. Runs a **dual-platform social simulation** (Twitter + Reddit) where agents freely interact
4. Produces a detailed **prediction report** written by a ReACT-based Report Agent
5. Lets you **chat** with any agent in the simulated world

> Think of it as: *run a digital rehearsal of the future, then win real decisions.*

### Use Cases

- 📰 **Public opinion prediction** — How will the public react to a news event?
- 📜 **Policy impact simulation** — What happens if this law is passed?
- 📖 **Creative writing** — What would happen next in a story?
- 📈 **Financial signal analysis** — How would agents react to market news?

---

## 🌐 Live Demo

Try the original team's demo: [mirofish-live-demo](https://666ghj.github.io/mirofish-demo/)

---

## 📸 Screenshots

<div align="center">
<table>
<tr>
<td><img src="./static/image/Screenshot/screenshot1.png" alt="Screenshot 1" width="100%"/></td>
<td><img src="./static/image/Screenshot/screenshot2.png" alt="Screenshot 2" width="100%"/></td>
</tr>
<tr>
<td><img src="./static/image/Screenshot/screenshot3.png" alt="Screenshot 3" width="100%"/></td>
<td><img src="./static/image/Screenshot/screenshot4.png" alt="Screenshot 4" width="100%"/></td>
</tr>
<tr>
<td><img src="./static/image/Screenshot/screenshot5.png" alt="Screenshot 5" width="100%"/></td>
<td><img src="./static/image/Screenshot/screenshot6.png" alt="Screenshot 6" width="100%"/></td>
</tr>
</table>
</div>

---

## 🔄 How It Works

```
Upload seed docs  →  Knowledge Graph  →  Agent Generation  →  Simulation  →  Report + Chat
      (PDF/TXT)        (Zep Cloud)         (LLM profiles)     (OASIS)       (ReportAgent)
```

1. **Graph Building** — Extracts entities from your documents, builds a GraphRAG-style knowledge graph in Zep Cloud
2. **Environment Setup** — Generates agent personas (personality, background, platform behavior) using LLM
3. **Simulation** — Runs dual-platform (Twitter + Reddit) multi-round agent interaction via the OASIS framework
4. **Report Generation** — ReportAgent uses ReACT reasoning + retrieval tools to write a structured prediction report
5. **Deep Interaction** — Chat with any simulated agent or ask follow-up questions to the ReportAgent

---

## 🚀 Quick Start

### Prerequisites

| Tool | Version | Purpose | Check |
|------|---------|---------|-------|
| **Node.js** | 18+ | Frontend runtime | `node -v` |
| **Python** | 3.11–3.12 | Backend runtime | `python --version` |
| **uv** | Latest | Python package manager | `uv --version` |

Install `uv` if you don't have it:
```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

---

### Step 1 — Get API Keys

You need **two** API keys:

#### 1. Longcat.chat (LLM) — Free

Longcat.chat provides a free OpenAI-compatible API. This fork is pre-configured to use it.

1. Sign up at **[longcat.chat](https://longcat.chat)**
2. Get your API key from the dashboard (starts with `ak_...`)
3. Models to use: `LongCat-Flash-Chat` (main) and `LongCat-Flash-Lite` (boost/fast)

#### 2. Zep Cloud (Graph Memory) — Free Tier Available

Zep Cloud stores agent memories and the knowledge graph. The free monthly quota is enough for basic simulations.

1. Sign up at **[app.getzep.com](https://app.getzep.com/)**
2. Copy your API key from the dashboard

---

### Step 2 — Configure Environment

Clone or download this repo, then create a `.env` file in the **project root** (same folder as `package.json`):

```env
# ── LLM API (Longcat.chat — free) ──
LLM_API_KEY=ak_your_longcat_key_here
LLM_BASE_URL=https://api.longcat.chat/openai/v1
LLM_MODEL_NAME=LongCat-Flash-Chat

# ── Boost LLM (optional but recommended — faster for simple tasks) ──
LLM_BOOST_API_KEY=ak_your_longcat_key_here
LLM_BOOST_BASE_URL=https://api.longcat.chat/openai/v1
LLM_BOOST_MODEL_NAME=LongCat-Flash-Lite

# ── Zep Cloud (graph memory) ──
ZEP_API_KEY=your_zep_api_key_here
```

> **Note:** `LLM_BASE_URL` and `LLM_MODEL_NAME` already default to Longcat values in the backend config, so they are optional in `.env` — but it's good practice to set them explicitly.

---

### Step 3 — Install Dependencies

```bash
# Install everything in one command (Node + frontend + Python backend)
npm run setup:all
```

Or step by step:

```bash
# Install Node dependencies (root + frontend)
npm run setup

# Install Python dependencies (backend — creates a virtual environment automatically)
npm run setup:backend
```

---

### Step 4 — Run

```bash
npm run dev
```

This starts both the frontend and backend together.

| Service | URL |
|---------|-----|
| Frontend (Vue) | http://localhost:3000 |
| Backend API | http://localhost:5001 |

Run them separately if you prefer:

```bash
npm run backend    # Flask API server only
npm run frontend   # Vite dev server only
```

---

### Step 5 — Use the App

1. Open `http://localhost:3000`
2. Upload seed documents (PDF or plain text)
3. Type your prediction goal in natural language
4. Click **Launch Engine** — the system will build the graph and generate agents
5. Start the simulation and watch agents interact in real time
6. Generate your prediction report when the simulation finishes
7. Chat with agents or the Report Agent for deeper insights

---

## 🐳 Docker (Alternative)

```bash
# 1. Set up your .env file (same as above)
cp .env.example .env   # then edit .env

# 2. Pull and start
docker compose up -d
```

Frontend: `http://localhost:3000` | Backend: `http://localhost:5001`

---

## 💡 Tips for Getting the Best Results

- **Seed documents**: The richer your input material, the better the agents and predictions. 2,000–50,000 words is ideal.
- **Simulation rounds**: Start with 10–20 rounds to test. Full simulations can use 40–100+ rounds.
- **Agent count**: Controlled by the document's entity count. Larger graphs = more agents = longer simulation.
- **Longcat free tier**: Suitable for small-to-medium simulations. For large runs (100+ agents, 50+ rounds), monitor your quota.

---

## 🔧 Project Structure

```
MiroFish/
├── frontend/              # Vue 3 + Vite frontend
│   └── src/
│       ├── views/         # Page components (14 files — all translated)
│       ├── api/           # Backend API client modules
│       └── store/         # Reactive state stores
├── backend/               # Flask + Python backend
│   └── app/
│       ├── api/           # REST API route handlers
│       ├── services/      # Core business logic
│       │   ├── ontology_generator.py      # Entity extraction via LLM
│       │   ├── oasis_profile_generator.py # Agent persona generation
│       │   ├── simulation_runner.py       # OASIS simulation orchestration
│       │   ├── report_agent.py            # ReACT report generation
│       │   ├── zep_entity_reader.py       # Zep graph memory reader
│       │   └── zep_graph_memory_updater.py # Real-time memory updates
│       ├── models/        # Data models (Project, Task, Simulation)
│       └── utils/         # LLM client, file parser, logger
├── static/image/          # Screenshots and demo images
├── .env.example           # Template for environment variables
└── package.json           # Root scripts (dev, setup, build)
```

---

## ⚙️ Environment Variable Reference

| Variable | Required | Default | Description |
|----------|----------|---------|-------------|
| `LLM_API_KEY` | ✅ Yes | — | Your LLM API key (Longcat or any OpenAI-compatible) |
| `LLM_BASE_URL` | No | `https://api.longcat.chat/openai/v1` | LLM API endpoint |
| `LLM_MODEL_NAME` | No | `LongCat-Flash-Chat` | Main model name |
| `LLM_BOOST_API_KEY` | No | Same as `LLM_API_KEY` | Boost model key (for faster light tasks) |
| `LLM_BOOST_BASE_URL` | No | Same as `LLM_BASE_URL` | Boost model endpoint |
| `LLM_BOOST_MODEL_NAME` | No | `LongCat-Flash-Lite` | Boost model name |
| `ZEP_API_KEY` | ✅ Yes | — | Zep Cloud API key for graph memory |

---

## 🐛 Troubleshooting

**Backend fails to start with `ModuleNotFoundError`**
- Make sure you ran `npm run setup:backend` (installs Python deps via uv)
- Python version must be 3.11 or 3.12

**Frontend port 3000 in use**
- Vite will automatically try port 3001 — check the terminal output for the actual URL

**`ZEP_API_KEY not configured` error**
- Your `.env` file must be in the project root (same folder as `package.json`)

**LLM API errors / quota exceeded**
- Check your Longcat dashboard for remaining credits
- Try reducing simulation rounds or agent count

---

## 📄 Credits & Attribution

### Original Project

This project is a fully English-translated fork of **MiroFish**, created by the [MiroFish Team](https://github.com/666ghj/MiroFish) and incubated by [Shanda Group](https://www.shanda.com/).

- **Original Repository:** [https://github.com/666ghj/MiroFish](https://github.com/666ghj/MiroFish)
- **Original Authors:** 666ghj and the MiroFish Team
- **License:** [AGPL-3.0](https://github.com/666ghj/MiroFish/blob/main/LICENSE) — This fork inherits the same license

> All credit for the architecture, simulation engine, agent design, and core algorithms goes entirely to the original MiroFish team. This fork only translates the user-facing text, comments, and documentation into English.

### Simulation Engine

The multi-agent social simulation is powered by **[OASIS (Open Agent Social Interaction Simulations)](https://github.com/camel-ai/oasis)** by the CAMEL-AI team.

### Translation

Chinese → English translation of all source code, comments, LLM prompts, and UI strings was performed with the assistance of AI tooling (Claude by Anthropic) on this fork. All translation work is non-commercial and done in good faith to make the project accessible to English-speaking developers.

### What Was Translated in This Fork

- All 14 frontend Vue component files (UI text, comments, variable descriptions)
- All backend Python service files (docstrings, inline comments, log messages, LLM prompt templates)
- REST API route files and model files
- Configuration files (`pyproject.toml`, `requirements.txt`, `package.json`, `docker-compose.yml`)
- Image asset filenames (renamed from Chinese to English)
- This README

---

## 📬 Community (Original Project)

The original MiroFish team is actively recruiting. If you're interested in multi-agent simulation and LLM applications, reach out at: **mirofish@shanda.com**

---

## 📈 Star History

<a href="https://www.star-history.com/#666ghj/MiroFish&type=date&legend=top-left">
 <picture>
   <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/svg?repos=666ghj/MiroFish&type=date&theme=dark&legend=top-left" />
   <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/svg?repos=666ghj/MiroFish&type=date&legend=top-left" />
   <img alt="Star History Chart" src="https://api.star-history.com/svg?repos=666ghj/MiroFish&type=date&legend=top-left" />
 </picture>
</a>
