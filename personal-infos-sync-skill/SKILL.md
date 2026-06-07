---
name: personal-infos-sync
description: >
  Syncs new experience discovered during resume generation back to the personal-infos folder. Use this skill after a resume has been delivered, when the user revealed new details during the gap-analysis Q&A (Step 4 of the resume skill) that aren't yet captured in the personal-infos files. This skill reviews what was learned, matches it to existing files, and writes the new information back so it's available for future resumes. Trigger when: "sync my info", "update personal infos", "save what I told you", "write back to personal infos", or automatically as the final step after resume delivery when new information was surfaced.
---

# Personal-Infos Sync

You write newly discovered experience back to the `personal-infos/` folder after a resume has been generated. During resume generation (Step 4 of the resume skill), the user often reveals details that aren't in their personal-infos files — tools they've used, skills they forgot to mention, side experience that maps to a gap. That information gets used in the resume, but it needs to be persisted back to the source-of-truth files so future resumes can draw from it too.

This skill runs **after** the resume is delivered. It never runs during resume generation.

---

## Step 1: Identify what's new

Review the conversation history from the resume generation session. Look for information the user provided during the interactive Q&A (Step 4) that is **not already captured** in the personal-infos files. Common categories:

- Tools or technologies the user confirmed they've used (e.g., "I used Selenium and Playwright for the DMV project")
- Skills or practices not in any file (e.g., "I always wrote unit and integration tests")
- New details about existing roles (e.g., "I wrote shell scripts for CI/CD and Docker setup")
- Auth, infrastructure, or process experience (e.g., "I implemented OAuth2/JWT")
- Soft skills with concrete examples (e.g., mentoring, leading a team)

**Only include things the user actually confirmed.** Do not infer or invent details. If the user said "minimal" or "no experience" for a gap, do not write anything for that gap.

---

## Step 2: Match to existing files

Read the current files in `personal-infos/`. For each piece of new information, determine which file it belongs to:

- New details about a job → `experience_[company].md`
- New details about a project → `project_[name].md`
- New personal info (contact, education, certs) → `basics.md`
- Entirely new project or job → create a new file following the personal-infos skill naming conventions

Use fuzzy matching — "Nyquiste" and "nyquiste" are the same. If unsure, ask.

---

## Step 3: Write the updates

For each file that needs updating, **append new bullets at the end** of the existing bullet list. Follow these rules from the personal-infos skill:

- **Never delete or rewrite existing bullets.** Only add.
- **Don't restructure the file.** Keep the format as-is.
- **Write bullets in the user's voice.** Match the style of the existing bullets in that file.
- **One idea per bullet.** Don't cram multiple new facts into one line.
- **Skip duplicates.** If the new info is already covered by an existing bullet (even in different words), don't add it.

---

## Step 4: Confirm what was written

After making all updates, show a summary table:

| File | Action | What was added |
|------|--------|----------------|
| `experience_nyquiste.md` | Updated | Added shell scripting and OAuth2/JWT bullets |
| `project_nc_dmv_tracker.md` | Updated | Added Selenium alongside Playwright |

Keep it short. The user already knows what they told you — they just need to confirm it landed in the right place.

---

## When to trigger

This skill should run in one of two ways:

1. **Automatically after resume delivery** — if the resume skill's Step 4 surfaced new information that was used in the resume but isn't in the personal-infos files, prompt the user: "I used some new details you shared in this resume. Want me to sync them back to your personal-infos files so they're available for future resumes?"
2. **Manually** — the user says "sync my info", "update personal infos", "save what I told you back", or similar.

---

## Notes

- **This skill only adds information.** It never removes, rewrites, or restructures existing content.
- **It only writes facts the user explicitly confirmed.** Never add inferred experience.
- **It runs after resume generation, never during.** The resume skill reads from personal-infos; this skill writes back to it. Keeping them separate avoids mid-generation file conflicts and keeps each skill's job clear.
