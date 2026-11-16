---
name: jh-inbox-tracker
description: Greet the user warmly by first name, sync Gmail and Google Calendar into Job_Tracker (updating the Applied column and interview stages), trigger Gemini Notebook stage prep, and save human-reviewed Gmail drafts without ever auto-sending (v2.2).
---
# JH Inbox Tracker (v2.2)

Keep `Job_Tracker` synchronized with Gmail and Google Calendar, greet the user warmly by their first name (extracted from their CV), track whether prepared jobs have been applied to yet, check in naturally once after interviews, and prepare unsent Gmail Drafts safely.

## When to Use

- At the start of every active run of `Job Hunt HQ by Sina` before scouting new jobs.
- Whenever the user asks about application replies, pending applications, upcoming tests/interviews, or recruiter emails.

## Steps

1. **Greet by First Name & Run Natural Human PA Check-Ins**:
   - Read the single `Agent_System/Agent_Memory` doc (never create `Agent_Memory v2` or duplicate state files!), recent Gmail (`newer_than:7d`), and Google Calendar (`[-24h, +14d]`).
   - Address the user warmly by their **First Name** from `Agent_Memory` (`"Hi Adam,"`, `"Morning Jacqueline,"` - never ask *"May I know your name?"* once their CV is uploaded).
   - If an interview, phone screen, or assessment finished recently (and is not yet marked `Asked_Once` or `Closed`), naturally ask once how it went right at the top of your reply, and immediately mark `Asked_Once` in `Agent_Memory` Section 2 so you never nag on later runs.
   - Only ask about quiet/sleep hours if `Agent_Memory` timestamps show the user set their schedule to **Hourly** (asking once if they prefer quiet hours while sleeping).

2. **Sync `Applied` Status & Stage Updates Into `Job_Tracker`**:
   - Search recent Gmail (`newer_than:7d`) and Calendar (`[-1d, +14d]`) for tracked company names in `Job_Tracker` (`Jobs` tab) plus confirmation/stage terms (`thank you for applying`, `application received`, `assessment`, `HireVue`, `SHL`, `interview`, `shortlisted`, `next stage`, `unfortunately`). Read matching threads in full.
   - **Auto-Update `Applied` Column**: Whenever Gmail shows an application confirmation (or the user tells you they applied), update that row's `Applied` column from `No - Ready to Apply` to `Yes - Applied (<Date>)` and `Status` to `Applied` via `sheets_agent:call`.
   - For roles still sitting at `Applied = No - Ready to Apply` from an earlier day, ask casually if they managed to submit them yet so `Job_Tracker` stays accurate.
   - **Next-Stage Trigger**: Whenever an email or Calendar invite confirms progression to an assessment, phone screen, or interview, update `Status` (`Assessment Due` or `Interview Scheduled`) and immediately run `jh-interview-prep` to push the job's materials into the **`Job Hunt HQ by Sina` Gemini Notebook**.

3. **Draft Emails Safely (NEVER Auto-Send)**:
   - Never call `gmail:send_message`, `gmail:reply`, or `gmail:forward`.
   - Save an unsent **Gmail Draft** (`gmail:create_draft`) for any needed recruiter reply or follow-up (3 to 4 crisp sentences), log 1 person per row on `Contacts` (`Draft Ready`), and share a clickable review link so the user checks and clicks Send themselves.

## Gotchas

- Never create duplicate `Agent_Memory` files, never claim `Job_Tracker` was updated without calling `sheets_agent:call`, and use zero em-dashes or en-dashes.
