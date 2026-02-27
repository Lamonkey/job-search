# Personal Infos Skill — Test Cases

Rerun these tests any time after making changes to the skill to verify nothing broke.

## What the tests check

- **Eval 1** (`parse-backend-resume`): Feed `fixtures/resume_backend.md` to the skill. Checks that it creates the right files and captures all tech stack items, impact metrics, and design decisions. **26 points total.**
- **Eval 2** (`parse-frontend-resume-and-merge`): Feed `fixtures/resume_frontend.md` on top of eval 1's output. Checks that new content is added correctly, existing content is NOT overwritten, and no duplicate files are created. **20 points total.**

Assertions and grading rubric are in `evals.json`. Anonymized test resumes are in `fixtures/`.

---

## How to run

**Step 1 — Clear any previous test output**
```bash
rm -rf /tmp/personal-infos-test/
mkdir -p /tmp/personal-infos-test/
```

**Step 2 — Run eval 1**

Give the skill this prompt, pointing it at the test fixture:
> "Here is my resume, please add everything to my personal-infos folder."

Set the output directory to `/tmp/personal-infos-test/` so nothing touches your real `personal-infos/` folder. The skill should create:
- `basics.md`
- `experience_acme_corp.md`
- `experience_beta_analytics.md`
- `project_gamma.md`
- `project_delta_stream_analyzer.md`

**Step 3 — Grade eval 1**

For each assertion in `evals.json` under eval id 1, run the `check` grep command against the output files in `/tmp/personal-infos-test/`. Mark each passed or failed. Deduct 1 point per failure.

**Step 4 — Run eval 2**

Without clearing the test folder, give the skill this prompt:
> "Here is another version of my resume. Please add any new information to my personal-infos folder. Don't overwrite what's already there — only add what's new."

Point it at `fixtures/resume_frontend.md`.

**Step 5 — Grade eval 2**

Run the grep checks from eval id 2 in `evals.json`. Pay close attention to the `PRESERVED` assertions — these confirm old content was not overwritten.

**Step 6 — Report the score**

```
Eval 1: X / 26
Eval 2: Y / 20
Total:  Z / 46
```

List every failed assertion by name so it's clear what regressed.
