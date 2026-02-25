# SOURCES.md — TRUTH HIERARCHY (A — AWARENESS)   
**Version:** 4.0   
**Status:** LAW   
**Purpose:** Defines valid sources of information. The Agent must strictly adhere to this hierarchy when resolving conflicts or seeking answers.

---

## 🏛️ 1. TIER 1: THE SUPREME COURT (Overrules Everything)   
*These files are absolute law. If external docs or training data conflict with these, these win.*

1.  **`SECURITY.xml`** (Security Constitution)   
2.  **`00_rules.md`** (Project Mandates)   
3.  **`deps.md`** (The Install Gate - if it's not here, it doesn't exist)   
4.  **`INTERFACES.md`** (The API Contract - if endpoint isn't here, it doesn't exist)
5.  **`OMEGA_PROMPTER.xml`** (Communication Quality Standard - how the agent structures responses)
6.  **`BEST_PRACTICES.md`** (Operational Wisdom - spiral loops, anti-patterns, compounding knowledge)
7.  **`AUDIT_PROTOCOL.md`** (Compliance Verification - how to audit projects against PRD and Constitution)
8.  **`ERROR_TAXONOMY.md`** (Error Classification - diagnostic repair protocols E1-E7)
9.  **`MULTI_SESSION_PROTOCOL.md`** (Session Continuity - how to resume across AI sessions)

---

## 🏗️ 2. TIER 2: PROJECT REALITY (The Current State)   
*The specific facts of this build.*

1.  **`02_project_brief.md`** (The Intent)   
2.  **`01_layout.md`** (The File Map)   
3.  **`STATE.md`** (The Current Position)   
4.  **Active PRDs** (`01_phases/xx/PRD.md`)

---

## 📚 3. TIER 3: VALIDATED KNOWLEDGE (The Vaults)   
*Reusable patterns and confirmed facts.*

1.  **`06_vault/kits/`** (Approved UI/SaaS/Automation patterns)   
2.  **`06_vault/knowledge_vault/`** (Snippets and lessons learned)   
3.  **NotebookLM Context** (Uploaded PDFs/Docs explicitly tagged as "Reference")

---

## 🌐 4. TIER 4: EXTERNAL VALIDATION (Allowed Lookup)   
*Where you are allowed to browse/search.*

1.  **Official Documentation Only:** (e.g., `nextjs.org/docs`, `stripe.com/docs`, `pypi.org`)   
2.  **GitHub Issues (Closed/Solved):** For debugging specific errors.   
3.  **Strict Constraint:** Do not trust StackOverflow answers older than 18 months without verification.

---

## 🛑 5. TIER 5: FORBIDDEN SOURCES (Hallucination Triggers)   
*You are strictly prohibited from relying on these for business logic or security.*

1.  **"Common Sense" or "General Knowledge":** Do not guess business rules. Ask the user.   
2.  **Unverified Tutorials:** Medium articles or random blogs.   
3.  **Implicit Assumptions:** "I assumed you wanted a user login" is a violation. Check the PRD.   
4.  **Mock Data as Truth:** Never treat `04_tests/fixtures` as production data.

---

## 🔄 6. RESOLUTION PROTOCOL   
*If Tier 1 conflicts with Tier 4 (e.g., Security Law conflicts with a Stripe Tutorial):*   
1.  **TIER 1 WINS.**   
2.  (Example: Stripe docs say "paste secret key", `SECURITY.xml` says "NEVER". You follow `SECURITY.xml`.)

**End of Truth Definition**
