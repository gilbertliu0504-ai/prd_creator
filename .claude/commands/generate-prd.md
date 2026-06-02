Generate the final PRD in two formats: `outputs/prd.md` (descriptive) and `outputs/prd.html` (interactive with embedded artifacts).

## Prerequisites check

1. Read `inputs/prd-answers.md` — must exist with answers for at least sections 1.1 through 2.3. If missing or sparse, tell the user to complete `/prd-interview` first.
2. Read `framework/user_research.md` — note whether it has been populated (real findings) or is still a template.
3. Read `framework/mockups.html`, `framework/reusable_design_system.html`, `framework/data_flow.html` — these will be embedded in the HTML PRD.

## Step 1 — Assemble content

Merge sources in priority order:
- **Section answers**: `inputs/prd-answers.md` is the primary source for all PRD section content
- **Research enrichment**: pull validated pain points, personas, JTBD, and recommendations from `framework/user_research.md` to enrich sections 1.3, 1.4, 1.5, and 2.1
- **Metadata**: use the header fields from `inputs/prd-answers.md` for owner, product, status, date

## Step 2 — Write `outputs/prd.md`

Produce a comprehensive, narrative Markdown PRD following the structure of `framework/PRD_Template.md`. For each section:
- Write prose that synthesizes the user's answers into complete, professional language — not raw Q&A
- Replace template italicized prompts with actual content
- For skipped sections, include the heading with a note: `_Pending — not yet answered._`
- At **Section 2.4** (Key Flows & Wireframes), include:
  ```
  > **Interactive wireframes:** `../framework/mockups.html`
  > **Design system reference:** `../framework/reusable_design_system.html`
  ```
- At **Section 3.3** (Tech Infrastructure), include:
  ```
  > **Architecture diagram:** `../framework/data_flow.html`
  ```

## Step 3 — Write `outputs/prd.html`

Produce an interactive HTML PRD. Requirements:

**Structure**: Mirror `outputs/prd.md` section for section, rendered as HTML with:
- The same CSS design tokens as `framework/reusable_design_system.html` (copy the `:root` block and base styles inline)
- A sticky left sidebar navigation linking to each major section (1–4 + Appendix)
- Section headings use the serif font (`.t-h1`, `.t-h2` classes from the design system)
- Tables rendered as styled `.table` elements
- Checklists rendered as styled checkbox lists

**Embedded artifacts** — at each location, render a full-width iframe with a caption:

At Section 2.4:
```html
<div class="artifact-embed">
  <div class="artifact-label">Wireframes &amp; UI Mockups</div>
  <iframe src="../framework/mockups.html" width="100%" height="600" frameborder="0" loading="lazy"></iframe>
</div>
<div class="artifact-embed" style="margin-top:24px;">
  <div class="artifact-label">Design System Reference</div>
  <iframe src="../framework/reusable_design_system.html" width="100%" height="500" frameborder="0" loading="lazy"></iframe>
</div>
```

At Section 3.3:
```html
<div class="artifact-embed">
  <div class="artifact-label">Architecture &amp; Data Flow</div>
  <iframe src="../framework/data_flow.html" width="100%" height="700" frameborder="0" loading="lazy"></iframe>
</div>
```

**Artifact embed styles** (add to the HTML `<style>` block):
```css
.artifact-embed {
  border: var(--border);
  border-radius: var(--r-md);
  overflow: hidden;
  background: var(--color-surface);
  box-shadow: var(--shadow-sm);
  margin: 24px 0;
}
.artifact-label {
  padding: 10px 16px;
  background: var(--color-gray-100);
  border-bottom: var(--border);
  font-family: var(--font-mono);
  font-size: 11px;
  text-transform: uppercase;
  letter-spacing: 0.08em;
  color: var(--color-text-muted);
}
.artifact-embed iframe {
  display: block;
  width: 100%;
}
```

## Step 4 — Confirm

After both files are written, report:
- File paths of `outputs/prd.md` and `outputs/prd.html`
- Which sections were populated vs. pending
- Whether research was incorporated (if user_research.md was populated)
- Instruction to open `outputs/prd.html` in a browser to review the embedded artifacts
