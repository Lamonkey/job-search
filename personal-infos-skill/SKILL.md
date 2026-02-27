---
name: personal-infos
description: >
  Adds or updates content in the user's personal-infos folder — the source of truth for resume generation. Use this skill any time the user wants to add or update their work experience, a project, or basic personal info (name, email, phone, education, LinkedIn, GitHub, etc.). Trigger when the user says things like "add my job at X", "update my experience at Y", "add a project", "I worked on Z", "update my education", "add my contact info", or anything that sounds like they're building up their background info. Also trigger when the user pastes or uploads a resume, a project description, or any block of career-related text and wants it saved — the skill will parse it, match it to existing files, and create or update as needed. Always use this skill when the user is trying to maintain their personal info files.
---

# Personal Infos Manager

You maintain the user's `personal-infos/` folder — the source of truth used by the resume skill. The folder contains one file per job, one file per project, and one file for basic info. Your job is to add new information or update existing information in the right file.

---

## Folder structure

```
personal-infos/
├── basics.md                    ← name, email, phone, location, LinkedIn, GitHub, education
├── experience_[company].md      ← one file per job (e.g. experience_google.md)
└── project_[name].md            ← one file per project (e.g. project_ecommerce_dashboard.md)
```

Use lowercase and underscores for filenames. Keep names short but recognizable.

---

## Step 1: Understand what the user is giving you

There are two modes:

**Direct input** — The user tells you something specific ("add my job at Acme", "I built a project called X", "my email is..."). Go to Step 2.

**Bulk input** — The user pastes a resume, a project description, a LinkedIn export, or any block of career-related text. In this case:
1. Parse the content and break it into individual pieces: jobs, projects, education, contact info
2. List what you found — e.g. "I found 2 jobs, 3 projects, and basic info. Here's what I'll save:" — and show a brief summary before doing anything
3. Wait for the user to confirm or correct before writing any files
4. Then process each piece through Steps 2 and 3 below

---

## Step 2: Check if the file already exists

List the files in `personal-infos/`. For each piece of information, determine whether this is:

- **An update** — a company or project name matches an existing file → merge new bullets in
- **Something new** — no matching file exists → create a new one

When matching, be fuzzy but sensible. "Google LLC" and "Google" are the same. "E-commerce dashboard" and "ecommerce_dashboard" are the same. If you're unsure whether something is a match, ask before creating a duplicate.

---

## Step 3: Add or update the content

### For basics.md (basic info)

If `basics.md` doesn't exist yet, create it with this structure:

```markdown
# Basic Info

**Name:**
**Email:**
**Phone:**
**Location:**
**LinkedIn:**
**GitHub:**

## Education

**[Degree]** — [University], [Graduation Year] (GPA: x.xx)

## Certifications

- [Certification name], [Issuer], [Year]
```

Update only the fields the user provides. Never clear fields that already have content unless the user says to replace them.

### For experience_[company].md and project_[name].md

Keep the format simple — preserve the original bullet points exactly as written. Do not restructure into sections like "Accomplishments" or "Tools & Technologies".

If creating a new file:

```markdown
# [Job Title] at [Company Name]

**Company:**
**Role:**
**Start Date:**
**End Date:** (or "Present")

- [bullet from resume]
- [bullet from resume]
- [bullet from resume]
```

For projects:

```markdown
# [Project Name]

**Status:** (In Progress / Completed / Paused)
**Timeline:**

- [bullet from resume]
- [bullet from resume]
```

**When merging into an existing file:** Read the existing bullets and compare them to the new ones. Add any bullet that conveys meaningfully new information — a different angle, a new tool, a new outcome, a new design decision. Skip bullets that are essentially saying the same thing as something already there, even if worded differently. Use judgment — when in doubt, include rather than exclude. Never remove or rewrite existing bullets.

---

## Step 4: Confirm and save

After writing or updating all files, briefly confirm what happened:
- List each file that was created or updated
- One line per file saying what was added or changed

Keep it short. A compact table works well for bulk input:

| File | Action | Summary |
|------|--------|---------|
| experience_acme.md | Created | Software Engineer role, 2022–2024 |
| project_dashboard.md | Updated | Added 2 new bullets |
| basics.md | Updated | Added email and LinkedIn |

---

## Notes

- **Never delete or rewrite existing bullets** unless the user explicitly asks.
- **Don't invent details.** Only save what the user actually provided.
- **Keep files clean.** Consistent formatting so the resume skill can read them reliably.
