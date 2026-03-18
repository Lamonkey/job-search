---
name: cold-outreach
description: |
  **Cold Outreach Email Writer**: Generates personalized cold outreach emails to hiring managers. Brief, conversational, research-driven emails that start conversations - not job applications.
  - MANDATORY TRIGGERS: cold outreach, cold email, reach out to hiring manager, outreach email, contact a company, write an outreach message
  - Also trigger when: user wants to email someone at a company about a role, "get in the door", reach out to a startup founder or engineering manager, "draft an email to this manager", "cold email about a role"
  - Use any time the user wants to write a cold outreach email to a hiring manager or company leader, even if they don't use those exact words.
---

# Cold Outreach Email Writer

You are writing a cold outreach email to a hiring manager. This is NOT a cover letter or a job application. It's a conversation starter - a brief, personalized message designed to get a 15-minute chat, not to land a job on the spot.

## Why this matters

Recruiters are drowning in inbound applications. Generic cold emails get deleted. But hiring managers - engineering managers, directors, team leads - are actively incentivized to find great people. They can fast-track candidates they believe in. Your email needs to reach these people and give them a reason to respond.

The difference between an email that gets a reply and one that gets trashed comes down to three things: personalization, brevity, and a clear ask.

## Core principles

**Be brief.** Three to five sentences max. This email is an invitation to talk, not a resume dump. Every sentence should earn its place.

**Be specific.** Reference something concrete about the person, their team, or their company. "I noticed your team is working on X" beats "I'm interested in your company" every time. Generic emails signal that you're mass-blasting, and mass-blasting signals desperation.

**Be conversational.** Write like you're emailing a smart colleague, not submitting a formal application. Drop the corporate speak. No "I'm writing to express my strong interest in..." - that's a cover letter opener, not how real people talk.

**Show, don't tell.** Instead of listing skills, mention what you've built. One specific accomplishment is worth more than a bullet list of technologies.

**Name-drop strategically.** Only mention a company name if it's recognizable enough to add credibility (e.g. Google, Stripe, a well-known startup). If the company name doesn't mean anything to the reader, skip it -describe what you did instead of where you did it. "I built observability tooling for a distributed backend" is stronger than "At [obscure company] I built observability tooling" because the reader's attention stays on the work, not on trying to place a name they don't recognize.

**Make a small ask.** "Would you be up for a 15-minute chat this week?" is perfect. Don't ask them to forward your resume, sponsor you for a role, or do anything that requires effort on their part.

## Step 0: Read the user's personal-infos folder

**Before writing anything, always read all files in the `personal-infos/` folder.** This is the source of truth for the user's background -work experience, projects, education, and personal details. Read every file in the folder so you have the complete picture before selecting which accomplishments to highlight.

The folder structure is:
```
personal-infos/
├── basics.md                    ← name, email, phone, location, LinkedIn, GitHub, education
├── experience_[company].md      ← one file per job
├── project_[name].md            ← one file per project
├── ai_workflow.md               ← how the user works with AI tools
└── interview_answers.md         ← reusable behavioral answers with real stories
```

When choosing what to include in the email, scan ALL experience and project files for accomplishments that are most relevant to the target person's team and role. Don't limit yourself to one file -the best value proposition often combines experience from multiple jobs or projects.

## Information gathering

With the user's background already loaded from `personal-infos/`, you only need to gather what's missing. Ask for whatever you don't already have:

1. **Who they're reaching out to** - the person's name, title, and company. If the user doesn't know the specific person, help them think about who the right target is (engineering manager > recruiter > VP).

2. **Why this company** - what specifically interests them about this company? A product they use, a blog post they read, a project the team is working on, a recent funding round. If the user isn't sure, prompt them: "What caught your eye about this company? Do you use their product? Have you seen any blog posts or talks from their team?" If the user doesn't know much about the company, do some quick research yourself (check the company's website, engineering blog, recent news) and suggest specific angles they could reference. A cold email with no personalization is a wasted email - help them find the hook.

3. **What the user brings** - pull from `personal-infos/` to find the strongest accomplishment or most relevant experience for this specific outreach. Select the 1-2 things that best connect to what the target person's team works on. If nothing in the files feels relevant enough, ask the user for more context.

4. **How they found the person** (optional but powerful) - through a blog post, a conference talk, a tweet, an open-source project, a mutual connection. This makes the opening feel natural rather than stalker-ish.

5. **Any common ground** (optional) - shared school, conference, open-source project, city, interests. Check `basics.md` for location and education that might overlap with the target person.

**Critical: never fabricate accomplishments.** Only use details that actually appear in the `personal-infos/` files or that the user provides directly. It's better to write a clearly marked placeholder than to invent credentials. The user's real story, even if modest, will always be more compelling than a fabricated one.

## Email structure

Follow this structure, but keep the whole thing to 3-5 sentences plus a sign-off:

### 1. Opening (1 sentence)
Reference something specific about the person or company. This is your proof that you've done homework.

Good openings:
- "I just read your team's blog post on migrating to event-driven architecture - the section on handling eventual consistency was especially interesting."
- "I've been using [Product] daily for the past year and noticed the recent redesign of the onboarding flow - it's a big improvement."
- "I saw your talk at [Conference] about scaling real-time data pipelines and it got me thinking about a similar challenge I tackled."

Bad openings:
- "I'm writing to express my strong interest in engineering at your company." (generic, formal)
- "I'm a senior software engineer with 8 years of experience." (leads with yourself, not them)
- "I noticed you're hiring for a backend role." (barely personalized)

### 2. Value proposition (1-2 sentences)
Briefly state what you bring to the table. Be specific - mention a project, a result, a technology. Connect it to what they're working on if possible.

Good:
- "I've spent the last two years building distributed systems at [Company], most recently leading a project that cut our API latency by 40% across 50M daily requests."
- "I built [Project] from scratch - it now handles [impressive metric] and I think the challenges are similar to what your team is tackling with [their project]."

Bad:
- "I have experience in Python, Java, AWS, Docker, Kubernetes, React, and machine learning." (tech-stack laundry list)
- "I believe I could contribute meaningfully to your team." (vague)

### 3. The ask (1 sentence)
A clear, low-commitment, yes-or-no question.

Good:
- "Would you be up for a quick 15-minute chat this week or next?"
- "Would you be open to a short conversation about how your team handles [specific challenge]?"

Bad:
- "Let me know if you'd like to discuss." (vague, no specific ask)
- "I'd love to interview for the open backend role." (too big an ask for a cold email)
- "Please find my resume attached." (this isn't an application)

### 4. Close
Keep it simple. "Best, [Name]" or "Thanks, [Name]". Optionally include a link to LinkedIn, GitHub, or personal site - but don't make it the centerpiece.

## Sample output

Here's what a good cold outreach email looks like:

> **Subject:** Your blog post on event sourcing
>
> Hi Sarah,
>
> I really enjoyed your team's recent post on adopting event sourcing at Acme - especially the tradeoffs you described around read model complexity. I've been working on a similar architecture at [Company], where I designed an event-driven pipeline processing 2M events/day for our billing system.
>
> Would you be up for a quick chat sometime this week? I'd love to hear more about how your team is approaching it.
>
> Best,
> Alex

Notice: it's five sentences. It's specific. It shows competence without being a resume. And the ask is small.

## What NOT to do

These patterns kill cold outreach. Avoid them:

- **The resume dump**: listing every technology you know, every job you've had. The email should make them curious enough to look at your LinkedIn - it shouldn't replace it.
- **The mass-blast**: anything that sounds like it could have been sent to 100 people. If you can swap out the company name and the email still makes sense, it's too generic.
- **The formal cover letter**: "Dear Hiring Manager, I am writing to express my interest..." This tone signals that you don't understand how cold outreach works.
- **The kitchen sink subject line**: "Contract Management, Business Operations, Program Management, Leadership, Strategy" - this is a real example of what not to do.
- **The desperate plea**: anything that positions you as someone who can't get a job through normal channels.
- **Attaching a resume**: this is a conversation starter, not an application.

## Subject line

The subject line should be specific and reference something real. It should look like an email a colleague would send, not a marketing blast.

Good: "Your blog post on event sourcing", "Quick question about [Product]'s recommendation engine", "Loved your PyCon talk on async patterns"

Bad: "Job Inquiry", "Software Engineer Looking for Opportunities", "Resume - Senior Developer"

## Tone calibration

Read the email out loud before finalizing. If it sounds like something you'd say to a friend-of-a-friend at a coffee shop, you're on the right track. If it sounds like something you'd read in a formal letter, rewrite it.

The email should feel like it was written by a real human who is genuinely interested in what this specific person or company is doing - because it was.
