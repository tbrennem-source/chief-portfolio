# Chief - AI Chief of Staff

**Intelligent thought capture and strategic planning powered by Claude AI**

Chief is a personal AI assistant that captures thoughts via Telegram (text & voice), classifies them using Claude, stores them in DuckDB, and delivers a prioritized daily "Happy List" to keep you focused.

## What It Does

- **Capture anything** - Send text or voice messages via Telegram. Chief classifies them automatically (task, idea, person, project).
- **Smart classification** - Claude AI categorizes, prioritizes (P0-P3), and extracts structured data from natural language.
- **Daily Happy List** - Every morning at 6am, get a prioritized rundown of what matters today.
- **Google Calendar sync** - Tasks with dates automatically create calendar events.
- **Query on demand** - Ask for your tasks, ideas, or happy list anytime with simple commands.

## Architecture

```
Telegram Bot (input)
    |
    v
Claude AI (classification + extraction)
    |
    v
DuckDB (structured storage)
    |
    v
Happy List / Calendar / Queries (output)
```

**Stack:** Python 3.11 | Claude API | python-telegram-bot | DuckDB | Google Calendar API | Railway (hosting)

## Commands

| Command | What it does |
|---------|-------------|
| `..happy` | Get your prioritized Happy List |
| `..tasks` | See active tasks by priority |
| `..ideas` | Browse recent ideas |
| `..help` | Show available commands |

All commands also work with `/slash` syntax (`/happy`, `/tasks`, etc.)

## Key Features

### Thought Classification
Every message is analyzed by Claude and categorized:
- **TASK** - Actionable items with priority and optional due dates
- **IDEA** - Creative thoughts and concepts for later exploration
- **PERSON** - People mentions with relationship context
- **PROJECT** - Project references with status tracking

### Happy List
A daily prioritized digest:
- P0 (Must Do) - Urgent items
- P1 (High Impact) - Important but not urgent
- P2 (If Time) - Nice to have
- Calendar events for the day

### Three-Way Coordination Protocol
Chief uses a novel coordination system between:
- **Claude Web (CW)** - Strategic planning and architecture decisions
- **Cowork Mode** - Hands-on execution and feature building
- **Claude Code (CC)** - Terminal operations, git, and deployment

Coordination files (`STATUS.md`, `STRATEGY_LOG.md`) enable seamless handoffs between AI sessions.

## Project Status

**Phase:** Foundation (Phase 1) - Functionally Complete

- [x] Telegram bot receiving text & voice
- [x] Claude AI classification
- [x] DuckDB storage with auto-incrementing IDs
- [x] Railway cloud deployment (24/7)
- [x] Google Calendar integration
- [x] Happy List generation & scheduling
- [x] Interactive commands (`/happy`, `/tasks`, `/ideas`)
- [x] Mobile-friendly `..dot` command shortcuts
- [ ] MCP integration for cross-tool access
- [ ] Portfolio documentation & diagrams

## Setup

See [docs/SETUP.md](docs/SETUP.md) for installation and configuration instructions.

## License

Private project - All rights reserved.

---

*Built with Claude AI as a demonstration of AI-augmented personal knowledge management.*
