# Laminar docs capstone: site plan

**Product:** Laminar (`lmnr.ai`)
**Tagline:** Open-source observability platform purpose-built for AI agents
**Platform:** Mintlify
**Repo:** github.com/Olamideod/laminar-docs

---

## What this site is

A documentation portal for Laminar — an open-source LLM observability platform. Laminar lets developers trace LLM calls, run evaluations, annotate datasets, and monitor agents in production. The site targets developers integrating Laminar into a Node.js or Python application for the first time.

---

## Information architecture

The site is organized around what a developer needs to do, in order:

1. Understand what the product is and whether it fits their needs
2. Get set up and send their first trace
3. Build understanding through a guided tutorial
4. Accomplish specific tasks using how-to guides
5. Look up detailed reference information
6. Diagnose and fix problems

This maps directly to the Diataxis framework: Overview (orientation), Getting Started (tutorial-adjacent), Tutorial (learning), How-To (task), Reference (information), Troubleshooting (support).

---

## Page list and structure

### Page 1: Overview (landing page)
**File:** `docs/overview.mdx`
**Purpose:** Orient the reader. What is Laminar, who is it for, what can they do with it.
**Components:** Cards for key capabilities, CardGroup for entry points, one code snippet showing the one-line setup
**Diataxis type:** Orientation

### Page 2: Getting started
**File:** `docs/getting-started.mdx`
**Purpose:** Take a new user from zero to a working trace. Install, configure, first LLM call, view in dashboard.
**Components:** Steps, Tabs (Python/TypeScript), Code blocks with expected output, Note callout
**Diataxis type:** Tutorial (procedural onboarding)

### Page 3: Tutorial — Trace a multi-step LLM pipeline
**File:** `docs/guides/tutorial-trace-pipeline.mdx`
**Purpose:** Teach the user how Laminar's tracing model works by building a real pipeline with nested spans. Goes beyond hello world. Builds understanding of executors, the @observe decorator, and trace hierarchy.
**Components:** Steps, Tabs, Code blocks, Info callouts explaining the why behind each step
**Diataxis type:** Tutorial (learning-oriented)

### Page 4: How-To — Run evaluations in CI/CD
**File:** `docs/guides/how-to-cicd-evals.mdx`
**Purpose:** Task-oriented guide for teams that want to automate evaluation runs on every pull request. Assumes the reader already knows how Laminar evaluations work.
**Components:** Steps, Code blocks, Warning callout for the threshold gate pattern, Tip callout for dataset management
**Diataxis type:** How-To

### Page 5: Reference — evaluate() function
**File:** `docs/reference/evaluate.mdx`
**Purpose:** Full reference documentation for the evaluate() function. All parameters, types, Python and TypeScript examples, return behavior.
**Components:** ParamField components, Tabs, Code blocks
**Diataxis type:** Reference

### Page 6: Troubleshooting
**File:** `docs/troubleshooting.mdx`
**Purpose:** Common errors developers encounter when setting up tracing and running evaluations. Cause and fix for each.
**Components:** AccordionGroup for each error, Warning callouts for destructive actions
**Diataxis type:** Support / reference

---

## Navigation outline (`docs.json`)

```
Documentation tab
├── Getting Started
│   ├── Overview          (docs/overview)
│   └── Getting started   (docs/getting-started)
├── Guides
│   ├── Tutorial: Trace a multi-step pipeline   (docs/guides/tutorial-trace-pipeline)
│   └── How-To: Run evaluations in CI/CD        (docs/guides/how-to-cicd-evals)
├── Reference
│   └── evaluate() function                     (docs/reference/evaluate)
└── Troubleshooting                             (docs/troubleshooting)
```

---

## Consistency rules applied across all pages

- No em-dashes
- Active voice
- Sentences under 25 words
- Sentence case headings
- Second person ("you", not "the user")
- Code tabs always show Python first, TypeScript second
- Every procedural section uses Steps component
- Expected output appears after every code block that produces terminal output
- Troubleshooting uses cause-and-fix pattern, not bullet lists of tips

---

## Day 13 deliverables (submitted today)
- This site plan
- `docs/overview.mdx` (complete)
- `docs/getting-started.mdx` (complete)
- `docs.json` (navigation configured)

## Day 14 deliverables (submitted tomorrow)
- `docs/guides/tutorial-trace-pipeline.mdx`
- `docs/guides/how-to-cicd-evals.mdx`
- `docs/reference/evaluate.mdx`
- `docs/troubleshooting.mdx`
- Vale config + GitHub Actions workflow
- Full site deployed on Mintlify
