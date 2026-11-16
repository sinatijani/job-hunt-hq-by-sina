---
name: jh-cv-builder
description: Build a strong Master CV from scratch through friendly guided questions, clean up or expand an incomplete CV, rename unclear uploaded files in My_CV_And_Docs, and create an editable Google Doc Master CV across any degree or profession (v2.2).
---
# JH CV Builder (v2.2)

Help users across any university department, trade, or profession who either do not have a CV yet, feel their current CV is incomplete or weak, or drop raw PDF/Word files into `My_CV_And_Docs/` that need clean naming and a complete editable Google Doc master copy.

## When to Use

- Automatically during onboarding whenever the user drops files into `My_CV_And_Docs/` (to rename unclear filenames cleanly and create a complete native Google Doc `<FirstName>_<LastName>_Master_CV` if they uploaded a PDF or Word file).
- Whenever a user says they do not have a CV yet, thinks their CV isn't strong enough, or wants to add missing degrees, modules, placements, part-time jobs, awards, publications, or skills.

## Steps

1. **Clean Up File Names & Create an Editable Master Google Doc in `My_CV_And_Docs/`**:
   - Inspect all files inside `Job_Hunt_HQ_by_Sina/My_CV_And_Docs/`.
   - Extract the user's real name from their CV (`First_Name` and `Last_Name` - never ask *"What is your name?"* if a CV or document already shows it!).
   - If an uploaded CV has a messy or generic filename (such as `Document(1).pdf`, `CV_final2.docx`, or `Copy of Resume`), rename it via `drive:update_file` to `<FirstName>_<LastName>_Master_CV.<ext>` (and rename unclear transcripts or certificates clearly, like `<FirstName>_<LastName>_Transcript.<ext>`).
   - If no native Google Doc version of the Master CV exists in `My_CV_And_Docs/` yet (for example, the user uploaded a PDF or `.docx`), create native Google Doc `<FirstName>_<LastName>_Master_CV` inside `My_CV_And_Docs/` containing **100% of the sections, roles, dates, bullets, education, awards, publications, and skills** from their uploaded CV without cutting anything out.

2. **Build or Strengthen a Master CV Through Guided Questions (When Needed)**:
   - If the user has **no CV yet** or asks for help improving a thin/incomplete CV, walk them warmly through 3 to 4 short, easy questions (one bite-sized step at a time if building from scratch):
     1. **Education & Standout Work**: Degrees, institutions, graduation dates, best coursework/projects/dissertation, and any scholarships, awards, or publications.
     2. **Work, Placements, Volunteering & Part-Time Roles**: Every job, internship, campus society role, or shift job they have held, plus concrete scale or results (volumes handled, time saved, accuracy, customers helped, teams supported).
     3. **Skills, Tools, Certifications & Languages**: Core domain tools, software, lab/clinical/creative/technical skills, licenses, and languages.
     4. **Contact Header**: City/Country, email, phone (optional), and LinkedIn/portfolio link.
   - Assemble their answers into `<FirstName>_<LastName>_Master_CV` (native Google Doc inside `My_CV_And_Docs/`, clean single-column layout, 1 to 2 A4 pages, strong ownership verbs + Google XYZ impact bullets in natural human English) using **only real facts provided by the user**.

3. **Suggest Tailored Role Directions Across All Relevant Fields**:
   - After reading or building `<FirstName>_<LastName>_Master_CV`, greet the user by their **First Name** and suggest a numbered list (`1, 2, 3, 4...`) of realistic target role types across **both** their latest study/work focus **and** their past transferable experience (works across any field: engineering, healthcare, design, finance, law, operations, marketing, software, research, analytics, or management), always making the final numbered option:
     - **`All of the above + any other roles my experience qualifies me for`**.

## Gotchas

- Never invent degrees, employers, dates, or metrics, never hardcode assumptions to one profession, and use zero em-dashes or en-dashes.
