# CLAUDE.md — chief-portfolio

**Version:** 1.0
**Last reviewed:** 2026-02-22
**Owner:** Tim Brenneman
**Status:** Active

---

## 1. What This Project Is

**One sentence:** Portfolio management overlay for Chief brain-state — tracks project health scores, maturity levels, and cross-project insights.

**Why it exists:** Without portfolio-level visibility, each project is a silo. This project gives the planning layer a way to compare health, spot gaps, and prioritize across all active work.

**What success looks like:** Tim can ask "which project needs attention?" and get a data-backed answer.

**What failure looks like:** Stale dashboards that don't reflect reality.

---

## 2. Context Files

| File | What It Contains | When to Read |
|------|-----------------|-------------|
| `README.md` | Project overview | Start of session |
| `docs/` | Architecture and design docs | Before making changes |

---

## 3–10. [Placeholder Sections]

_These sections will be filled in as the project matures. See the dforge CLAUDE.md template for the full structure._

---

## 11. Chief Hub Protocol

This project reports into Chief — a git-backed brain-state system that gives the planning layer (Claude.ai) visibility into what's happening across all projects.

### Chief Project Path

```
chief-brain-state/projects/chief-portfolio/
├── STATUS.md              ← project state (synced at session close + nightly)
├── CLAUDE.md.current      ← latest working CLAUDE.md (nightly sync)
├── scenarios-pending-review.md  ← CC-suggested scenarios awaiting planning review
├── qa-results/            ← QA scripts and results from RELAY sessions
└── specs/                 ← specs that affect planning decisions
```

**Project slug in Chief:** `chief-portfolio` → maps to `projects/chief-portfolio/` in chief-brain-state

### What Gets Pushed to Chief

**At session close (CHECKCHAT step 4 — SHIP):**
- STATUS.md updates (via `chief_write_file`)
- New scenarios from `scenarios-pending-review.md` (via `chief_write_file`)
- Task/goal updates (via `chief_add_task`, `chief_complete_task`, `chief_add_goal`)
- Session notes (via `chief_add_note`)

### Required Project Artifacts

| Artifact | Purpose | Status |
|----------|---------|--------|
| `qa-drop/` | Directory for RELAY QA script output | ✅ created |
| `qa-results/` | Directory for completed/reviewed QA scripts | ✅ created |
| `scenarios-pending-review.md` | CC appends suggested scenarios here | ✅ created |

---

## 12. Session Protocols

This project participates in Tim's standard session protocols. These are defined in `~/.claude/CLAUDE.md` (the global file) and activated per-project by the markers below.

### Protocol Markers

**RELAY** — QA loop. After building, CC runs QA scripts from `qa-results/` using browser tools. Loops until all tests PASS or are marked BLOCKED. New QA scripts go to `qa-drop/`.

**CHECKCHAT** — Session close protocol. Six steps: VERIFY (tests pass), DOCUMENT (update STATUS/CHANGELOG), CAPTURE (append scenarios), SHIP (push to Chief), PREP NEXT (surface next work items), BLOCKED ITEMS REPORT.

**Black Box Session Protocol** — Full session lifecycle: READ → BUILD → TEST → SCENARIOS → QA (RELAY) → CHECKCHAT.

> See `~/.claude/CLAUDE.md` for the full protocol definitions. This section activates them.

## RELAY: active
## CHECKCHAT: active
