---
name: resume
description: >
  Generates a tailored resume from the user's personal-infos folder for a specific job. Use this skill any time the user provides a job description and wants a resume — whether they say "tailor my resume", "make a resume for this job", "generate my resume", "help me apply to this", "what's missing from my resume for this role", or just pastes a job description. The skill reads all experience from the personal-infos/ folder (not from any previous resume), does a gap analysis, asks targeted questions to surface hidden experience, and outputs a complete resume in the required iconify markdown template format, ready to paste into a web renderer. Always trigger this skill when a job description is involved and a resume is the desired output.
---

# Resume Skill

You generate a tailored resume for a specific job. The source of truth for the user's experience is their **personal-infos folder** — located at `personal-infos/` in the working directory. Every resume is composed fresh from these files, never from a previous resume.

The final output is a markdown file in a specific template format. Read `references/template.md` for the exact format.

Before composing, read `references/hiring-manager-lens.md` — it describes how a hiring manager actually reads a resume. Every decision you make (what to include, what to bold, how to order things) should be filtered through that lens.

Before writing any bullet, read `references/style-guide.md` — it covers bolding, bullet writing, language to avoid, and the selection logic for what to include vs. cut.

---

## Step 1: Quick disqualifiers

Before doing any work, scan the JD for three deal-breakers:

**Security clearance** — Look for "TS/SCI", "Top Secret", "Secret clearance", "must have active clearance", "able to obtain a clearance." The user does not have a security clearance and is not eligible for one. If the role requires one, stop and tell the user to skip it.

**Visa sponsorship** — Look for "must be authorized to work", "no sponsorship", "will not sponsor", "U.S. citizens only", "not eligible for sponsorship", "cannot sponsor". The user is on an H-1B visa and requires employer sponsorship to work legally in the US. If the role explicitly states it will not sponsor, **stop immediately and do not generate a resume**. Tell the user the role doesn't offer sponsorship and recommend skipping it. Do not proceed unless the user explicitly says to continue anyway.

**Likely PERM labor certification posting** — PERM postings are job ads filed by companies to prove no qualified U.S. worker is available, so they can sponsor a specific foreign worker they've already chosen. The requirements are intentionally designed to be unfillable. Flag and skip the role if the "minimum requirements" combine skills from two or more unrelated engineering specializations that no single candidate would realistically have. Common tells:
- Niche proprietary tools alongside common web frameworks (e.g., Spirent + Django + React, or MATLAB + Rails + Kubernetes)
- Low-level systems/networking tools mixed with frontend/full-stack requirements (e.g., gdb + kernels + Wireshark alongside TypeScript + React)
- An impossibly broad required tech list (10+ specific tools spanning 3+ domains) listed as *minimum* requirements for a mid-level role
- The JD body describes normal software engineering work, but the requirements read like three different job descriptions merged into one

If you spot this pattern, stop and tell the user: "This looks like a PERM labor certification posting — the requirements combine [X domain] tools with [Y domain] tools in a way no real candidate would match. The company likely already has a candidate in mind and filed this ad to satisfy immigration requirements. Recommend skipping." Don't proceed with resume generation unless they say to continue anyway.

In all three cases, just tell the user and move on — don't proceed with resume generation unless they say to continue anyway.

---

## Step 2: Get the job description and read personal-infos

The user will paste a job description or share a URL. If it's a URL, fetch it. Extract: job title, company, core responsibilities, required skills/tools, preferred qualifications, and any specific keywords.

Then read **every file** in `personal-infos/`. This is the only source you draw from.

---

## Step 3: Gap analysis (read `references/hiring-manager-lens.md` first)

Compare the JD against the personal-infos files. Think like three people:

**ATS scanner** — Which exact keywords and tool names from the JD are missing? ATS matches literally — "Apache Kafka" and "message queue" are not the same.

**Hiring manager** — Does the user's experience tell a story that fits this role? What's the strongest case? What's the weakest? (Reference `references/hiring-manager-lens.md` for how they think.)

**HR screener** — Does the user meet the stated requirements? Gaps in years of experience, credentials, or specific tools?

Identify: strong matches (lead with these), critical gaps (required skills missing), nice-to-have gaps, and language gaps (user has the experience but uses different vocabulary).

Be honest. If the role is a stretch, say so — but also explain the strongest arguments.

---

## Step 4: Surface hidden experience and fill gaps

This step has three phases: ask, fill, then sync.

### Phase 1: Ask about gaps

For each critical gap from Step 3, ask the user whether they have experience using `AskUserQuestion`. Group related gaps into 2–3 rounds max. For each gap, the question should be direct: "Do you have any experience with [tool/skill]?" with options like "No experience", "Tutorials/learning", "Small project or script", etc.

Focus on:
- Required tools/skills the JD lists that aren't in personal-infos
- Outcomes and metrics that could strengthen existing bullets
- Projects or side work that maps to the role

If the user says **yes** to a gap — capture the details and use them in the resume.

### Phase 2: Fill remaining gaps with buildable projects

For gaps where the user answered **no** — run the gap-filling skill (`gap-filling-skill/SKILL.md`). Read it and follow its instructions. It designs realistic, buildable projects that demonstrate the missing skill in an industry-relevant context and writes them to `personal-infos/` as "In Progress."

Pass it: the list of gaps, the JD context (role, company, domain), and the user's existing stack from personal-infos.

### Phase 3: Sync new information back to personal-infos

After composing the resume (Step 5), if the user revealed new experience during Phase 1 that isn't already in the personal-infos files, run the `personal-infos-sync-skill` to write it back. This keeps the source of truth up to date for future resumes.

The sync happens after composition, not during — so it doesn't interfere with the writing process.

---

## Step 5: Compose the resume

Read these before writing:
- `references/hiring-manager-lens.md` — the mental model for every decision
- `references/style-guide.md` — bolding, bullet writing, language rules

Key principles (the reference files have the details):

**Curate for this role.** For every bullet, ask: does this directly demonstrate something the JD asks for? If no, cut it — even if it's strong. 5 targeted bullets beat 10 generic ones.

**Context first.** The first bullet under every role must orient the reader — what the company does, what you owned, what scope. Without this, the reader doesn't know what to make of the specifics.

**Bold for the human reader.** Bold outcomes and capabilities ("**reduced cycle time from 1 month to 2 weeks**"), never individual tech keywords (not **PostgreSQL**, not **Docker**). Read `references/style-guide.md` for the full rules and self-test.

**Mirror the JD's language.** If the JD says "scalable backend services," use that phrase. But reframe naturally — don't copy JD sentences verbatim and bold them back.

**Write like an engineer.** Not like a recruiter, not like a marketing page. Front-load ownership and scope, show how things work, cut filler.

**Section order.** If a project directly demonstrates a key skill the JD asks for that work experience doesn't cover, put Projects before Experience.

Read `references/template.md` for the exact output format.

---

## Step 6: Verify keywords

After composing, check the JD's top 20–30 terms against the resume:

```bash
keywords=("keyword1" "keyword2" ...)
file="path/to/resume.md"
for kw in "${keywords[@]}"; do
  grep -qi "$kw" "$file" && echo "✅ $kw" || echo "❌ $kw — MISSING"
done
```

Fix critical missing keywords. Don't add keywords for skills the user genuinely doesn't have.

---

## Step 7: Engineering head review

Before saving, run the `resume-review-skill`. Read `resume-review-skill/SKILL.md` and follow it. This step is not optional — every resume gets reviewed before the user sends it out. The review skill handles saving the final resume to the `resumes/[company-name]/` folder after fixes are applied.

If the user declines the review fixes, save the resume as-is using the structure below.

---

## Step 8: Save and deliver

The review skill saves the resume. If for any reason it hasn't been saved yet, save to `resumes/[company-name]/` (lowercase, hyphens). Three files:

```
resumes/[company-name]/
├── job_description.md         ← the full JD, exactly as given
├── [firstname]_resume_[company].md  ← the tailored resume
└── generated_[YYYY-MM-DD].md       ← metadata (role, date, resume filename)
```

Never overwrite an existing folder — append a number if needed.

### Render to one page and export the PDF (automatic)

After saving the `.md`, run the **resume-render skill** (`resume-render-skill/SKILL.md`) on it to produce a single-page, print-accurate PDF in the same folder. Read that skill and follow it — it drives the headless renderer in the markdown-resume repo, tunes line spacing and font size to one filled page (line-first, keeping the font large), and writes `resumes/[company-name]/[firstname]_resume_[company].pdf`.

This is **automatic** — don't ask first, just run it as the final delivery step. If the resume can't reach one page without dropping the font below the render skill's floor, the render skill will say so; trim the weakest bullet or project (Step 5 selection logic) and re-render.

### (Optional) Open in the editor for manual tweaks

If the user wants to hand-edit or re-print in the browser, load the saved `.md` straight into the local editor — no copy-paste — via an `?import=` URL (requires `pnpm dev` running in `/Users/jesse/Development/markdown-resume`):

```bash
RESUME="$(pwd)/resumes/[company-name]/[firstname]_resume_[company].md"
ENC() { python3 -c 'import urllib.parse,sys; print(urllib.parse.quote(sys.argv[1]))' "$1"; }
echo "http://localhost:3000/markdown-resume/?import=$(ENC "$RESUME")&name=$(ENC "[Company] — [Role]")"
```

Re-running with the same `&name=` overwrites that resume in place (no duplicates).

### Summarize

Share the **PDF** and briefly summarize: the fit settings used (font size / line spacing), the 3–4 most important tailoring decisions, and any real gaps that remain.

---

## Notes

- The personal-infos folder is the only source. Never pull from a previous resume.
- Every resume is a fresh composition. Same personal-infos, different job = different resume.
- Writing to personal-infos happens only in Step 4 (gap-filling projects) and after composition (sync). Never during Step 5 composition itself.
- Be honest about gaps. Help the user decide whether to build it, address it, or skip the role.
