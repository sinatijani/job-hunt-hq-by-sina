# Job Hunt HQ by Sina (v2.2)

**A £0, Open-Source Agentic Career Assistant for Every Degree, Profession & Country**  
Created by **Sina Tijani** ([github.com/sinatijani](https://github.com/sinatijani)) | Repository: `https://github.com/sinatijani/job-hunt-hq-by-sina`

Job Hunt HQ by Sina turns **Google Gemini + Google Drive + Gemini Notebook** into an organized personal career assistant at **£0 cost**. Whether you studied engineering, healthcare, business, design, law, sciences, humanities, software, or analytics - and even if you do not have a finished CV yet - it helps you build or sharpen your Master CV, scouts fresh roles with salary and sponsorship checks, prepares submission-ready Google Doc + PDF CVs per job without gutting your experience, tracks whether you applied so jobs never pile up, and syncs interview prep straight into **Gemini Notebook**.

> **Important Consent & Data Notice**: This open-source workflow runs inside **your own** Google Gemini and Google Workspace account (the creator never sees your data). By using it and uploading your CV, you understand and consent that your AI assistant will read and process the personal details on your CV (such as your name, email, education, and work history) to find matching roles and tailor your applications. Please read `DISCLAIMER.md` before starting.

## Clean Google Drive Layout (Created Automatically)

You do not create any folders, spreadsheets, or skills by hand. On first run, the assistant sets up `My Drive/Job_Hunt_HQ_by_Sina/` with short, calm names:

```text
My Drive/Job_Hunt_HQ_by_Sina/
├── Job_Tracker          (Google Sheet with 3 tabs: Jobs [with Salary & Applied columns], Contacts, Summary)
├── My_CV_And_Docs/      (Drop your CV + transcripts or projects here; unclear filenames are auto-cleaned!)
├── Applications/        (1 flat folder per job: <Company>_<Short_Role>/)
│   └── <Company>_<Short_Role>/
│       ├── Job_Details                      (Google Doc: Company, Salary, Sponsorship, JD & 1-page Cover Letter)
│       ├── FirstName_LastName_Role_CV       (Editable Google Doc CV, 1 to 2 pages max, full non-scanty depth)
│       ├── FirstName_LastName_Role_CV.pdf   (Submission-ready PDF file ready to upload on the employer portal)
│       └── Interview_Prep                   (Added automatically when invited to an assessment or interview)
└── Agent_System/        (Holds your single Agent_Memory file tucked out of your way)
```

## Important Compatibility Notes: Regions, Plans, Schedules & Quotas

1. **Scheduled Tasks vs. Standard Chat (UK & Free Google Accounts Work Too!)**:
   - **Where Scheduled Tasks Is Available**: Google Gemini's **Scheduled Tasks** feature is currently available on paid tiers (**Google AI Plus, Pro, and Ultra**) in supported rollout regions (such as the US).
   - **If You Are in the UK or Using a Free Google Account**: If you do not see **Scheduled** in your Gemini menu yet, **everything still works!** All 5 `jh-*` Gemini Skills, Google Drive folders, `Job_Tracker`, PDF generation, and Gemini Notebook work on standard/free accounts. Simply paste `PROMPT.md` into a normal Gemini chat, **pin that chat**, and type **`"Continue"`** or **`"Any updates?"`** once a day whenever you want your assistant to check emails and prepare roles.
2. **Schedule Caution: Use Daily, NOT Hourly**:
   - Google AI Pro enforces a minimum schedule of **Daily**. Even if you have an **AI Ultra** plan that allows hourly runs, **do NOT set this task to Hourly**. Hourly runs send 24 notifications a day, pile up unapplied roles faster than any human can review them, and cause notification fatigue. Set it to **Daily** (for example `07:00 AM`), and message the chat manually anytime you want an extra check.
3. **Models & 5-Hour Quota Windows**:
   - Capable reasoning models (such as **Gemini 4 Argon** or **Gemini 4 Carbon**, when unlocked on your account) produce the sharpest CV tailoring and sheet updates, while standard models (such as **Gemini 4 Hydrogen**, **Auto**, or **Flash-Lite**) also work.
   - Free Google accounts have smaller 5-hour usage windows. Because progress is saved inside Google Drive (`Agent_Memory` and `Job_Tracker`), if your chat ever pauses at a 5-hour usage limit mid-run, just wait for your 5-hour window to refresh and type **`"Continue"`** in the exact same chat to pick right back up.

## 60-Second Setup Guide (Android, iPhone, iPad, Windows & Mac)

1. **Turn On Connectors**:
   - In Gemini, tap the **menu button** (three lines in the top corner) -> **Customize** (where you see *Discover, Connectors, Skills*) -> **Connectors** -> switch **Google Workspace** and **Gemini Notebook** **ON** (uses your same Google account automatically).
2. **Start Your Assistant**:
   - *With Scheduled Tasks*: Open **Scheduled** -> **Create** -> name it `Job Hunt HQ by Sina` -> set your first run **5 minutes from now** and click **Save** (*do NOT click Run now*; once it runs the first time, edit the schedule to **Daily at 07:00**).
   - *Without Scheduled Tasks (UK / Free Accounts)*: Open a **New Chat** in Gemini and **Pin** the chat.
3. **Paste `PROMPT.md`**: Copy all of `PROMPT.md`, paste it in, and press Send/Save. It automatically creates your Drive folders and installs all 5 `jh-*` skills (`jh-cv-builder`, `jh-job-scout`, `jh-cv-tailor`, `jh-inbox-tracker`, `jh-interview-prep`).
4. **Drop Your CV (or Build One From Scratch!)**:
   - Drop your CV (PDF, Word, or Doc) into `My_CV_And_Docs/` and reply **`"Done"`** (or if you don't have a good CV yet, reply **`"Help me build my CV"`**!).
   - The assistant cleans up your filename, saves an editable Master CV Doc, greets you by first name, gives you a quick numbered list of role options based on your background (including an **`All of the above`** shortcut), and immediately prepares your `Job_Tracker` + ready-to-apply folders with PDFs!

## One-Paste Skill Upgrades

Whenever a newer version of `Job Hunt HQ by Sina` is released here on GitHub, check the version header at the top of `PROMPT.md` (currently **`v2.2`**). If it is higher than yours, simply copy `PROMPT.md`, paste it into Gemini, and hit Enter: the assistant automatically detects older `jh-*` skill versions and upgrades all 5 skills in place without needing you to delete anything first.

## Repository Files

- `PROMPT.md` - Complete All-in-One Prompt (`v2.2`) with automatic skill installer & version upgrader.
- `DISCLAIMER.md` - Open-source AI CV-processing consent & human-review notice.
- `skills/` - Standalone `SKILL.md` files (`jh-cv-builder`, `jh-job-scout`, `jh-cv-tailor`, `jh-inbox-tracker`, `jh-interview-prep`).
- `LICENSE` - MIT License.
