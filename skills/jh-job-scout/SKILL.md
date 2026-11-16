---
name: jh-job-scout
description: Discover fresh job openings across any field or country, enforce the anti-pileup pending queue cap, verify salary and country-specific visa sponsorship, log every shortlisted role in Job_Tracker with an Applied status column, and automatically trigger per-job folder tailoring (v2.2).
---
# JH Job Scout (v2.2)

Discover fresh, verified job openings across any profession, degree background, or country grounded in `My_CV_And_Docs/`, prevent unapplied job pileups, write complete details (including **Company**, **Salary**, and **Sponsorship**) into `Job_Tracker`, and hand the top matches straight to `jh-cv-tailor` without stopping to ask permission.

## When to Use

- During every active run of `Job Hunt HQ by Sina` after target roles/preferences are set.
- Whenever the user asks to find new roles, check openings in a sector/location, or refresh their shortlist.

## Steps

1. **Read Ground Truth & Enforce the Anti-Pileup Queue Guard First**:
   - Read `Agent_System/Agent_Memory`, `<FirstName>_<LastName>_Master_CV` (and any extra docs in `My_CV_And_Docs/`), and `Job_Tracker` (`Jobs` tab) via `drive:read_file_content`.
   - Extract all previously logged `Apply_Link` and `Company + Role` pairs so duplicates are never logged.
   - **Anti-Pileup Check (`Applied` Column)**: Count how many prepared roles in `Job_Tracker` currently sit at `Applied = No - Ready to Apply`.
     - If **`3 or more` prepared roles are still unapplied** (and the user did not explicitly ask for brand-new roles right now), **do NOT pile on new jobs**! Instead, surface those waiting roles in a clean summary table with 1-tap `[Folder]`, `[PDF CV]`, and `[Apply Link]` links so the user never has to scroll up in chat, and ask warmly by first name whether they applied to any yet or want to skip any and pull fresh ones.
     - If **`fewer than 3` prepared roles are waiting**, proceed to Steps 2 to 5 below so their active ready-to-apply queue stays at a comfortable **1 to 3 roles**.

2. **Search Fresh Openings Across the User's Real Profession (`< 24 to 48 Hours` Priority)**:
   - Search official employer career portals (Workday, Greenhouse, Lever, SmartRecruiters), public-sector/healthcare/academic boards (such as NHS Jobs, Civil Service Jobs, HigherEd/university portals, local councils, or country equivalents), and named industry employers matching the user's actual field and `Target_Roles`.
   - Prioritize direct named employers over unnamed recruitment agencies. If a strong role comes from a recruitment agency without naming the end client, label `Company` transparently as `<Agency Name> (Unnamed Employer)`.

3. **Extract Mandatory `Salary`, `Company`, & Country-Aware `Sponsorship` Check**:
   - For every shortlisted role, capture **all** decision-critical facts (never hide Company or Salary behind a bare link!):
     1. **Company**: Exact employer name.
     2. **Salary**: Exact advertised salary/rate band (for example `£38,000 to £45,000/yr`), or write `"Not listed on advert"` if genuinely undisclosed - never omit the salary field!
     3. **Country-Specific Sponsorship & Knockout Check**: Adapt automatically to the job's country and the user's `Visa_And_Work_Context`:
        - **United Kingdom**: Check whether the employer holds an active UK Skilled Worker sponsor license / accepts Graduate Visa vs. states "no sponsorship available".
        - **United States / Canada / EU / Australia / Other Countries**: Check relevant work-visa sponsorship rules (H-1B/OPT, LMIA/PGWP, EU Blue Card, TSS, or local right-to-work disclaimers) and portal knockout questions (`100%` minimum qualification check).
        - Label clearly (`Verified Sponsor`, `Open / Grad-Friendly`, `Check Sponsor Policy`, or `No Sponsorship Stated`).

4. **Rank Up to 5 Roles & Highlight the Top 1 to 3 Strongest Fits**:
   - Keep up to **5 real, verified roles** scoring `>= 7.0 / 10` against `My_CV_And_Docs/`, clearly flagging which **1 to 3 roles** the user is most competitive for.

5. **Mandatory `Job_Tracker` Write + Automatic Handoff to `jh-cv-tailor` (Zero Lazy Stops!)**:
   - **Actually call `sheets_agent:call`** to append all shortlisted roles into `Job_Tracker` (`Jobs` tab) with `Company`, `Role`, `Salary`, `Location`, `Visa_Fit`, `Fit_10`, `Applied` (`No - Shortlisted` or `No - Ready to Apply`), and verified `=HYPERLINK("URL", "Apply on Site")`. **Never claim a role is in `Job_Tracker` without executing `sheets_agent:call` first!**
   - **Do NOT stop to ask *"Would you like me to tailor your CV now?"*** Immediately run `jh-cv-tailor` in the same run for the **top 1 to 3 highest-fit roles** (up to 3 total `No - Ready to Apply` folders) so the user receives finished application folders, Google Docs, and PDFs right away!

## Gotchas

- Never invent URLs, employers, salaries, or sponsorship statuses; every `Apply_Link` must come verbatim from live search results in the current run.
- Never hardcode role searches to one field; adapt 100% to the user's actual background and chosen role numbers.
