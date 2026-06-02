Update the HTML design artifacts with real product content derived from user research and PRD answers.

## Prerequisites check

1. Read `framework/user_research.md` — if it still contains only template placeholders (no real findings), tell the user to run `/research-sync` first and stop.
2. Read `inputs/prd-answers.md` — if it doesn't exist or fewer than 3 sections are answered, tell the user to run `/prd-interview` first and stop.

## Step 1 — Extract the key content

From `inputs/prd-answers.md`, extract:
- **Product name** (from answers header or section 1.1)
- **Target users / personas** (section 1.3)
- **Key pain points** (section 1.4)
- **Target-state workflow steps** (section 2.2)
- **MVP features** (section 2.3)

From `framework/user_research.md`, extract:
- **Persona names and descriptions** (section 3.5)
- **Top pain points with quotes** (section 3.3)
- **Jobs-to-be-Done** (section 3.4)

## Step 2 — Update `framework/mockups.html`

Replace placeholder content with real product context:
- Update the page `<title>` and any visible product name headings with the real product name
- In **Screen 1 (Dashboard)**: update the page title, subtitle count text, and table row content to reflect actual feature/document names relevant to this product
- In **Screen 2 (Editor)**: update the section navigation labels if the PRD sections differ; update the field placeholder text to reflect real input examples from this product
- In **Screen 3 (AI Generation)**: update the AI output text to reflect the actual top AI opportunities identified in section 1.5 of prd-answers.md
- Keep all CSS, layout, and component structure unchanged — only update visible text/content

## Step 3 — Update `framework/reusable_design_system.html`

Replace placeholder content with real product context:
- Update the page `<title>` and `<h1>` from "Design System" to "[Product Name] — Design System"
- Update the subtitle `<p>` to describe this product's component library
- In the **Table** example in the Components section: replace "AI PRD Drafting", "User Research Sync", "Design System Tokens" with 3 real feature names from section 2.3 (MVP features)
- Update the avatar initials and owner names to match the actual product owner from prd-answers.md metadata
- Keep all CSS tokens, component variants, and layout unchanged

## Step 4 — Note on `data_flow.html`

Do NOT modify `data_flow.html` in this step. It reflects the technical architecture (section 3.3), which requires the PM to complete section 3.3 in `/prd-interview` first. After section 3.3 is answered, the PM can ask Claude to regenerate data_flow.html or update it manually.

## Step 5 — Confirm

After both files are written, tell the user:
- What was updated in each file
- That they should open the files in a browser to review
- That `data_flow.html` needs to be updated separately after completing section 3.3
- That they can run `/generate-prd` once satisfied
