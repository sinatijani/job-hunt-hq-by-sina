# Job Hunt HQ by Sina (v2.1)

**A £0, Zero-Setup Automated Career Assistant on Google Gemini Scheduled Tasks, Google Drive & Gemini Notebook**  
Created by **Sina Tijani** ([github.com/sinatijani](https://github.com/sinatijani)) | Repository: [`job-hunt-hq-by-sina`](https://github.com/sinatijani/job-hunt-hq-by-sina)

Job Hunt HQ by Sina works like a calm, organized human career assistant inside your own Google account at **£0 monthly cost**. While you sleep or work shifts, it scouts fresh UK and graduate openings, builds neat per-job folders with ATS-ready 1-to-2-page CVs (editable Google Doc + ready-to-upload PDF) and 1-page cover letters, tracks recruiter emails, checks in with you naturally after interviews, and syncs interview materials straight into a single **Job Hunt HQ by Sina** Gemini Notebook for live practice.

## Short, Simple Google Drive Layout (Created Automatically)

You do not create any folders, spreadsheets, or skills by hand. On its first run, the assistant sets up `My Drive/Job_Hunt_HQ_by_Sina/` with short, uncluttered names:

```text
My Drive/Job_Hunt_HQ_by_Sina/
├── Job_Tracker          (1 Google Sheet with 3 clean tabs: Jobs, Contacts, Summary)
├── My_CV_And_Docs/      (Drop your Master CV + transcripts, dissertations, or project notes here)
├── Applications/        (1 short-named folder per job, e.g. Unipart_Analyst/)
│   └── Unipart_Analyst/
│       ├── Job_Details          (Google Doc: full JD, apply link, company notes & 1-page cover letter)
│       ├── Master_CV_Copy       (Untouched snapshot copy of your Master CV)
│       ├── First_Last_CV        (Editable Google Doc CV, strictly 1 to 2 pages max)
│       ├── First_Last_CV.pdf    (Ready-to-upload PDF, strictly 1 to 2 pages max + 1-tap export link)
│       └── Interview_Prep       (Added automatically when invited to a test or interview)
└── Agent_System/        (Keeps Agent_Memory tucked away out of your working view)
```

## How It Works Across Your Whole Job Search

1. **Full Context Without Overwriting (`My_CV_And_Docs/`)**: Drop your Master CV plus any transcripts, dissertation or consultancy reports, and project notes. The assistant learns your real background and never alters your original files.
2. **Recruiter-Grade CV & Cover Letter Standards (`Applications/`)**:
   - **Strictly 1 to 2 A4 Pages for CVs & 1 A4 Page for Cover Letters**: Single-column, clean layout that parses cleanly in Workday, Greenhouse, and Lever, using Google's XYZ outcome formula without keyword stuffing or robotic AI jargon.
   - **Editable Doc + Ready PDF + Learns Your Edits**: Edit the Google Doc anytime; the assistant remembers your changes in `Agent_System/Agent_Memory` for future roles and gives you a ready PDF for portal upload.
3. **Gemini Notebook Live Interview Coach (`Job Hunt HQ by Sina`)**:
   - Whenever a morning Gmail/Calendar check sees you moved to the next stage (online test, phone screen, or interview), the assistant pushes that role's Job Description, your submitted CV, and live company research into one unified **Job Hunt HQ by Sina** Gemini Notebook.
   - It then gives you a **copy-paste company-scoped prompt** (so Gemini Notebook focuses on *that* exact company even when sources from multiple companies are in the notebook) and guides you to save a dedicated item in Gemini Notebook's **Studio** panel for quick review before your call.
4. **100% Human-in-the-Loop Safety**:
   - **Never Auto-Submits Portals**: Stops and shares clickable 1-tap links so you inspect your CV and apply on the company site yourself.
   - **Never Auto-Sends Emails**: Saves recruiter replies and follow-ups strictly as unsent **Gmail Drafts** so you review and click **Send** yourself.

## 60-Second Setup (Works on Android, iPhone, iPad, Windows & Mac)

1. **Turn On Google Workspace & Gemini Notebook Connectors**:
   - Inside Gemini (web or mobile app on Android or iPhone/iPad), tap the **menu button** (three horizontal lines in the top corner) or settings -> tap **Customize** (where you see Discover, Connectors, and Skills) -> tap **Connectors** -> switch **Google Workspace** and **Gemini Notebook** **ON**. Both use your existing Google account automatically with no separate sign-in needed.
2. **Create Your Scheduled Task**:
   - Go to **Scheduled** (Scheduled Tasks) -> **Create** -> name it **`Job Hunt HQ by Sina`**.
   - Set the time **5 minutes from now** and click **Save** (*do NOT click **Run now**, because Run now opens a separate one-off chat instead of starting your permanent assistant thread*). Once it wakes up and builds your folder, edit the schedule to **Daily at 07:00** and click **Save**.
3. **Paste `PROMPT.md`**: Copy everything inside `PROMPT.md`, paste it into the **Plan** box, and click **Save**.
4. **Drop Your CV & Reply `"Done"`**: Tap the link it gives you for `My_CV_And_Docs/`, upload your Master CV (plus any optional project reports), and reply `"Done"` with your target roles, preferred locations, visa status, and shift/sleep hours.
