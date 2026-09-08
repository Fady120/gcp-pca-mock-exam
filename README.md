# GCP Professional Cloud Architect — Mock Exam

A self-contained, offline practice exam for the **current** Google Cloud Professional
Cloud Architect certification. No backend, no API keys, no accounts. Open it and go.

## Run it

```bash
cd pca-mock-exam
python3 -m http.server 8080
```

Then open <http://localhost:8080>.

`npx serve .` or the VS Code Live Server extension work equally well. It must be served
over HTTP — opening `index.html` directly from disk will not work, because browsers
block `fetch()` on `file://` URLs.

## What's in it

**92 questions**, all written for this simulator:

| | Count |
|---|---|
| Standalone questions (weighted across the six domains) | 60 |
| Case-study questions (8 per case study × 4) | 32 |
| Multiple-select questions | 11 |

Domain weighting follows the official exam guide exactly:

| Domain | Weight | Questions |
|---|---|---|
| 1. Designing and planning a cloud solution architecture | 25% | 15 |
| 2. Managing and provisioning cloud solution infrastructure | 17.5% | 11 |
| 3. Designing for security and compliance | 17.5% | 11 |
| 4. Analyzing and optimizing technical and business processes | 15% | 9 |
| 5. Managing implementation | 12.5% | 7 |
| 6. Ensuring solution and operations excellence | 12.5% | 7 |

## Modes

- **Full exam** — 60 questions, 120 minutes, 2 randomly chosen case studies,
  15 case-linked questions (25%), 45 standalone questions drawn by domain weighting.
  This matches the real exam format: 50–60 questions in 2 hours, 2 case studies,
  case questions worth 20–30%.
- **Quick drill** — 25 questions, 50 minutes, one case study.
- **Case study drills** — all 8 questions for one case study.
- **Domain drills** — every question in a single domain.

## Features

- Split-screen case study panel, as in the real exam
- Countdown timer with auto-submit on expiry
- Question navigator with answered/flagged state; flag questions for review
- Keyboard shortcuts: `←` `→` navigate, `1`–`6` select an option, `f` flag
- Per-domain scorecard so you can see *which* domain to revise
- Full review mode with an explanation for the correct answer **and** a specific
  reason each distractor fails
- Progress is saved in the browser, so you can close the tab and resume
- Attempt history; light and dark themes

**Options are reshuffled on every attempt.** Answer position is never stable, so
retaking the exam tests the reasoning rather than a memorised letter.

## Two honest caveats

**The passing score.** Google does not publish a cut score for this exam. The 70%
guideline in the results screen is a widely repeated community estimate, not an
official figure. Treat it as a study target, not a prediction.

**The case studies.** The four scenarios here — Altostrat Media, Cymbal Retail,
EHR Healthcare, KnightMotives Automotive — are *original practice adaptations*. They
mirror the industries, technical environments and constraints of the case studies
named in the official exam guide, so the architectural reasoning transfers directly,
but the wording is mine, not Google's. **Read the official case studies too** — they
are linked from the exam guide, and you will see the real text on exam day.

Nothing in this repository is derived from exam dumps. No real exam questions are
reproduced.

## Verify the current exam guide before you sit

Google revised this exam in October 2025 and has since re-branded parts of it. As of
the build date, the official guide:

- names the four case studies above (Mountkirk Games, TerramEarth, Dress4Win and
  Helicopter Racing League are **gone** — most material online is still out of date)
- adds sections 2.4 and 2.5 covering end-to-end ML workflows and prebuilt AI APIs
- refers to the ML platform as the **Gemini Enterprise Agent Platform** and its
  pipelines as **Agent Platform Pipelines** (the underlying product is Vertex AI —
  questions here use the Vertex AI product names and flag the newer terminology)
- makes the **Well-Architected Framework** required knowledge, with section 6.1 built
  around the operational excellence pillar
- adds **Securing AI** to section 3.1, including Model Armor and Sensitive Data Protection
- names **Chrome Enterprise Premium**, **AI Hypercomputer**, **NotebookLM**,
  **Model Garden** and **Gemini Cloud Assist**

Re-read the guide before your exam date:
<https://cloud.google.com/learn/certification/guides/professional-cloud-architect>

## Files

```
index.html                 the entire application
data/questions.json        92 questions with explanations
data/case-studies.json     the four case study scenarios
```

Questions live in plain JSON — add your own by appending to `core` (needs `domain`)
or `cases` (needs `case` matching a case study `id`).
