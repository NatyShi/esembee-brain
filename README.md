# esembee-brain
> An AI multi-agent team that runs a solopreneur's business 24/7. Built with [Hermes](https://github.com/NousResearch/hermes-agent), from LATAM. Content, strategy, operations. No funding required to start.

## The Problem

Building a startup from Latin America means fighting three battles at once:

- **Funding is scarce**: only 2% of VC capital goes to women-led companies in LATAM
- **Hiring is expensive**: one employee costs more than monthly revenue for most solopreneurs
- **Doing everything yourself** kills your time, your health, and your business

## The Solution

**esembee gBrain** is an orchestrator that routes tasks to specialist AI agents. Not a chatbot. Not a prompt library. A team.

```
         YOU (Founder)
              ↓
      esembee gBrain Orchestrator
      ┌────────┼────────┐
      ↓        ↓        ↓
  Content    PM       Ops
  Creator   Expert   Expert
      ↓        ↓        ↓
  NatyShi/esembee/IPY   esembee/IPY   NatyShi/esembee
```

Each agent has one job:
- **Content Creator**: turns topics into publishable content across 3 brands (NatyShi, esembee, IPYNow)
- **PM Expert**: structures decisions, strategy, and project documentation
- **Ops Expert**: runs kanban boards, daily briefings, metrics and efficiency research

## How It Works

| Component | What it does |
|-----------|-------------|
| **Hermes Agent** | Orchestrator + specialist agents with persistent memory |
| **Obsidian** | Knowledge base with connected ideas (graph view) |
| **Kanban Board** | Visual task management (Obsidian plugin) |
| **Telegram** | 24/7 assistant with morning/evening briefings, Naty´s 24/7 assistant |
| **VM (Linux)** | Runs 24/7 cron jobs for automation, acts as a backup to synced with Github repo |
| **Windows** | Primary workspace, syncs with VM via Git |

## Real Results

- **3 brands** running simultaneously: [NatyShi](https://x.com/NatyShi_) (personal), [esembee](https://esembee.com) (B2B), [IPY Now](https://esembee.com/ipy-now) (product)
- **1 product** with WhatsApp integration: Lunadei/ConsorcioBoard (building management system for maintenance claims and traceability)
- **11 content pieces** generated per trigger across all brands
- **Quality gates** (SDD + eval criteria) ensure every output meets brand standards

## Tech Stack

- [Hermes Agent](https://github.com/NousResearch/hermes-agent) - AI orchestrator
- [Obsidian](https://obsidian.md) - Knowledge management + Kanban (efficiency tools)
- [Telegram Bot](https://core.telegram.org/bots) - 24/7 communication
- Linux VM + Windows - Dual-machine sync (via Git)
- [Kapso](https://app.kapso.ai) - Whatsapp message channel for Lunadei app (neighbours chat for claims creation and follow up platform)
- [Vercel](https://vercel.com) - Lunadei app dashboard for building managers prioritization and claim delegation

## Quick Start

```bash
# Clone the repo
git clone https://github.com/NatyShi/esembee-brain.git

# The skills/ directory contains the agent definitions
# The docs/ directory contains brand context and architecture

# To run gBrain, you need:
# 1. Hermes Agent installed (https://hermes-agent.nousresearch.com)
# 2. Obsidian with Kanban plugin
# 3. A Telegram bot token
```

## Architecture

See [ARCHITECTURE.md](ARCHITECTURE.md) for the detailed system design.

## Screenshots

| Kanban Board | Morning Briefing | Content Generation |
|---|---|---|
| ![Kanban](screenshots/kanban-board.png) | ![Briefing](screenshots/morning-briefing.png) | ![Content](screenshots/content-generation.png) |

## Built By

**NatyShi** - Solopreneur, product strategist, building from LATAM.

This system replaced 6 months of manual work in 2 weeks. The time saved goes to what matters: talking to real users, understanding their problems, and building solutions that actually work.

## License

No License

---

*Built with Hermes Agent × NVIDIA × Stripe — Hermes Agent Accelerated Business Hackathon 2026*
