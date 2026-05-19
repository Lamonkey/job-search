# Resume Style Guide

This document covers the writing rules for resume content: how to write bullets, what to bold, what language to avoid, and how to structure each section.

## Bolding Rules

Bold exists for the human reader skimming the page. ATS reads plain text and doesn't care about formatting. So bold should communicate **what you accomplished and how you work** — not which tools you used.

### What to bold: outcomes, capabilities, and experience descriptions

Good bolding reads like a mini-answer to "have you done what we need?"

Examples of good bolding:
- "enabling **usage-based billing, request throttling, and metering**"
- "achieving **up to 10x throughput improvement** under high-volume workloads"
- "**shipped rapid MVPs to a test group, gathered data-driven feedback, and iterated on what resonated**"
- "**owned the full debugging loop as a co-founder**"
- "**Reduced development cycle from 1 month to 2 weeks**"

### What NOT to bold: technology names

Never bold individual tech keywords. Not **PostgreSQL**. Not **Docker Compose**. Not **Flask and React**. Not **FastAPI**. Not **RESTful API**. Not **Django**. These are context, not the point.

### What NOT to bold: JD phrases copied back verbatim

When the JD says "implementing effective security protocols" and your resume bolds "**effective security and data protection measures**," the hiring manager sees that you copied their language word-for-word. It signals gaming, not experience.

### The self-test

Read only the bolded phrases in order, ignoring everything else. If they read like a list of technologies → the bolding is wrong. If they read like sentences from the job posting → the bolding is wrong. If they read like a summary of what you accomplished and how you work → the bolding is right.

### Quantity

Aim for ~15 bolded phrases across the whole resume, 1–2 per bullet max. Never bold the same idea in the summary and again in the first bullet of a role — the reader sees the same phrase twice in the most valuable real estate.

---

## Bullet Writing

### Lead with ownership and scope, not technology

Start bullets with what you owned or did, then let the tech stack flow naturally.

Good: "Owned frontend development across a React/Electron desktop app and a Next.js/TypeScript web platform"
Bad: "Built and maintained a **scalable** desktop app (**Electron + React**)"

### Show how things work, not just what was built

Good: "Designed an evaluation framework that decomposed LLM generation into measurable constraint checks"
Bad: "Implemented an evaluation framework with constraint-based checks"

The first one tells the reader about your engineering thinking. The second just describes the feature.

### Lead bullets with outcomes

Good: "Eliminated 1-on-1 walkthroughs by building a self-service onboarding wizard"
Bad: "Built an onboarding wizard"

### Every role opens with a context-setting bullet

The first bullet under every job and project must orient the reader — what the company/product does, what your role was, what scope you owned. Hiring managers skim; without that grounding sentence, they don't know what to make of the specifics that follow.

### Vary your verbs

If "Built" appears more than twice on the whole resume, rewrite some. Use: Owned, Designed, Implemented, Translated, Optimized, Led, Identified, Monitored.

### Cut filler

Remove decorative adjectives that don't add information: "content-rich", "learning-oriented", "clean and well-structured." If a word can be removed without losing meaning, remove it.

### One idea per bullet

If a bullet runs past two lines, it's probably two bullets. Keep sentences tight.

---

## Language to Avoid

**Marketing speak**: Never use phrases like "passionate about," "proven track record," "innovative solutions," "leveraged cutting-edge technologies." Engineers don't talk like this about their work.

**Adjective stacking**: "testable, reusable, efficient, scalable, performant, reliable, secure" — pick the one or two that actually matter for this role and drop the rest.

**Table-stakes work**: Don't waste a bullet on things every engineer does — version-controlled migrations, "clean documented code," participating in Agile ceremonies, using Git. These don't differentiate the candidate.

**Cover-letter language in the resume**: "I believe my experience in X aligns with Y" or "practiced the kind of end-to-end delivery this role calls for" — the resume is about your work, not your application.

**"This role" or "this position"**: A resume should never acknowledge that it was written for a specific job. If a bullet references "this role," the hiring manager knows it was machine-generated.

---

## Summary Section

1–2 sentences. Say what the candidate does, how long they've been doing it, and what their strongest angle is for this specific role.

Never: try to mention every skill and technology. Never: use soft-skill claims ("strong problem-solving, communication, and collaboration skills"). Never: exceed 3 short sentences.

---

## Section Order

If a project directly demonstrates a key skill the JD requires that the work experience doesn't cover, put Projects before Experience. Otherwise keep Experience first.

Reorder skills categories so the most relevant ones for this role appear first.

---

## Bullet Selection Logic

For every bullet you consider including, ask: **does this directly demonstrate a skill, tool, responsibility, or quality the JD asks for?**

If the answer is no, cut it — even if it's a strong accomplishment. A lean, laser-focused resume with 5 targeted bullets per role beats a comprehensive one with 10 generic bullets.

The same filter applies to projects. If a project doesn't add a signal that the experience section doesn't already cover, cut it.

---

## Reframing (Not Fabricating)

If the user built "a data pipeline" and the JD wants "content pipelines," reframe it if the underlying work is the same. Mirror the JD's exact language when the experience genuinely matches — ATS systems match literally.

But never invent work that didn't happen. And never use hedging phrasing like "comparable to Kafka" or "Kafka-style" — either you used the tool or you didn't. Describing what you actually built is more credible than borrowing another tool's name.
