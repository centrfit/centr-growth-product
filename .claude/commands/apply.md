# Apply — Sr. Growth Product Manager

Generate the candidate's application file by combining their Claude Code usage data with their background.

## Steps

### Step 1: Get candidate info

Ask the user for the following. Collect all answers before proceeding:

1. **Full name**
2. **Email address**
3. **LinkedIn URL**
4. **Current role and company**
5. **2-3 most relevant professional experiences** — focus on subscription funnels, trial-to-paid conversion, paywalls and pricing, mobile (iOS/Android) and web subscription flows, activation and onboarding, experimentation, and growth analytics. Be specific: what was the business, what was your scope, what did you achieve?
6. **One paragraph on why this role interests you**

### Step 2: Read insights data

Read the user's Claude Code insights report. The report is located at `~/.claude/usage-data/report.html`.

If the file doesn't exist, tell the user:
> "No insights report found. Run `/insights` first to generate your Claude Code usage report, then come back and run `/apply` again."

Parse the HTML report and extract:
- **Stats:** Total messages, sessions, files touched, days active, messages per day
- **Project areas:** The "What You Work On" section — project names, session counts, and descriptions
- **Top tools used:** Tool name and count (e.g., Bash: 1787, Read: 614)
- **Languages:** Language and file count
- **Session types:** Type and count (e.g., Iterative Refinement: 39, Single Task: 27)
- **How they use Claude Code:** The narrative paragraph(s) from "How You Use Claude Code"
- **Impressive things:** Each item from "Impressive Things You Did" — title and description
- **Multi-clauding:** Whether they run parallel sessions, overlap count if available

### Step 3: Generate the application file

Using the candidate's name, create a file called `firstname-lastname.md` in the current directory (e.g., `jane-doe.md`). Use lowercase with hyphens.

Write the file with this structure:

```markdown
# [Full Name] — Sr. Growth Product Manager Application

**Date:** [today's date]

---

## Contact

- **Email:** [email]
- **LinkedIn:** [linkedin url]

---

## Background

**Current Role:** [current role and company]

### Relevant Experience

[Their 2-3 experiences, formatted as short paragraphs with specifics]

### Why This Role

[Their paragraph on why this role interests them]

---

## Claude Code Usage

- **Messages:** [X] | **Sessions:** [X] | **Days Active:** [X] | **Messages/Day:** [X]
- **Files Touched:** [X] | **Lines Changed:** [+X/-X]

### What I Work On

[For each project area from insights, format as:]

**[Project Name]** ([X sessions])
[Description from insights]

### Tools & Languages

**Top Tools:** [tool1] ([count]), [tool2] ([count]), [tool3] ([count]), ...
**Languages:** [lang1] ([count]), [lang2] ([count]), ...
**Session Types:** [type1] ([count]), [type2] ([count]), ...

---

## Impressive Things I've Built

[For each impressive thing from insights:]

### [Title]
[Description]

---

## How I Use Claude Code

[The narrative paragraph(s) from the insights report]
```

### Step 4: Confirm and instruct

After writing the file, tell the user:

> Your application file is ready: `[filename].md`
>
> **To submit:**
> 1. Review the file and make any edits you'd like
> 2. Upload it at: https://docs.google.com/forms/d/e/1FAIpQLScDOmZ5PMswxNzUU1_11GCPBguE48TJSTqCkX_hs8F65wR4Ug/viewform
>
> Good luck, and thanks for applying this way.
