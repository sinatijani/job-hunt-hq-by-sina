---
name: jh-cv-tailor
description: Build clean per-job folders in Job_Hunt_HQ_by_Sina/Applications, tailor 1-to-2-page ATS-readable CV Google Docs and submission PDFs plus 1-page cover letters using recruiter-proven XYZ mapping (never keyword stuffing or robotic jargon), and remember user edits. Use for top shortlisted roles or whenever preparing an application.
---
# JH CV Tailor (v2.1)

Create a clean, un-overwhelming application folder per job inside `Job_Hunt_HQ_by_Sina/Applications/`, producing a top-of-class 1-to-2-page CV (both editable Google Doc and submission-ready PDF) plus a 1-page cover letter when needed, grounded in real hiring research and the user's verified background.

## When to Use

- Automatically after `jh-job-scout` shortlists daily roles (adding 2 concise CV tweaks into `Job_Tracker` for shortlisted roles and building the full job folder for today's `#1` top match).
- Whenever the user chooses a role to apply to, shares a job posting, edits a CV Google Doc, or asks to tailor a CV or cover letter.

## Steps

1. **Read Full Candidate Context & Absorb Past User Edits**:
   - Read all files inside `My_CV_And_Docs/` (Master CV, transcripts, dissertations, consultancy/project reports, notes) plus `Section 3: Learned Preferences` in `Agent_System/Agent_Memory`.
   - Compare `modifiedTime` on active `<FirstName>_<LastName>_CV` Google Docs inside `Applications/` against `Section 4` of `Agent_Memory` (and check user chat feedback). Whenever the user edits a CV Doc or requests wording changes, read their edit via `drive:read_file_content`, log that preference in `Agent_Memory` Section 3 for future CVs, and refresh the PDF.

2. **Create a Short, Simple Per-Job Folder (`Applications/<Company>_<Short_Role>/`)**:
   - Keep folder and file names short (2 to 3 words max, such as `Unipart_Analyst` or `NHS_Data_Analyst` - never paste long 10-word job titles!).
   - Inside `Applications/<Company>_<Short_Role>/`, save:
     1. `Job_Details` (Google Doc: full job description, direct apply link, key company priorities, 1 bottleneck question, and a 1-page cover letter when helpful).
     2. `Master_CV_Copy` (untouched snapshot copied via `drive:copy_file` from `My_CV_And_Docs/` - never alter files inside `My_CV_And_Docs/`).

3. **Tailor `<FirstName>_<LastName>_CV` (Google Doc + PDF, Strictly Max 2 Pages)**:
   - Evaluate honestly whether the Master CV needs adapting for this job description: if it already fits cleanly, save it without unnecessary edits and tell the user. Otherwise, adapt it using these recruiter-proven rules:
     - **Strict 1-to-2 A4 Page Cap & Single-Column ATS Layout**: Never exceed **2 pages** (1 page if early-career history fits cleanly; max 2 pages with strongest relevant proof in the top third of Page 1; trim older/unrelated roles to 1 to 2 lines rather than spilling onto Page 3). Use a clean single-column layout (10.5 to 11pt standard font, standard headings: `Profile`, `Work Experience`, `Projects`, `Education`, `Skills`), UK/US hygiene (`City, UK` + plain-text right-to-work status; zero photos, DOB, marital status, skill bars, icons, or multi-column tables that break Workday/Greenhouse parsers).
     - **Intentional Keyword Mapping, Never Keyword Stuffing**: Map the posting's exact target job title (using a parenthetical clarifier like `Operations Intern (Analytics Focus)` when bridging title gaps) and core required skills to work the user *actually did*. Spell key technical terms both ways once (`Structured Query Language (SQL)`). Never cram repetitive JD buzzwords, which lowers interview rates by ~21%.
     - **Calibrate Tone to the Job (Zero Over-Technical AI Jargon Soup)**: Adapt conciseness to the target audience - keep exact methods clear for technical roles, and translate academic/technical jargon into plain commercial outcomes for business/operations roles. Balance **technical credibility, business impact, and ownership** so the candidate reads as a "safe pair of hands".
     - **Google XYZ Formula + Speakable Human English**: Write 3 to 5 bullets per recent role starting with strong ownership verbs (`Built`, `Automated`, `Reduced`, `Analyzed`, `Led` - never passive `Helped`/`Worked on`, and never robotic AI cliches like `Spearheaded`, `Orchestrated`, `Synergized`, `Tapestry`, or `Landscape`). Frame bullets as *Accomplished [X] as measured by [Y: %, time saved, volume, accuracy] by doing [Z]*, keeping only natural language the user can defend out loud in an interview. Briefly explain any career pivot or short stint in 1 calm line so recruiters never guess negatively.
   - **Export Submission PDF (`<= 2 Pages`, `< 2.5 MB`)**: Save selectable-text PDF `<FirstName>_<LastName>_CV.pdf` inside `Applications/<Company>_<Short_Role>/` when PDF export/upload tools are available, AND always record the live 1-tap Google Docs PDF download link (`https://docs.google.com/document/d/<Doc_ID>/export?format=pdf`) in `Job_Tracker` (`PDF_Link`) and chat.

4. **Draft a 1-Page Cover Letter (Strictly Max 1 A4 Page, 250 to 400 Words)**:
   - Standard UK/global cover letters must **never exceed 1 A4 page** (3 to 4 short paragraphs, 250 to 400 words; only exceed 1 page if an academic, teaching, NHS, or Civil Service advert explicitly specifies a longer supporting statement):
     - **Salutation**: Address a named hiring manager or team lead (`Dear [Name / Analytics Team Lead],`) rather than `Dear Recruiter`.
     - **Paragraph 1 (Competitor-Swap Hook Test)**: Open on a specific operational challenge or priority unique to *this* company (if swapping in a competitor's name still makes sense, rewrite the hook!).
     - **Paragraph 2 (Quantified Proof Story)**: Share 1 to 2 quantified stories adding context behind the CV rather than repeating bullets word-for-word.
     - **Paragraph 3**: Confident, polite close (`City, UK` only - never include full street address).

5. **Link & Pause for Human Review (Never Auto-Submit)**:
   - Update `Job_Tracker` (`Jobs` tab) with clickable `Apply_Link`, `Folder_Link`, `CV_Doc_Link`, and `PDF_Link`, set `Status` to `Ready to Submit`, log `modifiedTime` in `Agent_Memory` Section 4, and stop so the user checks everything and submits on the portal themselves.

## Gotchas

- Never exceed 2 pages on any CV or 1 page on any standard cover letter, never invent unverified facts or numbers, and use zero em-dashes or en-dashes.
