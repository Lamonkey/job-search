---
name: resume
description: >
  Generates a tailored resume from the user's personal-infos folder for a specific job. Use this skill any time the user provides a job description and wants a resume — whether they say "tailor my resume", "make a resume for this job", "generate my resume", "help me apply to this", "what's missing from my resume for this role", or just pastes a job description. The skill reads all experience from the personal-infos/ folder (not from any previous resume), does a gap analysis, asks targeted questions to surface hidden experience, and outputs a complete resume in the required iconify markdown template format, ready to paste into a web renderer. Always trigger this skill when a job description is involved and a resume is the desired output.
---

# Resume Skill

You generate a tailored resume for a specific job. The source of truth for the user's experience is their **personal-infos folder** — located at `personal-infos/` in the working directory. It contains files that capture all their roles, projects, and skills. You never reference or copy from a previous resume. Every resume is composed fresh from the personal-infos folder, tailored to the job at hand.

The final output is a markdown file in a specific template format that the user pastes into a web app to render as HTML. Template fidelity is non-negotiable.

---

## Step 0: Clearance screening

Before doing any work, scan the job description for security clearance requirements. Look for phrases like "TS/SCI", "Top Secret", "Secret clearance", "polygraph", "security clearance required", "must have active clearance", or "able to obtain a clearance" paired with "U.S. citizenship required."

**The user does not have a security clearance and is not eligible for one.**

If the role requires an active clearance or requires the candidate to obtain one, **stop immediately**. Tell the user the role requires a clearance they don't have and skip it. Do not proceed to gap analysis, do not write a resume. Just flag it and move on.

If the clearance is listed as "nice to have" or "preferred" but not required, note it as a gap and proceed normally.

---

## Step 1: Get the job description

The user will paste a job description or share a URL. If it's a URL, use WebFetch or the browser to retrieve it. Extract:

- Job title and company
- Core responsibilities
- Required skills, tools, and technologies
- Preferred qualifications
- Any specific keywords, methodologies, or named tools

---

## Step 2: Read the personal-infos folder

Read all files in the `personal-infos/` folder in the working directory. This is the only source you draw from — it contains the user's roles, projects, skills, and any other personal background. Read every file in the folder fully before proceeding.

If the folder is empty or missing, tell the user to add their work experience files to `personal-infos/` before continuing.

---

## Step 3: Gap analysis

Compare the job description against the master artifact. Think like three people at once:

**ATS scanner** — Which exact keywords and tool names from the JD are missing from the artifact? ATS systems match literally. "Apache Kafka" and "message queue" are not the same match.

**Hiring manager** — Does the user's experience tell a compelling story for this role? What's the strongest case? What's the weakest?

**HR screener** — Does the user meet the stated requirements? Are there gaps in years of experience, credentials, or specific tools?

Identify:
- Strong matches (lead with these)
- Critical gaps (required skills not in the artifact)
- Nice-to-have gaps (preferred skills not in the artifact)
- Language gaps (user has the experience but uses different vocabulary than the JD)

Be honest. If the role is a stretch, say so — but also explain what the strongest arguments are.

---

## Step 4: Surface hidden experience interactively

Before writing, ask targeted questions about gaps. Use `AskUserQuestion` with multiple-choice options — keep it fast and structured. Group questions by theme and run 2–3 rounds max. Focus on:

- Specific tools the JD requires that aren't in the artifact — do they have adjacent or transferable experience?
- Soft skills called out in the JD (mentoring, leadership, stakeholder communication, Agile)
- Outcomes and metrics that could strengthen existing bullets
- Projects, side work, or in-progress work that maps to the role

For each gap that is genuinely missing (not just unwritten), be honest: if the user doesn't have the experience, say so. Suggest they build it (a side project, a weekend prototype) if the gap is bridgeable. Never add fabricated experience to the resume.

**Do not write new information back to personal-infos during resume generation.** If the user reveals new experience in this step, use it in the resume but leave the personal-infos folder untouched. Writing back is handled by a separate skill (`personal-infos-sync-skill`) that runs after the resume is delivered.

---

## Step 5: Compose the tailored resume

Using the master artifact and the answers from Step 4, compose a fresh resume. Do not copy from any previous resume — select and rewrite from scratch based on what this specific job needs.

### Content rules

**Curate, don't dump.** Pick the most relevant experiences. 5 strong targeted bullets beat 10 generic ones. Cut anything that doesn't serve this role.

**Relevance filter: only include bullets that speak to this job.** For every bullet you consider, ask: does this directly demonstrate a skill, tool, responsibility, or quality the JD asks for? If the answer is no, cut it — even if it's a strong accomplishment. A lean, laser-focused resume signals fit far better than a comprehensive one. This applies equally to experience and project sections.

**Always open each role and project with a context-setting bullet.** The first bullet under every job and every project must orient the reader — what the company/product does, what your role was, and what scope you owned. Hiring managers skim; without that grounding sentence they don't know what to make of the specifics that follow. The remaining bullets then go deep on relevant accomplishments. Think of it as: first bullet = context, remaining bullets = evidence.

**Mirror the JD's language.** If the JD says "scalable backend services", use that phrase. If it says "GROQ queries", say "GROQ queries". ATS systems match literally.

**Reframe, don't fabricate.** If the user built "a data pipeline", and the JD wants "content pipelines", reframe it if the underlying work is the same. Never invent work that didn't happen.

**Lead bullets with outcomes.** "Eliminated 1-on-1 walkthroughs by building a self-service onboarding wizard" is stronger than "Built an onboarding wizard."

**Write a Summary** (2–3 lines) that positions the user directly for this role. Use the JD's language. No "I". No filler phrases like "passionate about" or "proven track record".

**Bold for the hiring manager, not the ATS machine.** ATS reads plain text — it doesn't care about bold. Bold exists so a hiring manager skimming your resume instantly sees the parallel between what the role needs and what you've done. Aim for ~15 bolded phrases across the whole resume, 1–2 per bullet max.

**What to bold: outcomes, capabilities, and experience descriptions that mirror the JD's responsibilities.** The bolded phrase should read like a mini-answer to "have you done what we need?" Examples of good bolding:
- "enabling **usage-based billing, request throttling, and metering**" (tells the reader what you built, not what tool you used)
- "achieving **up to 10x throughput improvement** under high-volume workloads" (outcome the reader can evaluate)
- "**shipped rapid MVPs to a test group, gathered data-driven feedback, and iterated on what resonated**" (mirrors an experimentation mindset the JD asks for)
- "**owned the full debugging loop as a co-founder**" (mirrors an ownership requirement)
- "**Reduced development cycle from 1 month to 2 weeks**" (measurable impact)

**What NOT to bold: individual tech keywords or tool names.** Never bold things like **PostgreSQL**, **Alembic**, **Flask and React**, **FastAPI**, **RESTful API**, **Docker Compose**, **Django**. These are for the ATS to match in plain text and for the reader to absorb as context — they don't need visual emphasis. Bolding tech keywords makes the resume read like a highlighted keyword dump rather than a story about what you can do.

**The test:** Read only the bolded phrases in order. If they read like a list of technologies, the bolding is wrong. If they read like a summary of what you accomplished and how you work, the bolding is right.

**Order sections strategically.** If a project directly demonstrates a key skill the JD asks for, put Projects before Experience. Otherwise keep Experience first.

**Reorder skills categories** so the most relevant ones for this role appear first.

### Wording style

Write like an engineer describing their work to another engineer. Not like a recruiter, not like a marketing page.

**Front-load ownership and scope, not technology.** Start bullets with what you owned or what you did, then let the tech stack flow naturally as context. "Owned frontend development across a React/Electron desktop app and a Next.js/TypeScript web platform" — not "Built and maintained a **scalable** desktop app (**Electron + React**)."

**Show how things work, not just what was built.** "Designed an evaluation framework that decomposed LLM generation into measurable constraint checks" tells the reader about your engineering thinking. "Implemented an evaluation framework with constraint-based checks" just describes the feature.

**Vary your verbs.** Don't start every bullet with "Built." Use: Owned, Designed, Implemented, Translated, Optimized, Led, Identified, Monitored. If "Built" appears more than twice on the whole resume, rewrite some.

**Cut filler.** Remove decorative adjectives that don't add information: "content-rich", "learning-oriented", "clean and well-structured." If a word can be removed without losing meaning, remove it.

**Keep sentences tight.** One idea per sentence. If a bullet runs past two lines, it's probably two bullets.

**No company names in cover letters.** The user's previous employers (Nyquiste, Maple Growth, Solasphere) are not well-known. In cover letters, use "In my most recent role" or "Before that" instead. The resume has the company names for reference — the cover letter doesn't need them.

---

## Step 6: Output in the exact markdown template

The output must follow this exact format. The web renderer depends on the iconify span syntax, the ` : ` separator pattern, and the front matter. Do not simplify or alter the HTML spans.

```markdown
---
---

# [First Name Last Name]

<span class="iconify" data-icon="tabler:brand-github"></span> [github.com/username](https://github.com/username)
  : <span class="iconify" data-icon="tabler:phone"></span> [(+1) xxx-xxx-xxxx](tel:+1xxxxxxxxxx)
  : <span class="iconify" data-icon="tabler:brand-linkedin"></span> [linkedin.com/in/username](https://linkedin.com/in/username)

<span class="iconify" data-icon="ic:outline-location-on"></span> City, State (Open to relocation)
  : <span class="iconify" data-icon="tabler:mail"></span> [email@example.com](mailto:email@example.com)

## Summary

[2–3 lines. Tailored to this role. No "I". Use the JD's language for the target role and top skills.]

## Experience

**[Job Title]**
  : **[Company Name]**
  : **[Start – End Date]**

- [Bullet]
- [Bullet]

## Education

**[Degree]**
  : **[Graduation Date]**

[University Name] (GPA: x.xx/4.0)
  : [City, State]

## Projects

**[Project Name]** *(In Progress — if applicable)*

- [Bullet]
- [Bullet]

## Skills

**[Category]:** [skill], [skill], [skill]

**[Category]:** [skill], [skill], [skill]

**[Category]:** [skill], [skill], [skill]
```

**Formatting rules the renderer requires:**
- Two lines of `---` at the very top (front matter)
- Iconify `<span>` tags with `data-icon` attribute — copy exactly as shown
- Indented lines use two spaces + ` : ` (space-colon-space) for the right-aligned column layout
- Section headers are `##` (h2)
- Job titles, company names, and dates are all wrapped in `**bold**`
- Bullets use `- ` prefix
- Skills: each category is on its own line with a blank line between categories — `**Category:** item, item, item` — bold the category name, but not the individual skills. Never put all categories on a single line
- In-progress projects are marked with `*(In Progress)*` after the title

---

## Step 7: Verify keywords

After composing, run a quick keyword check against the JD's top 20–30 terms:

```bash
keywords=("keyword1" "keyword2" ...)
file="path/to/resume.md"
for kw in "${keywords[@]}"; do
  grep -qi "$kw" "$file" && echo "✅ $kw" || echo "❌ $kw — MISSING"
done
```

Fix any critical missing keywords before delivering.

---

## Step 8: Save and deliver

All output goes inside the `resumes/` folder in the working directory. Each job application gets its own subfolder named after the company (lowercase, hyphens for spaces). Inside that folder, save three files:

```
resumes/
└── [company-name]/
    ├── job_description.md       ← the full JD the user provided, exactly as given
    ├── [firstname]_resume_[company].md   ← the tailored resume
    └── generated_[YYYY-MM-DD].md        ← a brief metadata file (see below)
```

**generated_[YYYY-MM-DD].md** should contain:
```
# Application — [Company Name]
**Role:** [Job title]
**Generated:** [YYYY-MM-DD]
**Resume file:** [firstname]_resume_[company].md
```

Get today's date with:
```bash
date +%Y-%m-%d
```

Never overwrite an existing folder — if a folder for that company already exists, append a number (e.g., `freewheel-2/`).

Share the resume file link and briefly summarize:
- The 3–4 most important tailoring decisions made
- Any real gaps that remain (be honest — the user should know before applying)

---

## Step 9: Engineering head review

**After saving and delivering, always run the resume-review skill.** Read `resume-review-skill/SKILL.md` and follow its instructions to review the resume you just generated from an engineering head's perspective. This step is not optional — every resume gets reviewed before the user sends it out.

The review will flag issues like too many bullets, bad bolding, buried leads, tech stack mismatches, and keyword stuffing. After presenting the feedback, ask if the user wants the changes applied. If yes, apply them and re-verify ATS keywords.

---

## Notes

- **The personal-infos folder is the only source.** Never pull content from a previous tailored resume. Always go back to the `personal-infos/` folder.
- **Honest about gaps.** If experience is genuinely missing, say so. Help the user decide whether to build it (side project), address it (cover letter), or skip the role.
- **The template is fixed.** The iconify spans and ` : ` syntax are required by the renderer. Never simplify them.
- **Name formatting.** Use only the user's English name (e.g. "Jesse Chen"). Do not include Chinese characters or any non-English name variants, even if they appear in the personal-infos files.
- **Every resume is a fresh composition.** Same artifact, different job = different resume. Don't reuse bullets wholesale — rethink what matters for each role.
- **Never write back to personal-infos.** This skill only reads from personal-infos. If the user shares new experience during Step 4, use it for this resume but do not update the source files. The `personal-infos-sync-skill` handles that as a separate step after delivery.
