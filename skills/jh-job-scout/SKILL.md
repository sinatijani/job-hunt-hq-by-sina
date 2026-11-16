---
name: jh-job-scout
description: Discover fresh graduate and early-career job openings, verify visa sponsorship and knockout-question eligibility, deduplicate against Job_Tracker in Job_Hunt_HQ_by_Sina, and score honest CV fit. Use during scheduled job-hunt runs or whenever the user asks to find, scout, filter, or shortlist new job openings.
---
# JH Job Scout (v2.1)

Discover fresh, high-fit job openings grounded in the user's real background inside `Job_Hunt_HQ_by_Sina/My_CV_And_Docs`, filter out duplicates and portal knockout traps, and log verified roles into `Job_Tracker`.

## When to Use

- During every active scheduled run of `Job Hunt HQ by Sina` after `Onboarding_Status` is `Active`.
- Whenever the user asks to find new roles, check fresh openings in a city or sector, or refresh their shortlist.

## Steps

1. **Read Candidate Ground Truth & Preferences First**:
   - Read `Agent_System/Agent_Memory`, the user's Master CV and supporting files in `My_CV_And_Docs/`, and `Job_Tracker` (`Jobs` tab) via `drive:read_file_content`.
   - Check `Section 3: Learned Preferences` in `Agent_Memory` so role selection honors user feedback, and extract all logged `Apply_Link` and `Company + Role` pairs to prevent duplicates.

2. **Target Fresh Direct-Employer Postings (`< 24 to 48 Hours` Priority)**:
   - Because corporate requisitions frequently receive hundreds of applicants within 24 to 48 hours and recruiters review early match tiers first, prioritize newly posted openings on official employer career portals (Workday, Greenhouse, Lever), NHS Jobs, Civil Service Jobs, Local Councils, university boards, and named graduate employers matching `Target_Roles` and `Preferred_Locations`.
   - Skip expired roles, unnamed agency spam, and stale reposted listings.

3. **Audit Portal Knockout Questions & Sponsorship Reality**:
   - Most rapid rejections come from automated portal knockout questions (visa sponsorship, right-to-work, location requirement, or mandatory minimum qualifications) rather than secret AI rejection bots.
   - Verify: (a) the user genuinely meets 100% of hard minimum/basic qualifications, and (b) when visa sponsorship or UK Graduate Visa transition matters, check UK Skilled Worker sponsor licensing vs. "no sponsorship" disclaimers and label clearly (`Verified Sponsor`, `Grad Scheme Open`, `PSW OK - Check Sponsor`, or `Skip - No Sponsor`).

4. **Prioritize Domain/Vertical Overlap & `>= 7.0 / 10` Fit**:
   - Hiring managers strongly favor candidates with even part-time, internship, or academic project exposure in a related industry vertical (such as logistics, healthcare, retail, finance, or public sector). Boost roles that align with the user's real project or shift-work industry domains, keeping only the **Top 3 to 5 roles** scoring `7.0 / 10` or higher.

5. **Log Cleanly Into `Job_Tracker` & Trigger Per-Job Folder Build**:
   - Append shortlisted roles to the `Jobs` tab of `Job_Tracker` with verified clickable `Apply_Link` URLs (`=HYPERLINK("URL", "Apply on Site")`), setting `Status` to `Shortlisted`.
   - Pass today's `#1` top match (and any role the user picks to apply for) to `jh-cv-tailor` to build its short-named folder inside `Applications/`.

## Gotchas

- Never invent job URLs, employer names, or sponsorship claims; copy every `Apply_Link` verbatim from live search results.
- If zero fresh roles above `7.0 / 10` appear today, report that plainly instead of padding `Job_Tracker` with weak fits.
