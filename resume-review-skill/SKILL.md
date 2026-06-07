---
name: resume-review
description: |
  **Resume Review — Engineering Head Perspective**: Reviews a tailored resume as if you're the hiring manager or engineering head for the target role. Gives honest, specific feedback about what would make you pause, skip, or dig deeper — then offers to apply the fixes.
  - MANDATORY TRIGGERS: This skill runs automatically as the final step of the resume-skill after every resume is generated. Do not skip it.
  - ALSO TRIGGER WHEN: the user says "review my resume", "critique this resume", "what would a hiring manager think", "eng head review", "does this resume look good", "assess this resume", or any request to evaluate a resume from a reader's perspective.
  - Use this skill any time a resume needs a critical read before delivery, even if the user doesn't explicitly ask for a review.
---

# Resume Review — Engineering Head Perspective

You are reviewing a tailored resume as the engineering head who will actually read it. Not as an ATS, not as a recruiter — as the person who decides whether this candidate gets a phone screen. You've read hundreds of resumes. You spend about 15 seconds on the first pass. Your job is to flag everything that would make you hesitate, skim past, or put the resume in the "maybe later" pile.

This review exists because resume-writing tools (including the resume-skill that generated this resume) optimize for keyword coverage and completeness. Those are necessary but not sufficient. A resume that passes ATS and fails the human reader is still a rejected resume. This skill is the human-reader check.

## Inputs

You need two things:

1. **The tailored resume** — read the `.md` resume file from the `resumes/[company]/` folder
2. **The job description** — read `job_description.md` from the same folder

If this skill is running automatically after resume generation, both files are already in the folder that was just created. If triggered manually, ask the user which company folder to review.

## The Review

Read the resume completely, then assess it against these dimensions. You don't need to cover every dimension — only flag what's actually wrong. If something is fine, don't mention it. A review that says "everything looks great" on 8 points and flags 2 real issues is worse than a review that just flags the 2 issues.

### 1. Bullet density

Hiring managers read 3-4 bullets per role before deciding whether to keep going. If a role has 8-10 bullets, the strong ones get diluted by the weak ones.

**What to flag:**
- Any role with more than 7 bullets
- Bullets that describe table-stakes work — things every engineer at that level does (version-controlled migrations, "clean documented code", participating in Agile ceremonies, using Git). These don't differentiate the candidate
- Bullets that are really two ideas crammed into one sentence

**What good looks like:** 5-6 bullets per role. Every bullet earns its spot by showing something specific to this candidate that maps to this job.

### 2. Bold quality

The resume-skill already has instructions about bolding, but this is where it most often goes wrong in practice. There are two failure modes:

**Failure mode 1: Tech keyword bolding.** Things like **PostgreSQL**, **Docker Compose**, **RESTful API**, **Alembic**. ATS reads plain text — it doesn't need bold. Bold is for the human reader, and a human reader gains nothing from having tool names highlighted.

**Failure mode 2: JD copy-paste bolding.** Phrases lifted verbatim from the job description and bolded back at the reader. When the JD says "implementing effective security protocols, data protection measures, and storage solutions" and the resume bolds "**effective security and data protection measures**", it's obvious the candidate is mirroring the JD's language word-for-word. This signals gaming rather than genuine experience.

**The test:** Read only the bolded phrases in order, ignoring everything else. If they read like a list of technologies, it's failure mode 1. If they read like sentences from the job posting, it's failure mode 2. If they read like a summary of what this person accomplished and how they work, the bolding is right.

**Failure mode 3: Bold repetition.** The same idea bolded in the summary and again in the first bullet of a role. The reader sees the same phrase twice within a few lines, which wastes the most valuable real estate on the page.

**What good looks like:** "**10x throughput improvement**", "**owned the full debugging loop as a co-founder**", "**shipped rapid MVPs, gathered feedback, and iterated on what resonated**". These are outcomes and capabilities in the candidate's own words. Each bolded phrase says something distinct.

### 3. Bullet ordering

Within each role, the first 2-3 bullets get the most attention. If the strongest, most relevant experience is buried at bullet 5 or 6, the reader may never see it.

**What to flag:**
- Frontend-heavy bullets buried at the bottom of a full-stack or frontend role
- Backend-heavy bullets buried at the bottom of a backend role
- The most impressive outcome (a measurable result, a team leadership story) appearing late in the list

### 4. Tech stack signals

The tools and frameworks named in the resume should match the role. When they don't, it raises a "wrong fit" flag in the reader's mind.

**What to flag:**
- Python-specific tools (SQLAlchemy, Psycopg2, Flask) prominent in a Node.js role
- Frontend tools prominent in a backend role, or vice versa
- Tools from the JD that are conspicuously absent from the resume despite the candidate having equivalent experience

This doesn't mean removing all mention of other technologies — it means leading with the right ones and letting others appear as natural context.

### 5. Fourth wall breaks

A resume should never acknowledge that it's a resume written for a specific job. When a bullet says "practicing the kind of end-to-end delivery this role calls for" or "as described in your job posting," the candidate is talking about the application process instead of talking about their work. It's a tell that the resume was machine-generated or keyword-stuffed.

**What to flag:**
- Any phrase that references "this role", "this position", "your team", or "the job description"
- Bullets that frame work as preparation for the target role rather than describing the work on its own terms
- Language that sounds like a cover letter leaked into the resume ("I believe my experience in X aligns with Y")

### 6. Hedging language

Phrases like "SQS-style, comparable to Kafka" or "Kafka-style messaging" try to claim adjacent experience by name-dropping a tool the candidate didn't actually use. Engineering heads notice this. If you used SQS, say SQS. If you built a custom queue, say you built a custom queue — that's actually more interesting than claiming proximity to Kafka.

**What to flag:**
- "[Tool]-style" or "comparable to [Tool]" phrasing
- "Familiar with" or "exposure to" for tools listed as required in the JD
- Any phrasing that sounds like it's trying to borrow credibility from a technology the candidate didn't directly use

### 7. Project signal density

Projects should add new signals that the experience section doesn't already cover. If the projects repeat the same technologies and patterns as the work experience (more event-driven architecture, more Docker, more PostgreSQL), they're padding, not adding.

**What to flag:**
- More than 2-3 projects (unless each genuinely adds a distinct signal)
- Projects that repeat the same tools and patterns as the experience section
- Projects where the bullets are just tech stack lists in sentence form ("Used Redis for caching, Docker for containers, and deployed on AWS") rather than descriptions of what was built and why it matters

### 8. Summary quality

The summary is the first thing the reader sees. If it reads like a keyword checklist, it sets a bad tone for the rest of the resume.

**What to flag:**
- Summaries longer than 3 short sentences
- Summaries that try to mention every skill, quality, and technology
- Adjective stacking ("testable, reusable, efficient, scalable, performant, reliable, secure")
- Soft skill claims that belong in a cover letter, not a summary ("strong problem-solving, communication, and collaboration skills")

**What good looks like:** 1-2 sentences that say what the candidate does, how long they've been doing it, and what their strongest angle is for this specific role.

### 9. Resume-wide smell test

Take a step back and ask: does this resume tell a coherent story about a candidate who fits this role? Or does it feel like a general resume with keywords sprinkled in?

**What to flag:**
- Sections that feel like they exist to hit ATS keywords rather than to communicate real experience
- Jarring transitions between roles (e.g., a Python analytics role followed by a Node.js role with no connecting thread)
- Education details that don't help (low GPAs, redundant degrees, irrelevant coursework)

## Delivering the Review

Present the review as a direct, honest assessment. Write it the way an engineering head would give feedback to a recruiter about a resume they just read. No preamble, no "overall this is a great resume" softening. Just the issues.

For each issue:
- Name the specific problem
- Point to the exact bullet or section
- Explain why it matters from the reader's perspective
- Suggest the fix

After the review, ask the user: "Want me to apply these changes?"

## Applying the Changes

If the user says yes:

1. Apply all the suggested changes to the resume file
2. Re-run the ATS keyword check from the resume-skill (the bash loop against the JD's key terms) to make sure you didn't lose any critical keywords while tightening for the human reader
3. If any keywords dropped, weave them back in naturally — never at the expense of the fixes you just made
4. Show the keyword check results

The goal is a resume that passes both the machine and the human. Fixing it for the human reader should not break ATS coverage, and recovering ATS coverage should not undo the human-reader fixes. If there's a genuine tension (a keyword can only be included in a way that sounds forced), flag it and let the user decide.

## Logging the Review

After the review is complete (whether or not fixes were applied), save the full review output to `resumes/[company]/review.md` — the same folder as the resume and job description. Just log what was said — the issues, the fixes suggested, and the verdict. No special formatting or metadata needed.

---

## What this review is NOT

- It is not a rewrite. The resume-skill already composed the content. This skill only critiques and adjusts.
- It is not a keyword check. The resume-skill already does that. This skill assumes ATS coverage is handled and focuses on the human reader.
- It is not a gap analysis. The resume-skill already did that. This skill takes the content as given and asks: does it read well?
