---
name: jh-cv-tailor
description: Create per-job folders in Applications/<Company>_<Short_Role>, save Job_Details (with salary and sponsorship), build full non-scanty 1-to-2-page tailored CVs preserving transferable roles and sections as both Google Doc and real PDF file (FirstName_LastName_Role_CV.pdf), and remember user edits (v2.2).
---
# JH CV Tailor (v2.2)

Prepare a complete, submission-ready application folder per target role inside `Job_Hunt_HQ_by_Sina/Applications/` across any profession, preserving the full strength and depth of the user's real history while adapting ordering and transferable skills to the job description and uploading both the editable Google Doc and a real `.pdf` file.

## When to Use

- Automatically right after `jh-job-scout` shortlists roles (building complete folders for the top 1 to 3 strongest-fit roles without waiting to ask permission).
- Whenever the user selects another shortlisted role from `Job_Tracker`, pastes a job link, edits a CV Google Doc, or asks to tailor a CV or cover letter.

## Steps

1. **Read Full Master CV Context & Learned User Preferences**:
   - Read `<FirstName>_<LastName>_Master_CV` and all supporting documents inside `My_CV_And_Docs/`, plus `Section 3: Learned Preferences` in `Agent_System/Agent_Memory` (never create duplicate `Agent_Memory` files!).
   - Check `modifiedTime` on active CV Google Docs in `Applications/` against `Section 4` of `Agent_Memory` and user chat notes. Whenever the user edits a CV Doc or asks for changes, read their edits via `drive:read_file_content`, log durable preferences into `Agent_Memory` Section 3, and replace the `.pdf` in that folder with the updated version.

2. **Create a Flat, Short-Named Job Folder (`Applications/<Company>_<Short_Role>/`)**:
   - Create one folder directly inside `Applications/` named `<Company>_<Short_Role>` (2 to 4 short words max, such as `NHS_Data_Analyst` or `Arup_Civil_Engineer`; append city or `_2` if applying to two similar roles at the same employer).
   - **Do NOT save a redundant `Master_CV_Copy` inside each job folder** (the Master CV already lives cleanly inside `My_CV_And_Docs/`!).
   - Create native Google Doc `Job_Details` inside `<Company>_<Short_Role>/` containing:
     1. **Role Snapshot Header**: **Company Name**, **Exact Role Title**, **Location & Work Mode**, **Advertised Salary** (exact figure/band or `"Not listed on advert"` - never omit!), **Sponsorship / Right-to-Work Check**, and **Direct Apply Link**.
     2. **Full Job Description & Live Company Notes** (key priorities from their site/news + 1 smart Company Bottleneck Question).
     3. **Tailored Cover Letter (`<= 1 A4 Page`, 250 to 400 Words)** when helpful or requested (human/team-lead salutation, Competitor-Swap Hook in Paragraph 1, quantified proof in Paragraph 2, `City, Country` only; exceed 1 page only if academic/NHS/Civil Service explicitly requires a longer statement).

3. **Build `<FirstName>_<LastName>_<Short_Role>_CV` (Full, Non-Scanty, 1 to 2 Pages Max)**:
   - Use standard recruiter file naming: **`<FirstName>_<LastName>_<Short_Role>_CV`** (for example `Adam_Mensah_Operations_Manager_CV` - first/last name + target role + `CV`, underscores only, zero version numbers like `v2`/`final`, and never put the employer's company name in the CV filename).
   - **CRITICAL ANTI-GUTTING RULE (Never Make the CV Scanty or Bare!)**:
     - **Preserve every real core section** from the user's Master CV (`Personal Profile`, `Work Experience`, `Projects` [if present], `Education`, `Awards & Publications` / `Certifications` [if present], and `Skills`). **Never delete whole sections like Awards, Publications, or Education, and never throw out half the user's work history!**
     - **Reorder & Reframe Transferable Skills Instead of Deleting Roles**: Keep the user's real roles, employers, and dates 100% truthful (zero fabricated roles, titles, or years!). Place or emphasize the strongest matching roles/projects prominently with 4 to 5 sharp outcome bullets, and for other real roles, keep 2 to 3 solid bullets reframed around **transferable skills** (leadership, reliability, client/patient/stakeholder care, process speed, cost/error reduction, or analytical thinking) that prove readiness for this job!
     - Only condense very old roles (`10+ years ago`) to 1 to 2 lines if needed to keep the finished CV strictly within the **2 A4 page maximum** (aim for a rich, complete 1.5 to 2 pages when the Master CV has substantive history, or 1 crisp page if the Master CV itself is 1 page).
   - **Recruiter & ATS Quality Rules**:
     - Single-column layout (`10.5 to 11pt` clean font), zero multi-column tables, skill bars, icons, or headshots (unless local country norm explicitly requires one).
     - Intentional keyword mapping (mirror target role title in the top profile with parenthetical clarifiers when bridging title gaps; spell key domain terms out once; avoid repetitive keyword stuffing).
     - Calibrate language to the job's field (clear technical/clinical/domain terms where expected; plain commercial outcomes for management/operations roles) using ownership verbs + Google's XYZ formula (*Accomplished X as measured by Y by doing Z*) in natural human English with zero AI cliches.

4. **Generate & Upload the Real `.pdf` File Inside the Folder Before Replying**:
   - **Mandatory PDF Step**: Before finishing your turn, create and upload the actual PDF file **`<FirstName>_<LastName>_<Short_Role>_CV.pdf`** (`<= 2 pages`, selectable text, `< 2.5 MB`) directly inside `Applications/<Company>_<Short_Role>/`:
     - Export the Google Doc to PDF (if a Drive export tool is available) OR use Python (`reportlab` / `fpdf2` / `weasyprint`) to render the exact same formatted CV into a clean 1-to-2-page A4 PDF and upload it via `drive:create_file(title="<FirstName>_<LastName>_<Short_Role>_CV.pdf", mime_type="application/pdf", parent_id="<Job_Folder_ID>", text_content="", base64_content="<BASE64_OR_FILE_URI>")`.
     - Whenever the user later edits the Google Doc or asks for CV updates, remove/archive the previous PDF first (or move the old PDF out) and save the newly generated `<FirstName>_<LastName>_<Short_Role>_CV.pdf` so only the latest PDF sits in the job folder!
   - Also record the Google Doc's instant 1-tap PDF download URL (`https://docs.google.com/document/d/<Doc_ID>/export?format=pdf`) alongside the Drive `.pdf` file link.

5. **Update `Job_Tracker` (`Applied = No - Ready to Apply`) & Pause for Human Submission**:
   - Call `sheets_agent:call` to update the role's row in `Job_Tracker` (`Jobs` tab) with `Salary`, `Visa_Fit`, `Applied = No - Ready to Apply`, `Status = Folder & PDF Ready`, and clickable `Apply_Link`, `Folder_Link`, `CV_Doc_Link`, and `PDF_Link`.
   - Never auto-submit portals; present all details (including **Company**, **Role**, **Salary**, **Location**, **Sponsorship**, and clickable links) clearly in chat.

## Gotchas

- Never gut a rich Master CV into a bare skeleton, never invent roles/dates/facts, never skip uploading the `.pdf` file and updating `Job_Tracker`, and use zero em-dashes or en-dashes.
