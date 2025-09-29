# Marain Space — Development To-Dos

Scope: text-led website, services explainer dashboard, and MVP pipelines for each service. Goal = ship a clean v1 fast, with room to grow.

---

## 0) Project Setup

- Create mono‑repo with workspaces: `web/`, `data/`, `dash/`, `mvp/`.
- Choose stack: **Next.js + MDX + Tailwind** for site; **Streamlit** for explainer; **Python** for MVPs.
- Add `LICENSE`, `CODEOWNERS`, `CONTRIBUTING`, PR template.
- Configure Prettier, ESLint, TypeScript strict.
- Set up CI (GitHub Actions): lint, typecheck, build on PR.
- Add `.env.example` and secrets policy.

---

## 1) Content & IA (information architecture)

- Finalize page map: **Home**, **Thesis**, **Services**, **Case Studies** (stub), **Team** (stub), **Contact**.
- Convert approved copy to MDX files under `/web/content/*`.
- Create `services.json` (provided) under `/data/services.json`.
- Define site navigation, footer links and route slugs.
- Add favicon and a minimal logotype (wordmark).

---

## 2) Web Frontend (Next.js)

- Boot Next.js app with App Router and Tailwind.
- Set up global layout: typography scale (serif heads, sans body) and spacing rhythm.
- Create reusable components: `Prose`, `Divider`, `IconHeading`, `Callout`, `CTAButtons`.
- Implement pages:
  - **Home**: hero, beliefs, offer, promise, and call‑to‑action (MDX).
  - **Thesis**: long‑form manifesto (MDX, anchored headings).
  - **Services**: text‑led sections with anchors, populated from `services.json`.
  - **Case Studies**: placeholder grid (coming soon).
  - **Team**: placeholder bios (coming soon).
  - **Contact**: form to email webhook (or mailto for v1).
- Perform an accessibility pass (heading order, landmarks, focus states).
- Configure SEO: metadata, OpenGraph, canonical, `sitemap.xml`, `robots.txt`.
- Add custom **404** and **500** pages.

---

## 3) Services Explainer Dashboard (Streamlit or Web)

- Decide the host: a Streamlit app in `/dash` (fastest) or an in‑site React page.
- Load `services.json` and render cards with tabs: **Purpose**, **Inputs**, **Tools**, **Deliverables**, **Examples**.
- Create a **System Map** visualization (simple DAG: Insight → Strategy → Dialogue → Practice).
- Optional: add a “Which service fits me?” prompt box with basic LLM recommendation (reads JSON only).
- Export a static build (if Streamlit Cloud isn’t used) or link the dashboard from the Services page.

---

## 4) MVP Pipelines (Python)

Minimum: runnable notebooks, CLI scripts, sample data and README.

### 4.1 Mindstate Analysis (`/mvp/mindstate`)

- Notebook: ingest CSV text → clean → LLM extract narratives/metaphors → cluster → output `mindstates.json`.
- Optionally run BERTopic to validate clusters.
- Produce `mindstate_map.png` using NetworkX.
- Provide a README with run steps and caveats.

### 4.2 The Lens Infinite (`/mvp/lens`)

- Ingest sample tweets/news (mock data or API‑less CSV).
- Apply sentiment analysis (HF model), topic modeling (BERTopic/LDA) and LLM summarization.
- Output `insights.json`, a simple time‑series chart, and `lens_dashboard.html`.
- Include a bias/coverage warning section in the README.

### 4.3 Strategem Weavers (`/mvp/strategem`)

- Inputs: `mindstates.json`, `insights.json`, `org_purpose.md`.
- Use LLM prompts to produce `strategy_blueprint.json` (narratives, positioning, actions, risks).
- Create a simple radar or Sankey visualization of alignment.
- Include a README with prompt templates.

### 4.4 The Concord Table (`/mvp/concord`)

- Convert stakeholder text to LLM summaries (values, narratives, tone).
- Compute embedding similarity to create clusters and network graph edges by alignment.
- Output `alignment_map.json`, `shared_narratives.md` and `concord_dashboard.html`.
- Add a README with facilitation notes.

### 4.5 The Praxis Engine (`/mvp/praxis`)

- Define cultural KPIs and an example tracker schema (`kpis.csv`).
- Build a mock dashboard (Streamlit) with trend lines and “learning loop” notes.
- Include templates: Implementation Playbook (Markdown) and Training outline.
- Provide a README with an adoption checklist.

---

## 5) Data & Assets

- `/data/services.json` (done) — versioned, with documented schema.
- `/data/samples/*` for MVP notebooks (synthetic or public domain).
- Add TypeScript schema types for the services JSON.

---

## 6) Analytics, Consent, Privacy

- Add GTM and GA4 (baseline page and scroll depth events).
- Implement a consent management platform (CMP): CookieYes or OneTrust with GTM consent mode.
- Create a Privacy page (plain English) and starter Terms.
- Respect Do‑Not‑Track and default to minimal cookies.

---

## 7) Forms & Messaging

- Contact form: POST to a serverless function (Resend/SES) or use a mailto fallback.
- Implement success and error states with anti‑spam (hCaptcha or honeypot).
- Provide a plain‑English confirmation message.

---

## 8) Performance

- Achieve Lighthouse scores ≥ 95 for Performance, Accessibility, Best Practices and SEO.
- Optimize fonts (subset, use `display=swap`).
- Remove unused Tailwind classes (purge).
- Avoid heavy images; rely on typography and whitespace.

---

## 9) Deployment & DNS

- Deploy the web app to Vercel (or Netlify) and set environment variables.
- Configure the domain: `marain.space` DNS to Vercel; enable SSL automatically.
- Deploy the Streamlit app on Streamlit Cloud or a lightweight EC2 instance; link it from the Services page.
- Set up preview deployments for pull requests.

---

## 10) QA & UAT

- Test across browsers (Chrome, Safari, Firefox, Edge) and on mobile breakpoints.
- Proof content against approved copy.
- Perform accessibility checks (axe, keyboard navigation, color contrast).
- Run a link checker and verify 404 handling.

---

## 11) Post‑Launch Iteration

- Add Case Studies (2–3) with outcomes and artifacts.
- Add Team bios with short, human introductions.
- Add a Newsletter (Buttondown/Substack) — optional.
- Collect qualitative feedback and groom the backlog.

---

## 12) Backlog (Nice‑to‑Haves)

- Build an in‑site React version of the explainer dashboard (shared styling).
- Create a D3/Cytoscape knowledge graph for Mindstate Maps.
- Implement an admin CMS for MDX (Contentlayer or Notion sync).
- Add multi‑language support (i18n routing).
- Build an LLM “Ask Marain” Q&A trained on public pages.

---

## Acceptance Criteria (v1 ship list)

- Home, Thesis and Services pages live with approved copy.
- Services page renders dynamically from `services.json`.
- Explainer dashboard live and linked.
- At least **two** MVP notebooks runnable with sample data.
- GA4 and CMP working; site is accessible; Lighthouse ≥ 95.
- Deployed on a custom domain with SSL.

---

## Owners

- **Product/Content**: Naren
- **Web**: assign
- **Data/MVPs**: assign
- **Design/UX**: assign
- **DevOps**: assign