---
name: gap-filling
description: >
  Designs buildable projects to fill skill gaps identified during resume generation. Use this skill when the resume pipeline (Step 4 Phase 2) identifies required skills the user doesn't have. It designs realistic, weekend-sized projects that demonstrate the missing skill in an industry-relevant context, writes them to personal-infos/ as "In Progress", and logs the tech pairings used for future refinement. Trigger when: "fill my gaps", "design a project for [skill]", "I need a project that shows [tool]", or automatically during resume generation when the user answers "no" to a gap question.
---

# Gap-Filling Skill

You design buildable projects that fill skill gaps for a specific job application. When the resume skill identifies required tools or skills the user doesn't have, you create realistic projects that demonstrate those skills in an industry-relevant context.

Every project you design gets written to `personal-infos/` as "In Progress" — available for this resume and all future ones.

---

## Inputs

You receive:
1. **The gaps** — a list of tools/skills the user confirmed they don't have
2. **The JD context** — the role, company, and domain so projects feel relevant
3. **The user's existing stack** — from personal-infos, so projects extend naturally from what they already know

---

## Step 1: Group gaps into projects

Don't create one project per gap — that's resume clutter. Instead, group gaps that naturally belong together into coherent projects. A good project covers 2–4 gaps.

The key constraint: **every technology pairing must be architecturally honest.** Technologies in the same project should be ones you'd actually see together in a real codebase.

### How to decide what pairs together

Use your own judgment as an experienced engineer. Ask yourself: "Would a senior engineer at a real company choose these tools together for this problem?" If the answer is no, split them.

Some principles to guide you:

**Frontend + backend pairings should share ecosystems.** Angular pairs with NestJS or .NET, not with Go or Flask. React pairs with Node/Express or Next.js. Vue pairs with Nuxt or Node. Cross-ecosystem pairings (Go backend + Angular frontend) happen in the real world but look forced on a junior resume.

**Infrastructure tools pair with anything.** Docker, AWS services, CI/CD, Terraform — these are layer concerns, not framework concerns. They pair naturally with any stack.

**Databases pair based on the problem, not the language.** PostgreSQL goes with everything. Redis pairs with anything that needs caching. MongoDB pairs with Node-heavy stacks more naturally but isn't wrong elsewhere.

**AI/ML tools pair with Python or TypeScript.** LLM APIs (Claude, OpenAI) work from any language but the ecosystem (LangChain, embeddings libraries, vector DBs) is richest in Python and TypeScript.

**Don't force a pairing just to cover more gaps.** Two focused projects are better than one Frankenstein project. If Go and Angular are both gaps, that's two projects — a Go microservice and an Angular dashboard — not one project with both.

### Pairing feedback log

After designing projects, check `gap-filling-skill/pairing-feedback.md` for any past feedback on pairings. If the user previously rejected a pairing, don't repeat it. If they approved one, favor similar patterns.

If the file doesn't exist yet, that's fine — it will be created when the user gives their first feedback.

---

## Step 2: Design each project

For each project, define:

**What it is** — one sentence. A legal doc processor, a case management dashboard, a real-time analytics pipeline. Name it something specific, not "Go Practice Project."

**Why it exists** — how it maps to the target role's domain. If applying to a fintech company, the project should be in fintech. If applying to a legal tech company, make it legal tech. Domain relevance makes the project feel intentional rather than tutorial-driven.

**Core implementation** — 5–8 bullets describing what the user would actually build. Be specific about libraries, patterns, and architecture decisions. These bullets become the personal-infos file content, and eventually resume bullets.

**What it demonstrates** — which gaps from the JD this project covers, stated explicitly.

### Data requirements

If a project needs a dataset, it must use data that is **readily available** — not data the user has to create, generate, or manually curate. Good data sources include:

- **Public APIs** with free tiers (government data, open datasets, public REST endpoints)
- **Well-known open datasets** (Kaggle, data.gov, UCI ML Repository, public GitHub repos with sample data)
- **Freely downloadable files** (public court records, SEC filings, open-access PDFs, CSV dumps)
- **Self-generating data** (the app's own usage produces the data — e.g., a task tracker where CRUD operations create the dataset)

Never design a project that requires the user to hand-build a realistic dataset, scrape a site that blocks scraping, pay for data access, or populate dozens of records manually before the project does anything interesting. If the project needs seed data, point to a specific public source or design the project so a small, trivially-created seed (5–10 records) is enough to demonstrate the full functionality.

When writing the project file, include a **Data Source** line noting where the data comes from.

### Project sizing

Every project should be buildable in a weekend with AI coding tools (Cursor, Claude Code). That means:
- One service or application, not a distributed system
- One database, not a data warehouse
- A working prototype, not production-grade infrastructure
- Real functionality, not just scaffolding

---

## Step 3: Write to personal-infos

For each project, create a file in `personal-infos/` following the naming convention `project_[name].md`. Use the format from the personal-infos skill:

```markdown
# [Project Name] — [Short Description]

**Status:** In Progress
**Timeline:** [Current year]
**Repo:** github.com/[username]/[repo-name] (planned)
**Data Source:** [Where the data comes from — public API, open dataset, self-generated, or trivial seed]

## What It Is

[1-2 sentences — what the project does and what domain it serves]

## Why This Project

[1-2 sentences — why this project exists in the context of the user's learning goals and target role domain. Frame as "built to learn X by solving Y" — not "created for a resume."]

## Core Implementation

- [Specific implementation bullet — library, pattern, architecture decision]
- [Specific implementation bullet]
- [Specific implementation bullet]
- [5-8 bullets total]

## What This Demonstrates

- [Gap 1 from JD]: [how this project covers it]
- [Gap 2 from JD]: [how this project covers it]
```

**Important:** Write the implementation bullets as if the user has already started building — present tense or past tense, not future tense. "Built a REST API in Go using gorilla/mux" not "Will build a REST API." The resume skill needs to be able to pull from these bullets directly.

---

## Step 4: Present to the user

Show the user what you designed before moving on. For each project:
- Name and one-line description
- Tech stack
- Which gaps it covers
- Confirm this looks like something they'd actually build

If the user pushes back on a pairing or project design, adjust and log the feedback (see Step 5).

---

## Step 5: Log pairing feedback

After the user reviews the projects, log the outcome to `gap-filling-skill/pairing-feedback.md`. Append to the file (create it if it doesn't exist):

```markdown
## [Date] — [Target Company/Role]

**Gaps filled:** [list]

**Projects designed:**
- [Project 1]: [tech stack] — [accepted/rejected/modified]
- [Project 2]: [tech stack] — [accepted/rejected/modified]

**Feedback:** [What the user said, if anything. "No feedback — accepted as designed" is fine.]
```

This log accumulates over time. After enough data points, patterns will emerge (e.g., "user always rejects Go + frontend pairings", "user prefers Python for data projects") that can be codified into explicit rules.

---

## Notes

- **Never claim completed work.** Every project is "In Progress" — the user hasn't built it yet.
- **Domain relevance matters.** A generic CRUD app doesn't signal intent. A legal doc processor for a legal tech role does.
- **Extend the user's existing stack when possible.** If they know React and TypeScript, a new project should add NestJS or Prisma on top — not switch to an entirely unfamiliar ecosystem unless that's the gap itself.
- **The resume skill calls this skill, but it also works standalone.** A user might say "design me a project that shows I can use Kubernetes" outside of resume generation.
- **Don't over-engineer.** The user needs to actually build this. Complex distributed systems that look impressive on paper but take a month to build defeat the purpose.
