# pitch-deck

> A skill for AI agents to create professional investor pitch decks — with live preview, i18n, and PPTX export.

[![Install with npx skills](https://img.shields.io/badge/npx%20skills-install-black?logo=npm)](https://skills.sh)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

## Install

```bash
npx skills add faroke/pitch-deck
```

Or target a specific agent:

```bash
npx skills add faroke/pitch-deck -a claude-code
npx skills add faroke/pitch-deck -a cursor
npx skills add faroke/pitch-deck -a codex
```

## What it does

This skill teaches your AI agent to create full investor pitch decks using **Slidev** (Markdown + live hot-reload server) with **Marp CLI** for native PPTX export.

**Features:**
- 🌍 **Full i18n** — deck language is independent of your conversation language. Supported out of the box: English, French, German, Spanish. Any other language is auto-translated inline.
- 📊 **12-slide standard deck** — Cover, Problem, Solution, How It Works, Business Model, Market (TAM/SAM/SOM), Traction, Go-to-Market, Competition, Team, Roadmap, The Ask
- 🖥️ **Live dev server** — `localhost:3030` with hot-reload and presenter mode
- 📥 **PPTX + PDF export** — via Marp CLI, no Playwright required
- 💬 **Speaker notes** — on every slide, in the deck language

## Usage

Just ask your agent in plain language:

```
Create a pitch deck for my SaaS startup targeting Series A investors
```

```
Make me an investor deck in French for a pre-seed raise of €500k
```

```
Build a seed-stage pitch deck for Acme, a B2B payroll automation tool
```

The agent will ask for any missing context (team, traction, market size, etc.) and generate a ready-to-present deck.

## Tech stack

| Tool | Role |
|---|---|
| [Slidev](https://sli.dev) | Markdown-based slides with live dev server |
| [Marp CLI](https://github.com/marp-team/marp-cli) | PPTX / PDF export without Playwright |

## Compatibility

This skill follows the [Agent Skills open standard](https://agentskills.io) and works with:

- ✅ Claude Code
- ✅ Cursor
- ✅ GitHub Copilot
- ✅ OpenAI Codex
- ✅ Windsurf
- ✅ Gemini CLI
- ✅ Any agent that supports `SKILL.md`

## Structure

```
pitch-deck/
├── SKILL.md                        ← Agent instructions
└── references/
    ├── slides-template.md          ← Full 12-slide Slidev template
    └── i18n/
        ├── en.json                 ← English labels + locale rules
        ├── fr.json                 ← French
        ├── de.json                 ← German
        └── es.json                 ← Spanish
```

## Adding a language

Open a PR adding `references/i18n/<lang>.json` with the same structure as `en.json`. The skill automatically picks it up — no code changes needed.

## License

MIT
