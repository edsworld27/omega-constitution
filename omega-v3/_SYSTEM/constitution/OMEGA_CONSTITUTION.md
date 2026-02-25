# Ω — THE OMEGA FORMULA STACK (CONSTITUTION)   
**Version:** 4.0 (Canonical)   
**Status:** SUPREME DOCTRINE   
**Definition:** The Omega Formula Stack (ΩF·STACK) is a deterministic, security-first operating system for building reality. It enforces that **Function** is proven before **Motion** (UX), and **Motion** is proven before **Look** (Form).

---

## 🛑 0. PRECEDENCE OF LAW   
*If instructions conflict, this hierarchy determines the winner:*   
1.  **`SECURITY.xml`** (Supreme Override)
2.  **`00_rules.md`** (Project Mandates & Constraints) *— Generated at project init via `PROJECT_TEMPLATE.md`. Does not exist in the pack — created when the agent bootstraps a project.*
3.  **This Constitution** (Framework Definitions)
4.  **`OMEGA_PROMPTER.xml`** (Communication & Response Quality Standard)
5.  **`BEST_PRACTICES.md`** (Operational Wisdom & Anti-Patterns)
6.  **`AUDIT_PROTOCOL.md`** (Compliance Verification)
7.  **`ERROR_TAXONOMY.md`** (Error Classification & Repair)
8.  **`MULTI_SESSION_PROTOCOL.md`** (Session Continuity)
9.  **Architecture & SOPs** (Strategy)
10.  **Tools & Code** (Execution)

---

## 🟦 PART 1: Ω — O.M.E.G.A (The Preconditions)   
*Before a project moves, these five elements must exist.*

### O — Origin   
*   **Definition:** The singular intent of the system.   
*   **Artifact:** `02_project_brief.md`   
*   **Requirements:** Must define the "North Star," Non-Goals, and Constraints.   
*   **Paradigm Lock:** Must declare if the project is an **App** (Logic-First) or **Site** (Content-First).

### M — Mandates   
*   **Definition:** The non-negotiable laws and prohibitions.   
*   **Artifact:** `00_rules.md`   
*   **Scope:** Includes "Never-Do" lists, Halt Conditions, and the Circuit Breaker protocols.

### E — Environment   
*   **Definition:** The operational reality and file structure.   
*   **Artifacts:** `01_layout.md`, `.env` (local only), `.gitignore`, **`STATE.md`**.   
*   **State Rule:** The system must maintain `STATE.md` to track the current Letter and Phase. If `STATE.md` is missing, execution halts.

### G — Governance   
*   **Definition:** Control of dependencies, capabilities, and supply chain.   
*   **Artifacts:** `deps.md` (Ledger), `stack.md` (Registry).   
*   **The Install Gate:** No tool may be installed unless declared in `deps.md` with a version pin and reason.

### A — Awareness   
*   **Definition:** The system's memory and context connection.   
*   **Artifact:** `03_context_bridge.md`   
*   **Mechanism:** Links NotebookLM/LLM context to the project's source of truth. The system must distinguish between *known facts* and *assumptions*.

---

## 🟩 PART 2: F.O.R.M.U.L.A (The Engine)   
*The IRONCORE build order: Function → UX → Form.*

### F — Function   
*   **Definition:** The engine of value.   
*   **Paradigm A (Apps):** Logic, Data Schema, APIs, Auth.   
*   **Paradigm B (Sites):** Content Strategy, Sitemap, Information Architecture.   
*   **Rule:** Function must be proven (via tests) before UX begins.

### O — Observation   
*   **Definition:** Proof of work.   
*   **Artifact:** `04_tests/results/`   
*   **Rule:** "It works" is invalid. "Here is the log/screenshot" is valid.

### R — Repair   
*   **Definition:** The Self-Healing Loop.   
*   **Artifact:** `progress.md`   
*   **Protocol:** Analyze Error → Patch Code → Retest → **Update SOP**. Never fix the same bug twice without updating the process.

### M — Motion   
*   **Definition:** Usability, Flow, and Interaction Physics.   
*   **Scope:** Navigation, F-Patterns, Friction reduction, Error states.   
*   **Rule:** UX optimizes the *use* of the Function.

### U — Uniformity   
*   **Definition:** Standardization and Consistency.   
*   **Scope:** Naming conventions, directory structure, reuse patterns.

### L — Look   
*   **Definition:** Form and Aesthetics.   
*   **Scope:** Styling, Colors, Brand Assets (`07_assets/`).   
*   **Rule:** Applied last. Cannot fix broken Function or poor Motion.

### A — Archive   
*   **Definition:** Compounding Knowledge.   
*   **Artifact:** `06_vault/`   
*   **Action:** Validated assets are moved to the Vault. Release artifacts are tagged.

---

## 🟨 PART 3: S.T.A.C.K (Lifecycle & Control)   
*How the project moves through time.*

### S — Strategy   
*   **Definition:** Phased execution.   
*   **Artifact:** `01_phases/`   
*   **Rule:** One phase, one clear objective.

### T — Thresholds   
*   **Definition:** The Gates.   
*   **Artifact:** `PRD.md` (per phase).   
*   **Rule:** No Phase MVP build begins without an approved PRD defining Acceptance Criteria.   
*   **Timebox Rule:** Every PRD must define a "Time Appetite" (Effort Box). If the timebox expires, work halts for re-evaluation.

### A — Abstraction   
*   **Definition:** Separation of Concerns.   
*   **Artifacts:** `02_architecture/`, **`INTERFACES.md`**.   
*   **Rule:** `INTERFACES.md` defines the strict boundary between internal logic and external usage. Anything not listed there is not a contract.

### C — Control   
*   **Definition:** Deployment, Safety Triggers, and **Termination**.   
*   **Scope:** Rollback plans, Environment promotion (Dev -> Prod), and Kill Switches.   
*   **Kill Protocol:** A project/phase may be intentionally terminated ("Killed") if constraints change. This is a valid system state, distinct from failure.

### K — Knowledge   
*   **Definition:** The Learning Loop.   
*   **Artifact:** `findings.md` / `decision_log.md`   
*   **Rule:** Every major decision or discovery must be logged.

---

## 🟪 PART 4: I.D.E.A.S (Divergence)   
*The Sandbox for creativity that protects the Build.*

### I — Ideation   
*   **Artifact:** `05_ideas/inbox.md` (Raw thoughts).

### D — Divergence   
*   **Artifact:** `05_ideas/candidates.md` (Exploration of options).

### E — Evaluation   
*   **Action:** Ranking and selection against Mandates.

### A — Absorption   
*   **Action:** Validated ideas promoted to a Phase PRD.

### S — Suspension   
*   **Artifact:** `05_ideas/parking_lot.md` (Not now, not lost).

---

## 🟥 PART 5: S.E.C.U.R.E (The Binding)   
*See `SECURITY.xml` for the Supreme Law.*

### S — Secrets   
*   Never commit `.env`.

### E — Exposure   
*   Frontend/Backend Split. No keys in client.

### C — Containment   
*   Least Privilege. Input Validation.

### U — Update   
*   Dependency rotation and patching.

### R — Review   
*   Pre-push checks and audit gates.

### E — Enforcement   
*   **HALT** condition on any security ambiguity.

---

## 🔄 PART 6: OPERATIONAL PROTOCOLS

### 1. The Circuit Breaker (Anti-Loop)   
*   **Category-Tuned Limits:** See `ERROR_TAXONOMY.md` for per-category attempt limits (E1:2, E2:3, E3:4, E4:3, E5:1/HALT, E6:3, E7:2). Default Rule of 3 applies if unclassified.   
*   **New Hypothesis:** Never repeat a failed action identically.   
*   **Halt:** If limit reached, generate **STOP REPORT** and wait for human decision.

### 2. Version Control Doctrine   
*   **Atomic Commits:** Changes must be isolated and verifiable.   
*   **Tagging:** Releases must be tagged for rollback.   
*   **Changelog:** All meaningful changes logged in `00_admin/changelog.md`.

### 3. Legal Surface   
*   **Requirement:** `legal/` folder must be initialized (Privacy, Terms, License).   
*   **Constraint:** Legal mandates (e.g., Data Deletion) are treated as **Functional Requirements**, not documentation.

---

**END OF CONSTITUTION**
