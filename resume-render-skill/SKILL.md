---
name: resume-render
description: >
  Renders a tailored resume Markdown to a single filled page and exports a print-accurate PDF.
  Use after a resume has been generated (e.g. by the resume skill) and saved to resumes/[company]/.
  Drives the headless renderer in the markdown-resume editor, fitting the page by adjusting line
  spacing first and font size second to land on a single, well-filled page, then writes the PDF
  next to the .md. Trigger when the user says "render the resume", "fit this to one page", "make it
  one page", "export the PDF", or after composing a resume that needs to be finalized for sending.
---

# Resume Render Skill

Take a finished resume Markdown file and produce a **single-page, well-filled, print-accurate PDF** by adjusting only line spacing and font size. The page layout (margins, fonts, paper) is fixed by the defaults below; this skill only tunes the fit.

## Tool

The renderer lives in the markdown-resume repo:

```
cd /Users/jesse/Development/markdown-resume
pnpm render <abs-path-to-resume.md> [--font-size N] [--line-height N] [--pdf out.pdf] [--png out.png] [--json]
```

- It renders the resume headlessly in the actual editor (so the PDF matches the editor's Export PDF exactly) and prints `{ "pages": N, "fits": bool, "pdf": ..., "styles": {...} }`.
- It **auto-starts the dev server** if it isn't running. First run after a fresh clone needs `pnpm install` and `pnpm build:pkg` once.
- Use `--json` while searching (quiet, machine-readable). Pass `--pdf <path>` only on the final render.

## Fixed defaults (do not change these to fit)

These are already the renderer's defaults — `pnpm render <md>` with no flags uses them:

- Paper **A4**; fonts **华康宋体** (Chinese) / **Verdana** (English)
- Margins: **top 0**, **bottom 20**, **left/right 16**
- Paragraph spacing **5**
- Starting font size **13**, starting line spacing **1.25**

## The fit algorithm (line-first — keep the font big)

The goal is one page, filled, with the **largest readable font**. Line spacing is the fine knob; font size is the coarse fallback.

Bounds: **font size 10.5–14** (start 13), **line spacing 1.15–1.50**. Step font by 0.5, line by 0.05 (then refine by 0.01 near the boundary).

1. **Render at the defaults** (font 13, line 1.25): `pnpm render <md> --json`.
2. **Tune line spacing at the current font** to the largest value that still fits one page:
   - If it's **over one page**, lower line spacing toward **1.15**.
   - If it **fits with blank space**, raise line spacing toward **1.50**.
   - Find the boundary: the largest line spacing where `pages == 1`. That is the maximally-filled page at this font.
3. **Only adjust font size when line spacing can't resolve it:**
   - If even **line 1.15** is still over one page → drop font by 0.5 and go back to step 2.
   - If even **line 1.50** still leaves blank (a short resume) → raise font by 0.5 (cap **14**) and go back to step 2.
4. **Floor:** if the font would have to go **below 10.5** to fit, stop shrinking — the resume has too much content. **Trim the weakest bullet or project** (see the resume skill's selection logic) and re-run from step 1. Never make the resume unreadable to force one page.
5. **Final render:** once you have the winning `font-size` / `line-height`, render once more with `--pdf <resumes/[company]/[firstname]_resume_[company].pdf>`.

## Always do a visual check

Fitting is visual, not just numeric. After the final render, **read the PDF** (or a `--png`) and confirm it actually looks right — balanced, not cramped, no awkward last-line widow, sections not split oddly. The page-count number passing is necessary but not sufficient. If it looks off, adjust and re-render.

## Output

Report the final settings (`font-size`, `line-height`) and the PDF path. Example: "Fit to one page at font 13 / line 1.24 → resumes/traba/jesse_resume_traba.pdf".

## Notes

- Search quietly with `--json` (no `--pdf`); each render takes a few seconds, so bracket coarsely then refine, rather than testing every 0.01.
- Margins, fonts, and paper are intentionally out of scope here — they're the fixed house style. If the user wants to change them, that's a defaults change in the markdown-resume repo, not a per-resume fit.
