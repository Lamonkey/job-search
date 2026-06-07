You are running inside a Cowork session with access to the "job search" workspace folder. Your job is to check the `to-apply/` folder for any unprocessed job description `.md` files, generate a tailored resume for each one, and report the results.

The workspace folder is your mounted working directory. All paths below are relative to it (e.g. `to-apply/`, `resume-skill/SKILL.md`, `personal-infos/`, etc.).

---

## Step 1: Claim a file (atomic scan + move)

**This step MUST happen before reading any file contents or doing any other work.**

Run a single bash command that:
1. Creates `to-apply/processing/` if it doesn't exist
2. Lists all `.md` files directly inside `to-apply/` (not in subfolders like `processed/` or `processing/`)
3. Picks the **first** file found
4. Immediately moves it to `to-apply/processing/`

Use something like:
```bash
mkdir -p to-apply/processing && FILE=$(ls to-apply/*.md 2>/dev/null | head -1) && [ -n "$FILE" ] && mv "$FILE" "to-apply/processing/$(basename "$FILE")" && echo "CLAIMED: $(basename "$FILE")" || echo "NO_FILES"
```

If the output is `NO_FILES`, output:
> No new job files found in to-apply/. Nothing to do.

Then stop. Do not proceed further.

If the move fails (e.g. file was already moved by a parallel run), treat it as `NO_FILES` and stop.

From this point on, work with the file in `to-apply/processing/`. Process only this one file — do not loop.

---

## Step 2: Parse the file

Each file follows this format:

```
---
url: https://example.com/careers/123
---
[job description text here, or the URL is the only source]
```

Extract:
- **url** — from the `url:` line inside the opening code fence block
- **job description body** — all text after that block (may be empty if only a URL was given; in that case fetch the URL)

---

## Step 3: Generate a resume

Read `resume-skill/SKILL.md` and follow ALL steps in it:

- **Step 1** – Quick disqualifiers (clearance, visa)
- **Step 2** – Read ALL files in `personal-infos/`.
- **Step 3** – Gap analysis (ATS / hiring manager / HR screener)
- **Step 4** – Since this is an automated run (no interactive user), skip Phase 1 (asking questions) and go directly to Phase 2. **You must read `gap-filling-skill/SKILL.md` and run it for every critical gap identified in Step 3.** Do not skip this step. Do not substitute your own judgment about whether existing projects "partially" cover the gap — read the skill and run it. Pass it the full list of critical gaps, the JD context, and the user's existing stack from personal-infos.
- **Step 5** – Compose the resume using `resume-skill/references/template.md`, `resume-skill/references/style-guide.md`, and `resume-skill/references/hiring-manager-lens.md`
- **Step 6** – Run the keyword verification bash loop against the JD's top 20–30 terms. Fix any missing critical keywords before moving on.
- **Step 7** – **Engineering head review. This step is mandatory and must be completed before the resume is saved.** Read `resume-review-skill/SKILL.md` completely. Then set aside the fact that you wrote the resume and read it fresh as the engineering head described in that skill. Work through every dimension in the skill. Apply every fix the review identifies. After applying fixes, re-run the keyword check from Step 6 to confirm no critical keywords were dropped. Do not proceed to Step 8 until this is done.
- **Step 8** – Save to `resumes/[company-name]/`. Only save after Step 7 is fully complete.

---

## Step 4: Move the processed file

After the resume is saved:
- Move the file from `to-apply/processing/` to `to-apply/processed/`

---

## Step 5: Output results

Output a one-line summary (e.g. "✅ hiring-cafe.md — resume generated"), then present two clickable elements:

1. **A markdown hyperlink** to the job posting URL, formatted as:
   `**[Company Name — Job Posting](url)**`

2. **A file card** — call `mcp__cowork__present_files` (load via ToolSearch if deferred) with the saved resume **PDF** if `resume-skill` Step 8 rendered one (it auto-runs the `resume-render` skill), otherwise the resume **`.md`**, so the user gets a clickable card that opens it in the side panel.

If the file failed, output:
```
❌ [filename] — [reason it failed]
```
