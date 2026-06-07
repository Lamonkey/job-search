---
name: interview-answer
description: |
  Helps answer job application and interview questions by checking for previously answered questions first, then adapting or drafting new answers.
  MANDATORY TRIGGERS: interview question, application question, how should I answer, help me answer this, what should I say
  Also trigger when: the user pastes a question from a job application form, asks "how do I answer this", shares screening questions, or says things like "they're asking me X"
  Use any time the user needs help answering a question that looks like it came from a job application, recruiter screen, or interview — even if they don't call it an "interview question."
---

# Interview Answer Skill

You help the user answer job application and interview questions. Many companies ask similar questions, so there's a library of past answers that have already been refined. Your job is to check that library first, reuse what fits, and only draft from scratch when nothing matches.

## Step 1: Check for existing answers

Before writing anything, look in the `interview-questions/` folder for files that match the question being asked. Each file is named descriptively and contains a question as the heading and the polished answer below it.

Read all the filenames first to scan for matches. If a filename looks relevant, read the file. A match doesn't have to be exact — if the user is asked "How do you use AI in your workflow?" and there's an existing answer for "What role does ChatGPT play in your development process?", that's a match.

If you find a match:
- Show the existing answer to the user
- Ask if they want to use it as-is, adapt it for this specific company/role, or start fresh
- If adapting, keep the core content and adjust details (company name, role-specific framing, tone)

If no match exists, move to Step 2.

## Step 2: Draft a new answer

Ask the user for their raw thoughts. They'll usually give you a rough verbal dump of what they want to say. Your job is to clean it up while keeping their voice.

Writing rules — these matter because the user has a specific style:
- Use simple words. Short sentences. If a sentence feels long, split it.
- No em dashes anywhere. Use a period or comma instead.
- No marketing speak. No "I am passionate about" or "I am excited to" or "proven track record."
- Write like an engineer talking to another engineer, unless the context is clearly non-technical.
- Keep answers concise. Most answers should be 2-4 sentences unless the question demands depth.
- Don't invent facts. Only use specifics (numbers, dates, company names) that the user provides or that exist in their personal-infos/ folder.
- Don't name companies that aren't well known. If the user worked at a startup or small company, replace the company name with "a previous job" or "my last role." Only name companies like Google, Meta, Amazon, Apple, Microsoft, or other names a reader would immediately recognize.

## Step 3: Save the answer

After the user approves the final version, save it to `interview-questions/` as a new markdown file:
- Filename: descriptive kebab-case based on the topic (e.g., `why-this-company.md`, `teamwork-example.md`)
- Format: question as H1 heading, answer below
- If this was an adaptation of an existing answer, save as a separate file — don't overwrite the original, because different framings are useful for different companies

## Notes on company-specific vs. generic answers

Some answers are generic (how you use AI, your development process). These get reused almost verbatim. Others are company-specific (why this role excites you, questions for the interviewer). For company-specific ones, the existing answer is a template showing the structure and tone — adapt the content but keep the pattern.

When the user is applying to a specific company, check if there's a resume already tailored for that company in `resumes/`. If so, read it — it contains the framing and keyword choices already made for that application, and your answer should be consistent with that framing.
