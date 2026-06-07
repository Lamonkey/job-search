# How a Hiring Manager Actually Reads a Resume

This document describes the mental model you should use when composing a resume. Every decision — which bullets to include, what to bold, how to order sections — should be filtered through this lens.

## The 15-Second Pass

A hiring manager spends about 15 seconds deciding whether to read further or move to the next resume. In those 15 seconds, they scan:

1. **The summary** — Does this person do what I need? ("Full-stack engineer" vs "data scientist" vs "DevOps engineer"). If the summary doesn't match the role shape within the first sentence, the resume goes in the "no" pile.

2. **The bolded text** — Their eye jumps to bold phrases throughout the page. This is the highlight reel. If they read only the bold text and it tells them "this person has done the kind of work I need done," they'll read the full bullets. If the bold text is just a list of technology names (PostgreSQL, Docker, React, TypeScript), it tells them nothing about what the person can actually do — and they move on.

3. **The first bullet of each role** — This is where they orient. "What company is this? What did this person own?" If the first bullet is generic ("Participated in Agile ceremonies and contributed to Git workflows"), they get no signal and start skimming.

If the 15-second pass goes well, they'll read more carefully. If it doesn't, everything else on the resume is irrelevant.

## What They're Actually Asking

The hiring manager has one question in mind: **"Has this person done the work I need done?"**

Not "does this person know the tools I use" — tools can be learned. Not "is this person impressive in general" — general impressiveness doesn't help them fill a specific role. They want evidence that the candidate has solved similar problems to the ones their team faces.

This means:
- A bullet about "building event-driven microservices for document processing" is strong signal for a role that involves document processing pipelines
- A bullet about "achieved 10x throughput improvement" is strong signal for a role that involves performance-sensitive systems
- A bullet about "wrote clean, well-documented code and participated in code reviews" is zero signal — every engineer at every company does this

## The Story Test

Good resumes tell a story that makes the hiring manager think: "I can see how this person's trajectory leads naturally to my role."

Bad resumes read like a keyword-stuffed list of technologies and generic accomplishments that could belong to anyone.

The story is: what did this person own, what problems did they solve, what was the outcome? Each role should have a clear through-line. If someone was a full-stack developer at two companies and is applying for a backend role, the resume should emphasize backend work from both roles — not dump every bullet and hope the reader picks out the relevant ones.

## Red Flags That Make Hiring Managers Hesitate

**Keyword stuffing**: When every other word is a technology name, the resume reads like it was written for a machine, not a person. The hiring manager thinks: "this person is gaming the system, not communicating their experience."

**Marketing language**: Phrases like "passionate about building scalable, efficient, high-performance systems" or "proven track record of delivering innovative solutions" are empty calories. Engineers don't talk like this about their work. When a resume sounds like a marketing brochure, the hiring manager assumes the candidate is compensating for thin experience.

**Hedging on tools**: "SQS-style, comparable to Kafka" or "Kafka-style messaging" signals the candidate didn't actually use the tool they're name-dropping. If you used SQS, say SQS. If you built a custom queue, say that — it's actually more interesting.

**Every bullet sounds the same**: When all bullets follow the pattern "Built X using Y, achieving Z," the resume becomes monotonous and the reader stops processing. Vary the structure.

**Tech keyword bolding**: Bolding **PostgreSQL**, **Docker**, **React**, **TypeScript** throughout the resume is the single most common mistake. It makes the resume look like a highlighted keyword dump. ATS reads plain text — bold is exclusively for the human reader's benefit. A hiring manager who sees bold tech keywords thinks "AI-generated resume" and their trust drops.

## What Actually Impresses

**Specificity over generality**: "Reduced API latency from 800ms to 120ms by identifying N+1 queries in the order pipeline" beats "Optimized application performance" every time.

**Ownership language**: "Owned the data modeling and API integration layer" tells the hiring manager this person drove decisions. "Contributed to the API layer" tells them the person was along for the ride.

**Outcomes that matter to the business**: "Eliminated all 1-on-1 onboarding calls" tells the hiring manager this person thinks about impact. "Built an onboarding wizard" just describes what they made.

**Context that orients the reader**: The hiring manager doesn't know your company. "Owned frontend and backend development across two products at a small startup — a desktop app (Electron + React) and a web platform (Next.js)" gives them the picture immediately. Without that context, specific bullets don't land because the reader doesn't know the scale or type of work.
