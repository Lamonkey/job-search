# Job Search Workspace

## Skills to load at the start of every session

When working in this folder, always read the following skill files before doing any work:

1. **Personal Infos Skill** — manages the `personal-infos/` folder (source of truth for all resume generation)
   - File: `personal-infos-skill/SKILL.md`

2. **Resume Skill** — generates tailored resumes from `personal-infos/` for a specific job description
   - File: `resume-skill/SKILL.md`

3. **Cold Outreach Skill** — writes personalized cold outreach emails to hiring managers
   - File: `cold-outreach-skill/skill.md` (this is a zipped .skill package — extract with `unzip` to a temp directory first, then read `cold-outreach/SKILL.md`)

## Folder structure

```
job search/
├── personal-infos/          ← source of truth for experience, projects, basics
├── personal-infos-skill/    ← skill for managing personal-infos/
├── resume-skill/            ← skill for generating tailored resumes
├── cold-outreach-skill/     ← skill for writing cold outreach emails
└── resumes/                 ← generated resumes, one subfolder per company
```
