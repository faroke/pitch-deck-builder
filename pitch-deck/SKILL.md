---
name: pitch-deck
description: >
  Create professional pitch decks for fundraising (pre-seed, seed, Series A and beyond).
  Use this skill whenever the user wants to create a pitch deck, investor presentation,
  fundraising slides, or any slide deck for a startup or business.
  Triggers on: "pitch deck", "investor deck", "fundraising slides", "levée de fonds",
  "deck investisseur", "Investorenpräsentation", "presentación inversores", or any
  similar phrasing in any language. Always use this skill even for quick or partial
  decks — it handles everything from a single slide to a full 15-slide presentation
  with live preview and PPTX export. Supports full i18n: the deck language is
  independent of the conversation language.
version: 1.0.0
license: MIT
authors:
  - name: Your Name
    url: https://github.com/yourusername
tags:
  - pitch
  - fundraising
  - slides
  - startup
  - i18n
  - slidev
  - pptx
---

# Pitch Deck Skill

Creates investor pitch decks using **Slidev** (Markdown + live dev server) with **Marp CLI** for PPTX export. Fully i18n-aware: conversation language and deck language are independent.

---

## Step 0 — i18n: Language detection & storage

**Always do this first.**

Detect the conversation language from the user's messages. Ask:

> *"What language should the pitch deck be in? (slides, labels, and speaker notes)"*

Offer at minimum: English, French, German, Spanish, "other (specify)".

If the user already mentioned a language preference, skip the question and use it.

### Store in `pitch.config.json`

```json
{
  "deckLang": "en",
  "companySlug": "acme",
  "stage": "seed",
  "createdAt": "2025-01-01"
}
```

**Supported codes:** `en` · `fr` · `de` · `es` · `pt` · `it` · `nl` · `zh` · `ja` · `ko` · `ar`

Load labels from `references/i18n/<lang>.json`. If missing, fall back to Step 0b.

### Apply the language throughout

All slide copy (titles, body, speaker notes, UI labels, number formats) must be in the **deck language** — never the conversation language.

---

## Step 0b — Fallback for unsupported languages

If `references/i18n/<lang>.json` doesn't exist, generate a label object inline from your knowledge. Example for Japanese:

```json
{
  "cover": "表紙", "problem": "課題", "solution": "ソリューション",
  "howItWorks": "仕組み", "businessModel": "ビジネスモデル",
  "market": "市場規模", "traction": "トラクション", "gtm": "GTM戦略",
  "competition": "競合", "team": "チーム", "roadmap": "ロードマップ",
  "ask": "調達概要", "appendix": "補足資料"
}
```

---

## Step 1 — Gather context

Ask only for what's missing:

| Field | Example |
|---|---|
| Company name + tagline | "Acme — the Stripe for payroll" |
| Problem | Pain point, who suffers, how big |
| Solution | Product pitch, demo available? |
| Business model | SaaS, marketplace, freemium, pricing |
| Traction | ARR, MRR, users, growth rate |
| Market size | TAM / SAM / SOM with sources |
| Competition | 2–3 alternatives + your edge |
| Team | Founders + key hires |
| Ask | Amount, valuation, use of funds |
| Stage | pre-seed / seed / Series A |
| Currency | USD / EUR / GBP (infer if not stated) |

---

## Step 2 — Project setup

```bash
mkdir -p /home/claude/<slug>-pitch/public
cd /home/claude/<slug>-pitch
npm init -y
npm install @slidev/cli @slidev/theme-default --save-dev
```

Load the i18n label file:
```bash
cat <skill-base-dir>/references/i18n/<lang>.json
```

Read the full slide template:
```bash
cat <skill-base-dir>/references/slides-template.md
```

---

## Step 3 — Generate `slides.md`

Use `references/slides-template.md` as the structural base. Replace every `[PLACEHOLDER]` with real content in the deck language. Replace every `[LABEL: key]` with the translated string from the i18n file.

### Slidev frontmatter

```yaml
---
theme: default
title: "[Company] — Investor Deck · [Stage] [Year]"
colorSchema: light
fonts:
  sans: Inter
transition: slide-left
mdc: true
---
```

### Available layouts
`default` · `cover` · `two-cols` · `image-right` · `image-left` · `statement` · `fact` · `quote` · `section`

### Locale number formatting

| Lang | Number | Currency | Date |
|---|---|---|---|
| `en` | 1,250,000 | $1.5M | Jan 2025 |
| `fr` | 1 250 000 | 1,5 M€ | janv. 2025 |
| `de` | 1.250.000 | 1,5 Mio. € | Jan. 2025 |
| `es` | 1.250.000 | 1,5 M€ | ene. 2025 |
| `zh`/`ja` | 億/万 units | ¥1.5億 | 2025年1月 |

---

## Step 4 — Standard 12-slide deck

| # | i18n key | English default |
|---|---|---|
| 1 | `cover` | Company name + tagline |
| 2 | `problem` | The Problem |
| 3 | `solution` | The Solution |
| 4 | `howItWorks` | How It Works |
| 5 | `businessModel` | Business Model |
| 6 | `market` | Market Opportunity |
| 7 | `traction` | Traction |
| 8 | `gtm` | Go-to-Market |
| 9 | `competition` | Competitive Landscape |
| 10 | `team` | The Team |
| 11 | `roadmap` | Roadmap |
| 12 | `ask` | The Ask |

Design rules: one idea per slide · ≤30 words body · `layout: fact` for big numbers · speaker notes in deck language inside `<!-- ... -->`.

---

## Step 5 — Launch the dev server

```bash
cd /home/claude/<slug>-pitch
npx slidev slides.md --open
```

Tell the user:
> "Live at **http://localhost:3030** — hot-reloads on save. Presenter mode at **http://localhost:3030/presenter**."

---

## Step 6 — PPTX export (via Marp)

Generate `marp-export.md` with the same content in Marp format:

```markdown
---
marp: true
theme: default
lang: [deckLang]
style: |
  section { font-family: 'Inter', sans-serif; background: #fff; }
  h1 { color: #1a1a2e; }
---
```

Export:
```bash
npx @marp-team/marp-cli marp-export.md --pptx -o <company>-pitch.pptx
# or PDF:
npx @marp-team/marp-cli marp-export.md --pdf -o <company>-pitch.pdf
cp <company>-pitch.pptx /mnt/user-data/outputs/
```

Then call `present_files`.

---

## Step 7 — Editing

- Identify slide by `---` separator in `slides.md`
- Use `str_replace` on that slide only — dev server auto-reloads
- Language change mid-session: update `pitch.config.json`, reload i18n, re-render all slides

---

## Quality checklist

- [ ] All copy in **deck language** (not conversation language)
- [ ] Numbers use correct locale format
- [ ] ≤40 words body text per slide
- [ ] Speaker notes on: problem, traction, ask (minimum)
- [ ] Figures sourced or labeled "estimate"
- [ ] The Ask: amount + use of funds + milestones unlocked
- [ ] PPTX/PDF generated and shared via `present_files`

---

## Troubleshooting

| Issue | Fix |
|---|---|
| Port 3030 busy | `npx slidev slides.md --port 3031` |
| PPTX images missing | Move to `public/` or embed base64 |
| Marp not found | `npm i -g @marp-team/marp-cli` |
| Slidev export crash | Use Marp for all exports |
| RTL language (ar, he) | Add `dir: rtl` to Marp frontmatter |
