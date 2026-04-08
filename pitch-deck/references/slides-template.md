# Slidev Pitch Deck — Full Template

This file is the base template for `slides.md`.
Replace all `[PLACEHOLDER]` values with real content in the deck language.
Replace all `[LABEL: key]` references with the translated string from the loaded i18n file.

---

```markdown
---
theme: default
title: "[COMPANY] — [LABEL: cover] · [STAGE] [YEAR]"
info: "Investor presentation · [STAGE] · [MONTH YEAR]"
colorSchema: light
fonts:
  sans: Inter
  mono: Fira Code
drawings:
  persist: false
transition: slide-left
mdc: true
---

<!-- ============================================================
  SLIDE 1 — COVER
============================================================ -->
---
layout: cover
background: '#0f172a'
---

# [Company Name]
## [Tagline — one sentence, max 12 words]

<br>

**[Founder Name]** · [Stage] · [Month Year]

<!-- [LABEL: speakerNotes.cover] -->

---

<!-- ============================================================
  SLIDE 2 — THE PROBLEM
============================================================ -->
---
layout: default
---

# 😤 [LABEL: problem]

<v-clicks>

- **[Target group]** struggle with **[concrete problem]**
- Today, they resort to [painful workaround]
- Result: [quantified cost / time lost / frustration]

</v-clicks>

<br>

> **"[Customer quote or striking stat that illustrates the pain]"**

<!-- [LABEL: speakerNotes.problem] -->

---

<!-- ============================================================
  SLIDE 3 — THE SOLUTION
============================================================ -->
---
layout: image-right
image: https://via.placeholder.com/600x400?text=Product+Screenshot
---

# ✨ [LABEL: solution]

**[Company]** lets [target] [primary benefit] via [key mechanism].

<br>

**In one sentence:**
> [Company] = [known analogy] for [market]

<br>

- ✅ [Benefit 1]
- ✅ [Benefit 2]
- ✅ [Benefit 3]

<!-- [LABEL: speakerNotes.solution] -->

---

<!-- ============================================================
  SLIDE 4 — HOW IT WORKS
============================================================ -->
---
layout: default
---

# ⚙️ [LABEL: howItWorks]

<div class="grid grid-cols-3 gap-8 mt-8">

<div class="text-center">

**① [Step 1 label]**

[Short description — 1–2 lines]

</div>

<div class="text-center">

**② [Step 2 label]**

[Short description — 1–2 lines]

</div>

<div class="text-center">

**③ [Outcome label]**

[Short description — 1–2 lines]

</div>

</div>

<!-- [LABEL: speakerNotes.howItWorks] -->

---

<!-- ============================================================
  SLIDE 5 — BUSINESS MODEL
============================================================ -->
---
layout: two-cols
---

# 💰 [LABEL: businessModel]

**How we make money**

- Model: [SaaS / Marketplace / Usage / Freemium]
- Pricing: [[CURRENCY]X/mo per seat / X% commission / etc.]
- Recurrence: [MRR / ARR / one-shot]

<br>

**Unit Economics**
- CAC: [[CURRENCY]X]
- LTV: [[CURRENCY]X]
- LTV/CAC: [ratio]
- Payback: [X [LABEL: ui.monthsPayback]]

::right::

<br><br>

```
[LABEL: ui.keyMetrics]

Avg revenue per customer : [CURRENCY][X/yr]
Gross margin             : [X%]
Monthly churn            : [X%]
```

<!-- [LABEL: speakerNotes.businessModel] -->

---

<!-- ============================================================
  SLIDE 6 — MARKET OPPORTUNITY
============================================================ -->
---
layout: default
---

# 🌍 [LABEL: market]

<div class="grid grid-cols-3 gap-4 mt-6">

<div class="border rounded-xl p-6 text-center bg-blue-50">

### [LABEL: ui.totalAddressableMarket]
## [CURRENCY][X]B
[Market description]

*[Source]*

</div>

<div class="border rounded-xl p-6 text-center bg-blue-100">

### [LABEL: ui.serviceableAddressableMarket]
## [CURRENCY][X]B
[Segment description]

*[Geo / vertical scope]*

</div>

<div class="border rounded-xl p-6 text-center bg-blue-200">

### [LABEL: ui.serviceableObtainableMarket]
## [CURRENCY][X]M
[LABEL: ui.estimate] — 3-year target

*[Capture assumption]*

</div>

</div>

<!-- [LABEL: speakerNotes.market] -->

---

<!-- ============================================================
  SLIDE 7 — TRACTION
============================================================ -->
---
layout: default
---

# 📈 [LABEL: traction]

<div class="grid grid-cols-2 gap-8">

<div>

**[LABEL: ui.keyMetrics]**

| Metric | Value | [LABEL: ui.growth] |
|---|---|---|
| ARR / MRR | [CURRENCY][X] | +[X%] MoM |
| Active customers | [X] | +[X] this month |
| Retention | [X%] | — |
| NPS | [X] | — |

</div>

<div>

**[LABEL: ui.milestonesReached]**

- ✅ [Milestone 1 — e.g. First paying customer]
- ✅ [Milestone 2 — e.g. Key partner integration]
- ✅ [Milestone 3 — e.g. [CURRENCY]X ARR reached]
- 🔜 [LABEL: ui.nextMilestone]: [description]

</div>

</div>

<!-- [LABEL: speakerNotes.traction] -->

---

<!-- ============================================================
  SLIDE 8 — GO-TO-MARKET
============================================================ -->
---
layout: default
---

# 🚀 [LABEL: gtm]

<v-clicks>

**Primary channel:** [Outbound / Inbound / PLG / Partnerships / Direct sales]

**Why this channel:** [Data-backed or tested rationale]

**Current funnel:**
- Leads generated: [X/month]
- Conversion rate: [X%]
- Sales cycle: [X days]

**Next step:** [What the raise will fund to accelerate]

</v-clicks>

<!-- [LABEL: speakerNotes.gtm] -->

---

<!-- ============================================================
  SLIDE 9 — COMPETITIVE LANDSCAPE
============================================================ -->
---
layout: default
---

# 🥊 [LABEL: competition]

<div class="grid grid-cols-2 gap-8 mt-4">

<div>

**[LABEL: ui.currentAlternatives]**

| Competitor | Strengths | Weaknesses |
|---|---|---|
| [Competitor 1] | [+] | [−] |
| [Competitor 2] | [+] | [−] |
| Status quo | Familiar | [Core pain] |

</div>

<div>

**[LABEL: ui.ourEdge]**

- 🔑 [Differentiator 1 — tech / data / network]
- 🔑 [Differentiator 2 — experience / pricing / speed]
- 🔑 [Long-term moat]

</div>

</div>

<!-- [LABEL: speakerNotes.competition] -->

---

<!-- ============================================================
  SLIDE 10 — THE TEAM
============================================================ -->
---
layout: default
---

# 👥 [LABEL: team]

<div class="grid grid-cols-2 gap-8 mt-4">

<div class="border rounded-xl p-4">

**[Founder 1 — First Last]**
*[Role — CEO / CTO / etc.]*

- [Key experience 1 — e.g. Ex-Google, 8 years]
- [Key experience 2 — e.g. Founded and sold X]
- [Core competency]

</div>

<div class="border rounded-xl p-4">

**[Founder 2 — First Last]**
*[Role]*

- [Key experience 1]
- [Key experience 2]
- [Core competency]

</div>

</div>

<br>

**[LABEL: ui.advisors]:** [Name — role / credibility] · [Name — role]

<!-- [LABEL: speakerNotes.team] -->

---

<!-- ============================================================
  SLIDE 11 — ROADMAP
============================================================ -->
---
layout: default
---

# 🗺️ [LABEL: roadmap] — 18 months

<div class="grid grid-cols-3 gap-4 mt-6">

<div class="border-l-4 border-green-500 pl-4">

**Q[X] – Q[X+1]**
*Today*

- ✅ [Feature / milestone already shipped]
- 🔄 [In progress]

</div>

<div class="border-l-4 border-blue-500 pl-4">

**Q[X+2] – Q[X+3]**
*Post-raise*

- 🔜 [Priority 1 funded by the raise]
- 🔜 [Priority 2]
- 🔜 [Priority 3]

</div>

<div class="border-l-4 border-purple-500 pl-4">

**Q[X+4] – Q[X+6]**
*Vision*

- 🎯 [ARR / customer target]
- 🎯 [Geo / product expansion]
- 🎯 [Next fundraising milestone]

</div>

</div>

<!-- [LABEL: speakerNotes.roadmap] -->

---

<!-- ============================================================
  SLIDE 12 — THE ASK
============================================================ -->
---
layout: statement
---

# [LABEL: ask]

<br>

## 🎯 [CURRENCY][X]M — [Stage]

<br>

<div class="grid grid-cols-3 gap-8 text-left mt-8">

<div>

**[X%] — [Use 1]**
e.g. Hiring (4 roles)

</div>

<div>

**[X%] — [Use 2]**
e.g. Product & Engineering

</div>

<div>

**[X%] — [Use 3]**
e.g. Sales & Marketing

</div>

</div>

<br>

**[LABEL: ui.withThisRound]:** [Milestone 1] · [Milestone 2] · [Milestone 3]

<!-- [LABEL: speakerNotes.ask] -->

---

<!-- ============================================================
  BACKUP SLIDES — add if needed during Q&A
============================================================

Ideas for appendix slides:
- Cohort retention chart
- 3-year P&L forecast
- Technical deep-dive
- Customer case studies / testimonials
- Current cap table
- Term sheet summary (if already received)
- Detailed unit economics
============================================================ -->
```
