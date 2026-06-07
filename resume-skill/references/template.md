# Resume Markdown Template

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

[1–2 sentences. Tailored to this role. No "I". Use the JD's language for the target role and top skills.]

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

**[Project Name]**

- [Bullet]
- [Bullet]

## Skills

**[Category]:** [skill], [skill], [skill]

**[Category]:** [skill], [skill], [skill]

**[Category]:** [skill], [skill], [skill]
```

## Formatting rules the renderer requires

- Two lines of `---` at the very top (front matter)
- Iconify `<span>` tags with `data-icon` attribute — copy exactly as shown
- Indented lines use two spaces + ` : ` (space-colon-space) for the right-aligned column layout
- Section headers are `##` (h2)
- Job titles, company names, and dates are all wrapped in `**bold**`
- Bullets use `- ` prefix
- Skills: each category is on its own line with a blank line between categories. Format: `**Category:** item, item, item`. Bold the category name, but not the individual skills. Never put all categories on a single line

## Name formatting

Use only the user's English name (e.g., "Jesse Chen"). Do not include Chinese characters or any non-English name variants, even if they appear in the personal-infos files.
