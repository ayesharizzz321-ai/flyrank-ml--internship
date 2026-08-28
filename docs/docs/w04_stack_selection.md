# Stack Selection Rationale & Evaluation (Three Roads)

**Track:** General AI Fluency | **Phase:** Build  
**Assignment:** Three Roads (Choose Your Stack)

---

## 1. Project Constraints

* **Budget:** Free only ($0 hosting, deployment, and infrastructure budget).
* **Skill Level:** Intermediate Data Science student (comfortable with Python, Pandas, Scikit-Learn, Markdown, and basic HTML/CSS/Git; minimal custom JavaScript backend experience).
* **Portfolio Objectives (Content Map & Sitemap):**
  * Display technical machine learning case studies with clean typography.
  * Render code snippets, evaluation metrics, confusion matrices, and ROC curves clearly.
  * Host static research papers and documentation.
* **Display & Dynamic Requirements:** Needs long-form reading support, image rendering for model evaluation charts, and embedded GitHub/Colab repository links. **Dynamic backend required?** No, not yet. All content is static documentation and project evaluation outputs.

---

## 2. Three Stack Options (Simplest to Most Powerful)

### Option 1: HTML/CSS Static Site hosted on GitHub Pages (Simplest)
* **How to build:** Write vanilla HTML/CSS pages manually for each case study.
* **Where to host:** GitHub Pages (Free).
* **Backend needed:** No.
* **Trade-off:** High manual overhead when adding new content; lack of systematic navigation components and automated markdown parsing.

### Option 2: MkDocs (Material) / Docsify static site hosted on GitHub Pages (Balanced / Chosen Front-Runner)
* **How to build:** Write case studies in standard Markdown (`.md`) files; MkDocs compiles them automatically into a responsive site.
* **Where to host:** GitHub Pages via GitHub Actions (Free).
* **Backend needed:** No.
* **Trade-off:** Minimal customization beyond theme settings, but provides instant technical search, zero-config code highlighting, and effortless maintenance.

### Option 3: Next.js + Tailwind CSS hosted on Vercel (Most Powerful)
* **How to build:** React-based frontend framework rendering MDX/JSON data.
* **Where to host:** Vercel Hobby Tier (Free).
* **Backend needed:** Optional API routes available, but unnecessary for current scope.
* **Trade-off:** High initial setup complexity and boilerplate code; ongoing maintenance overhead for npm dependencies and framework updates.

---

## 3. Pressure-Testing the Front-Runner (MkDocs on GitHub Pages)

* **What breaks if I pick the simplest (Option 1 - Vanilla HTML)?** Updating sitewide headers, footers, or code block styles requires editing every HTML file individually, making long-term maintenance tedious.
* **What do I maintain if I pick the most powerful (Option 3 - Next.js)?** Node packages, build pipeline errors, React state management, and continuous JS dependencies—taking time away from writing ML research content.
* **Can I finish in two weeks?** Yes. MkDocs builds directly from standard Markdown files in minutes.
* **Does it show my work properly?** Yes. It renders mathematical formulas, code blocks, technical tables, and evaluation images natively.

---

## 4. Stack Decision Rationale

### Chosen Stack: MkDocs (Material Theme) on GitHub Pages
I am choosing **MkDocs deployed on GitHub Pages**. Because my portfolio centers on machine learning case studies, research papers, and code implementations, Markdown is the fastest and cleanest format for my workflow. 

### Why I Rejected Options 1 and 3:
* **Vanilla HTML/CSS (Option 1):** Writing raw HTML layout wrappers for every single data science case study creates unnecessary friction. I need a framework that parses Markdown instantly so I can focus on documenting my models.
* **Next.js + Tailwind (Option 3):** While powerful, a full React application adds excessive component architecture overhead. It risks spending time troubleshooting JavaScript builds rather than refining my machine learning research.

### Evaluation Criteria:
* **Can I maintain this?** Yes. Adding a new case study is as simple as dropping a `.md` file into the `docs/` folder and pushing to GitHub.
* **Does it show my work well?** Absolutely. It formats technical prose, code blocks, metrics tables, and evaluation plots cleanly without requiring an active server backend.

---

## 5. Pass / Revise Checklist

- [x] **Three genuine options evaluated:** Vanilla HTML, MkDocs, and Next.js compared with trade-offs.
- [x] **Free & Matched to Needs:** Deployed free on GitHub Pages; optimized for data science technical writing.
- [x] **Honest Backend Decision:** Identified as "not yet" required for a static portfolio.
- [x] **Maintained Rationale:** Written in personal voice answering maintainability and work display requirements.
-
