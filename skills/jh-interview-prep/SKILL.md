---
name: jh-interview-prep
description: Research live company bottlenecks and hiring-manager priorities across any profession, save Interview_Prep inside Applications/<Company>_<Short_Role>, sync materials into the single Job Hunt HQ by Sina Gemini Notebook, and provide a company-scoped prompt plus Studio setup guide (v2.2).
---
# JH Interview Prep (v2.2)

Prepare candidates across any degree or profession to walk into assessments and interviews as a calm, capable "safe pair of hands", backed by `Interview_Prep` inside that job's Drive folder and live interactive prep inside their single **`Job Hunt HQ by Sina` Gemini Notebook**.

## When to Use

- Alongside `jh-job-scout` and `jh-cv-tailor` to craft 1 sharp Company Bottleneck Question per shortlisted role.
- Automatically whenever `jh-inbox-tracker` or the user flags progression to an online assessment, phone screen, portfolio/clinical/technical test, assessment centre, or interview.
- Whenever the user asks to prepare for an interview or salary conversation.

## Steps

1. **Research Live Company Reality & Role Priorities**:
   - Search the employer's website, recent news, annual/impact reports, product or service launches, and sector challenges from the past 12 months with clickable source links.
   - Frame prep around the **Hiring Manager Buyer Lens**: stressed hiring managers hire a coachable, detail-oriented "safe pair of hands" who understands their real problem rather than reciting textbook theory.

2. **Create `Interview_Prep` Inside `Applications/<Company>_<Short_Role>/`**:
   - Save native Google Doc `Interview_Prep` inside `Applications/<Company>_<Short_Role>/` containing:
     - **60-Second Employer Snapshot**: How the organization operates, recent priorities (with clickable source links), and team culture.
     - **4 Conversational STAR Stories**: Mapped to the user's real history in `My_CV_And_Docs/` and exact bullets on the `<FirstName>_<LastName>_<Short_Role>_CV` submitted for this role, written as natural spoken bullet cues.
     - **3 Role-Specific Practice Scenarios**: Tailored directly to the profession on the job description (whether engineering, healthcare, design, finance, law, operations, marketing, software, research, or analytics) with clear step-by-step walkthroughs.
     - **High-Signal Questions to Ask**:
       1. *Company Bottleneck Question* tied to live operations,
       2. *90-Day Team-Gap Question*: *"Looking at your current team, what is the biggest gap or priority you want this person to take off your plate in the first 90 days?"*,
       3. *Calm Salary-Band Script*: *"I've researched the market for this level and would love to hear the budgeted salary band you have in mind for the role."*

3. **Sync Into the Single `Job Hunt HQ by Sina` Gemini Notebook**:
   - Check `notebooklm:list_notebooks` for the single shared notebook titled **`Job Hunt HQ by Sina`** (create it once via `notebooklm:create_notebook` if missing; never create separate notebooks per company!). If Gemini Notebook is not turned on in Connectors yet, give simple steps (Gemini menu -> **Customize** -> **Connectors** -> switch **Gemini Notebook** ON across Android, iPhone/iPad, or web).
   - Check `notebooklm:list_sources` to avoid duplicates, then push 3 company-prefixed sources via `notebooklm:batch_create_sources`:
     1. `[<Company> - <Short_Role>] Job Description` (from `Job_Details`),
     2. `[<Company> - <Short_Role>] Submitted CV` (from `<FirstName>_<LastName>_<Short_Role>_CV`),
     3. `[<Company> - <Short_Role>] Interview & Employer Research` (from `Interview_Prep`).

4. **Provide Company-Scoped Gemini Notebook Prompt & Studio Guide**:
   - Share the clickable **`Job Hunt HQ by Sina` Gemini Notebook** link plus:
     - **Copy-Paste Gemini Notebook Prompt** explicitly naming `[<Company> - <Short_Role>]` so even when all sources across multiple companies stay selected, Gemini Notebook focuses strictly on *this* employer, role, and submitted CV for mock interviews and gap checks.
     - **Studio Tip**: Guide the user in 2 simple lines to open the **Studio** panel inside Gemini Notebook, create a **Study Guide**, **Briefing Doc**, or **Audio Overview** from those `[<Company> - <Short_Role>]` sources, and title it **`<Company> - <Short_Role> Prep`** so they can reopen it anytime in one tap.

## Gotchas

- Adapt every practice scenario to the user's actual field (never assume one profession), use zero em-dashes or en-dashes, and log the interview window in `Agent_Memory` Section 2 (`Upcoming`).
