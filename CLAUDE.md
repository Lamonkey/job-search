# Job Search Workspace

## Skills to load at the start of every session

When working in this folder, always read the following skill files before doing any work:

1. **Personal Infos Skill** — manages the `personal-infos/` folder (source of truth for all resume generation)
   - File: `personal-infos-skill/SKILL.md`

2. **Resume Skill** — generates tailored resumes from `personal-infos/` for a specific job description
   - File: `resume-skill/SKILL.md`

3. **Cold Outreach Skill** — writes personalized cold outreach emails to hiring managers
   - File: `cold-outreach-skill/skill.md` (this is a zipped .skill package — extract with `unzip` to a temp directory first, then read `cold-outreach/SKILL.md`)

4. **Interview Answer Skill** — helps answer application and interview questions by checking past answers first, then adapting or drafting new ones
   - File: `interview-answer-skill/SKILL.md`

5. **Resume Review Skill** — reviews every generated resume from an engineering head's perspective, flags issues a human reader would notice, and offers to apply fixes
   - File: `resume-review-skill/SKILL.md`
   - Auto-triggers as Step 7 of the resume-skill (review before save)

6. **Personal-Infos Sync Skill** — writes newly discovered experience back to `personal-infos/` after a resume is delivered
   - File: `personal-infos-sync-skill/SKILL.md`
   - Runs after resume delivery when the user revealed new details during gap-analysis Q&A
   - The resume skill reads from personal-infos; this skill writes back to it — they never overlap

7. **Gap-Filling Skill** — designs buildable projects to fill skill gaps found during resume generation
   - File: `gap-filling-skill/SKILL.md`
   - Auto-triggers during resume-skill Step 4 Phase 2 when user confirms they lack a required skill
   - Writes projects to `personal-infos/` as "In Progress"
   - Logs tech stack pairing feedback to `gap-filling-skill/pairing-feedback.md` for iterative refinement

## Folder structure

```
job search/
├── personal-infos/          ← source of truth for experience, projects, basics
├── personal-infos-skill/    ← skill for managing personal-infos/
├── resume-skill/            ← skill for generating tailored resumes
├── resume-review-skill/     ← skill for eng-head review of generated resumes
├── personal-infos-sync-skill/ ← skill for syncing new info back to personal-infos/
├── gap-filling-skill/       ← skill for designing projects to fill skill gaps
├── cold-outreach-skill/     ← skill for writing cold outreach emails
├── interview-answer-skill/  ← skill for answering application/interview questions
├── interview-questions/     ← library of past answers, one file per question
└── resumes/                 ← generated resumes, one subfolder per company
```
