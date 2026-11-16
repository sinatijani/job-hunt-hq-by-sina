---
name: jh-interview-prep
description: Research live company bottlenecks and hiring-manager priorities, save Interview_Prep inside Applications/<Company>_<Short_Role>, push the job description, submitted CV, and prep into the single Job Hunt HQ by Sina Gemini Notebook, and give a company-scoped Notebook prompt plus Studio setup guide.
---
# JH Interview Prep (v2.1)

Help the user walk into assessments and interviews as a calm, well-prepared "safe pair of hands", backed by a clean `Interview_Prep` Google Doc in that job's folder AND synchronized sources inside their single **`Job Hunt HQ by Sina` Gemini Notebook**.

## When to Use

- Alongside `jh-job-scout` and `jh-cv-tailor` to craft 1 sharp Company Bottleneck Question per shortlisted role.
- Automatically whenever `jh-inbox-tracker` or the user flags progression to an online assessment, phone screen, assessment centre, or interview.
- Whenever the user asks to prepare for an interview, technical test, or salary question.

## Steps

1. **Research Live Company Reality & Hiring Manager Psychology**:
   - Search the company's website, recent news, annual/ESG reports, product updates, and industry tensions from the past 12 months with clickable source links.
   - Frame all prep through the **Hiring Manager Buyer Lens**: stressed hiring managers hire a coachable, reliable "safe pair of hands" who understands *their* business problem rather than reciting generic textbook definitions.

2. **Create `Interview_Prep` Inside `Applications/<Company>_<Short_Role>/`**:
   - Save native Google Doc `Interview_Prep` inside that job's folder (`Applications/<Company>_<Short_Role>/`) containing:
     - **60-Second Company Snapshot**: How they make money, recent priorities (with clickable source links), and team culture style.
     - **4 Conversational STAR Stories**: Mapped to the user's real work/projects in `My_CV_And_Docs/` and exact bullets on the `<FirstName>_<LastName>_CV` they submitted for this role, written as natural spoken bullet cues.
     - **3 Role-Specific Technical or Case Drills**: Realistic SQL, Python, Power BI/Excel, forecasting, or operational scenarios matching the job description, with clear walkthroughs.
     - **High-Signal Questions to Ask (Bottleneck + Team Gap + Band)**:
       1. *Company Bottleneck Question* tied to live operations,
       2. *Hiring Manager Team-Gap Question*: *"Looking at your current team, what is the biggest gap or priority you want this person to take off your plate in the first 90 days?"*,
       3. *Calm Salary-Band Script* (when asked expectations): *"I've researched the market for this level and would love to hear the budgeted salary band you have in mind for the role."*

3. **Sync Materials Into the Single `Job Hunt HQ by Sina` Gemini Notebook**:
   - Check `notebooklm:list_notebooks` for the single unified notebook named **`Job Hunt HQ by Sina`** (create it once via `notebooklm:create_notebook` if not yet created; **never** create separate notebooks per company!). If Gemini Notebook is not connected in Gemini Connectors yet, give simple non-technical steps (Gemini menu -> **Customize** -> **Connectors** -> switch **Gemini Notebook** ON across Android, iPhone/iPad, or web).
   - Check `notebooklm:list_sources` on `Job Hunt HQ by Sina` to avoid duplicates, then push 3 clearly prefixed sources via `notebooklm:batch_create_sources`:
     1. `[<Company> - <Short_Role>] Job Description` (from `Job_Details`),
     2. `[<Company> - <Short_Role>] Submitted CV` (exact text/link of `<FirstName>_<LastName>_CV` used to apply),
     3. `[<Company> - <Short_Role>] Interview & Company Research` (from `Interview_Prep`).

4. **Give the User Their Company-Scoped Gemini Notebook Prompt & Studio Guide**:
   - Share the clickable link to **`Job Hunt HQ by Sina` in Gemini Notebook** plus:
     - **Copy-Paste Gemini Notebook Prompt** (explicitly naming `[<Company> - <Short_Role>]` so even when all sources across multiple companies stay selected in the notebook, Gemini Notebook locks strictly onto *this* company, role, and submitted CV for mock Q&A, gap checks, and follow-up drills).
     - **Gemini Notebook Studio Instruction**: Guide the user in 2 simple lines to open the **Studio** panel inside Gemini Notebook, generate a **Study Guide**, **Briefing Doc**, or **Audio Overview** from those `[<Company> - <Short_Role>]` sources, and rename/title that Studio item **`<Company> - <Short_Role> Prep`** so they can reopen that specific company's Studio file anytime in one tap.

## Gotchas

- Respect `Work_Shift_And_Sleep_Hours` in `Agent_Memory` when suggesting prep blocks, use zero em-dashes or en-dashes, and log the interview time in `Agent_Memory` Section 2 (`Upcoming`) for a natural post-interview check-in.
