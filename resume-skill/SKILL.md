---
name: resume
description: >
  Generates a tailored resume from the user's personal-infos folder for a specific job. Use this skill any time the user provides a job description and wants a resume — whether they say "tailor my resume", "make a resume for this job", "generate my resume", "help me apply to this", "what's missing from my resume for this role", or just pastes a job description. The skill reads all experience from the personal-infos/ folder (not from any previous resume), does a gap analysis, asks targeted questions to surface hidden experience, and outputs a complete resume in the required iconify markdown template format, ready to paste into a web renderer. Always trigger this skill when a job description is involved and a resume is the desired output.
---

# Resume Skill

You generate a tailored resume for a specific job. The source of truth for the user's experience is their **personal-infos folder** — located at `personal-infos/` in the working directory. It contains files that capture all their roles, projects, and skills. You never reference or copy from a previous resume. Every resume is composed fresh from the personal-infos folder, tailored to the job at hand.

The final output is a markdown file in a specific template format that the user pastes into a web app to render as HTML. Template fidelity is non-negotiable.

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

---

## Step 5: Compose the tailored resume

Using the master artifact and the answers from Step 4, compose a fresh resume. Do not copy from any previous resume — select and rewrite from scratch based on what this specific job needs.

### Content rules

**Curate, don't dump.** Pick the most relevant experiences. 5 strong targeted bullets beat 10 generic ones. Cut anything that doesn't serve this role.

**Mirror the JD's language.** If the JD says "scalable backend services", use that phrase. If it says "GROQ queries", say "GROQ queries". ATS systems match literally.

**Reframe, don't fabricate.** If the user built "a data pipeline", and the JD wants "content pipelines", reframe it if the underlying work is the same. Never invent work that didn't happen.

**Lead bullets with outcomes.** "Eliminated 1-on-1 walkthroughs by building a self-service onboarding wizard" is stronger than "Built an onboarding wizard."

**Write a Summary** (2–3 lines) that positions the user directly for this role. Use the JD's language. No "I". No filler phrases like "passionate about" or "proven track record".

**Bold 20–30 critical keywords** — technologies, methodologies, role-specific terms. Bold what a recruiter's eye should land on. Don't bold everything.

**Order sections strategically.** If a project directly demonstrates a key skill the JD asks for, put Projects before Experience. Otherwise keep Experience first.

**Reorder skills categories** so the most relevant ones for this role appear first.

---

## Step 6: Output in the exact markdown template

The output must follow this exact format. The web renderer depends on the iconify span syntax, the ` : ` separator pattern, and the front matter. Do not simplify or alter the HTML spans.

```markdown
---
---

# [Full Name]

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

**[Category]:** [skill], **[key skill]**, [skill]
```

**Formatting rules the renderer requires:**
- Two lines of `---` at the very top (front matter)
- Iconify `<span>` tags with `data-icon` attribute — copy exactly as shown
- Indented lines use two spaces + ` : ` (space-colon-space) for the right-aligned column layout
- Section headers are `##` (h2)
- Job titles, company names, and dates are all wrapped in `**bold**`
- Bullets use `- ` prefix
- Skills are `**Category:** item, item, **key item**, item` on a single line
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

Save to the workspace folder as:
`[firstname]_resume_[company].md`

Example: `jdoe_resume_acme.md`

Never overwrite a previously saved resume — each job gets its own file.

Share the file link and briefly summarize:
- The 3–4 most important tailoring decisions made
- Any real gaps that remain (be honest — the user should know before applying)

---

## Notes

- **The personal-infos folder is the only source.** Never pull content from a previous tailored resume. Always go back to the `personal-infos/` folder.
- **Honest about gaps.** If experience is genuinely missing, say so. Help the user decide whether to build it (side project), address it (cover letter), or skip the role.
- **The template is fixed.** The iconify spans and ` : ` syntax are required by the renderer. Never simplify them.
- **Every resume is a fresh composition.** Same artifact, different job = different resume. Don't reuse bullets wholesale — rethink what matters for each role.
