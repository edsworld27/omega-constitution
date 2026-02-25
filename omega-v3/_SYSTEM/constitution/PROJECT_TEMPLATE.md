# Ω — PROJECT BOOTSTRAP TEMPLATE   
**Version:** 4.0 (Canonical)   
**Usage:** The Agent must execute the "Generator Actions" below to initialize the project environment (E).

---

## 🛠️ 1. GENERATOR ACTION: FOLDER TREE   
*Create the following directory structure immediately. Do not ask for permission.*

```text   
project_root/   
├── 00_admin/               # Logs, decisions, and changelogs (A - Archive)   
├── 01_phases/              # Strategy & MVP iterations (S - Strategy)   
│   └── phase_01_foundation/# First phase (Auto-created)   
│       ├── mvp/            # Thresholds (T)   
│       └── build/   
├── 02_architecture/        # SOPs & Schemas (A - Abstraction)   
├── 03_tools/               # Deterministic Scripts (F - Function)   
├── 04_tests/               # Evidence & Proof (O - Observation)   
│   ├── results/            # Timestamped evidence bundles   
│   └── fixtures/   
├── 05_ideas/               # Divergence Sandbox (I - Ideation)   
│   ├── inbox.md   
│   ├── candidates.md   
│   └── parking_lot.md   
├── 06_vault/               # Knowledge Compounding (K - Knowledge)   
│   ├── kits/               # Active Kits   
│   └── knowledge_vault/   
├── 07_assets/              # Visuals & Media (L - Look)   
├── frontend/               # Client-Side (Hostile / NO SECRETS)   
├── backend/                # Server-Side (Trusted / SECRETS ALLOWED)   
├── legal/                  # Compliance Surface (Mandatory)   
└── .tmp/                   # Ephemeral workbench

--------------------------------------------------------------------------------

📄 2. GENERATOR ACTION: ROOT FILES   
**Create these files in the root directory with the specific content below.**   
File: `01_layout.md`   
****Content:**** Copy the "Folder Tree" text above into this file. Add the note: **"Status: IMMUTABLE. The Agent may not create folders outside this map without updating this file first."**   
File: `02_project_brief.md` (The Origin)   
****Content:****   
# 02_project_brief.md — O — ORIGIN   
**Status:** DRAFT (Must be approved by User)

## 1. The North Star   
(One sentence: What is the singular desired outcome?)

## 2. Project Type (Paradigm Fork)   
*Select one to define "Function":*   
- [ ] **Path A: Application** (Logic First)   
   - Function = Backend/Schema/API.   
   - Order: Function → UX → Form.   
- [ ] **Path B: Website** (Content First)   
   - Function = Content/Sitemap/SEO.   
   - Order: Structure → Navigation → Visuals.

## 3. Non-Goals   
(What will we NOT build?)

## 4. Core Constraints   
- Budget/Time:   
- Tech Stack:   
- Compliance:

File: `STATE.md` (The GPS)   
****Content:****   
# STATE — SYSTEM POSITION   
**Current Letter:** O — Origin   
**Current Subsystem:** OMEGA (Preconditions)   
**Current Phase:** Phase 01 — Foundation   
**System Status:** 🟢 ACTIVE | 🔴 HALTED   
**Last Action:** Initialization   
**Next Required Action:** Approve Project Brief

File: `03_context_bridge.md` (The Memory)   
****Content:****   
# 03_context_bridge.md — A — AWARENESS   
**Role:** Links NotebookLM/LLM Context to Project Reality.

## 1. Active Sources of Truth   
- [x] OMEGA_CONSTITUTION.md (Framework)   
- [x] SECURITY.xml (Law)   
- [ ] (Link to External Docs/PDFs)

## 2. Context Rules   
- Do not hallucinate APIs. Check `INTERFACES.md`.   
- Do not install tools. Check `deps.md`.

File: `deps.md` (The Install Gate)   
****Content:****   
# deps.md — G — GOVERNANCE   
**Rule:** No package installation without an entry here.

## Active Dependencies   
| Package | Version | Reason | Used In | Risk |   
| :--- | :--- | :--- | :--- | :--- |   
| (example) | (1.0.0) | (example) | (backend) | (Low) |

File: `stack.md` (The Registry)   
****Content:****   
# stack.md — CAPABILITIES   
## Active Kits   
- [ ] UI Website Kit   
- [ ] SaaS Kit

## Active MCPs / Integrations   
- (List APIs here)

File: `INTERFACES.md` (Boundary Contract)   
****Content:****   
# INTERFACES.md — A — ABSTRACTION   
**Rule:** Frontend may only call Backend endpoints listed here.

## Exposed Endpoints   
- (e.g., POST /api/v1/login)

File: `.gitignore` (Git Hygiene)   
****Content:****   
.env   
.env.local   
node_modules/   
__pycache__/   
.tmp/   
04_tests/results/*   
!04_tests/results/.keep   
.DS_Store

File: `.env.example` (Safe Config)   
****Content:****   
# DO NOT ADD REAL KEYS HERE. Structure only.   
API_KEY_OPENAI=   
DATABASE_URL=

--------------------------------------------------------------------------------

⚖️ 3. GENERATOR ACTION: LEGAL SURFACE   
**Initialize the legal/ folder with these empty placeholders to enforce compliance constraints. (Reference: Ironcore Legal Mandates)**   
• `legal/PRIVACY_POLICY.md` (Required for Data Minimization checks)   
• `legal/TERMS_OF_SERVICE.md`   
• `legal/COOKIE_POLICY.md` (Required for Prior Blocking checks)   
• `legal/DATA_RETENTION.md` (Required for Kill Protocol)   
• `legal/LICENSE.md`   
• `legal/THIRD_PARTY_NOTICES.md`

--------------------------------------------------------------------------------

🚦 4. GENERATOR ACTION: PHASE 1 GATE   
**Initialize the first mandatory gate.**   
File: `01_phases/phase_01_foundation/PRD.md`   
****Content:****   
# Phase 01 PRD — Foundation   
**Status:** DRAFT

## 1. Objective   
Establish the "Walking Skeleton" (Environment + Hello World).

## 2. MVP Definition   
- [ ] Repo initialized with Omega Structure.   
- [ ] Legal surface created.   
- [ ] CI/CD Pipeline (if applicable).   
- [ ] "Hello World" endpoint (Backend) or Page (Frontend) working.

## 3. Acceptance Criteria   
- [ ] Tests pass in `04_tests/`.   
- [ ] No secrets in Git.   
- [ ] `deps.md` updated.

## 4. Evidence Requirements   
- Screenshot of local run.   
- Log of test pass.

--------------------------------------------------------------------------------

**END OF TEMPLATE** **After executing these actions, report: "Ω System Initialized. Awaiting Project Brief approval."**
