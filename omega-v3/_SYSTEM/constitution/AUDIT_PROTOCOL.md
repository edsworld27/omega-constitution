# Ω — AUDIT PROTOCOL
**Version:** 4.0
**Location:** `_SYSTEM/constitution/`
**Trigger:** When the user says "audit", "review", "check compliance", or "how does the project measure up"

---

## PURPOSE

The Audit Protocol compares the current state of the built project against three layers:
1. **PRD/MVP Compliance** — Does the build match what was planned?
2. **Constitution Compliance** — Does the build follow the system's rules?
3. **Quality Assessment** — Actionable insights for the Pilot.

---

## WHEN TO AUDIT

- On demand (user asks for it)
- Automatically at CP-7 (Phase Complete) — mini audit
- Automatically at CP-10 (Release Gate) — full audit
- After importing an existing project

---

## THE THREE-LAYER AUDIT

### Layer 1: PRD/MVP Compliance
Compare the project against the active PRD(s):

| Check | Method | Pass Criteria |
| :--- | :--- | :--- |
| Every MVP item built | Compare PRD checklist vs project files | All items present |
| Acceptance criteria met | Run each criterion's test | All pass with evidence |
| Non-goals respected | Check for scope creep | No unplanned features |
| Time appetite | Compare actual vs budget | Within tolerance |
| IRONCORE order followed | Check build sequence | Function tested before UX |

**Output:** MVP Scorecard (use `_SYSTEM/blueprints/MVP_SCORECARD_TEMPLATE.md`)

### Layer 2: Constitution Compliance
Compare the project against the constitution files:

| Check | Source | Pass Criteria |
| :--- | :--- | :--- |
| Folder structure | PROJECT_TEMPLATE.md | All required dirs exist |
| STATE.md current | OMEGA_CONSTITUTION.md | Exists and up to date |
| deps.md complete | DEPENDENCY_POLICY.md | Every installed package listed |
| INTERFACES.md exists | OMEGA_CONSTITUTION.md | Present if APIs exist |
| Security posture | SECURITY.xml | No .env committed, no keys in client, capability matrices defined (if agentic) |
| SOPs exist for code | BUILD_PROMPT_TEMPLATE.md | Every code file has SOP in 02_architecture/ |
| Test evidence exists | BUILD_PROMPT_TEMPLATE.md | 04_tests/results/ has evidence |
| Legal surface | OMEGA_CONSTITUTION.md | legal/ folder initialised |
| Sources respected | SOURCES.md | No Tier 5 (forbidden) sources used |
| Best practices followed | BEST_PRACTICES.md | No anti-patterns detected |
| Seed completeness | BUILD_PROMPT_TEMPLATE.md | Required seeds filled per Seed Activation Matrix; recommended seeds addressed or intentionally skipped |
| Accessibility | BEST_PRACTICES.md §10 | WCAG 2.1 AA minimum; Lighthouse accessibility ≥90 |

### Layer 3: Quality Assessment
Actionable insights, not just pass/fail:

- **Technical Debt Inventory:** What shortcuts were taken? What needs refactoring?
- **Security Gaps:** What's exposed? What needs hardening?
- **Performance Assessment:** Against budgets from CONSTRAINTS.md or PRD
- **Documentation Completeness:** What's missing or stale?
- **Recommendation Priority:** Ranked list of what to fix first

---

## AUDIT FOR IMPORTED PROJECTS

When a user imports an existing project (not built by this system), run a modified audit:

1. **Scan** — Read the project structure, identify what exists
2. **Map** — Compare against PROJECT_TEMPLATE.md, note what's missing
3. **Gap Report** — Present what the constitution requires that doesn't exist:
   - Missing STATE.md? → Generate it
   - Missing deps.md? → Scan package files, generate it
   - Missing SOPs? → Note which code has no SOP
   - Missing tests? → Note coverage gaps
4. **Remediation Plan** — Propose a phased plan to bring the project into compliance
5. **Present at CP-0** — Treat this as the Seed Scan for an existing project

---

## AUDIT OUTPUT FORMAT

```
═══════════════════════════════════════════
  Ω AUDIT REPORT
  Project: [Name]
  Date: [Date]
  Type: [PRD Audit / Constitution Audit / Full Audit / Import Audit]
═══════════════════════════════════════════

  📊 SCORECARD SUMMARY
  PRD Compliance:          [X/Y items] ([percentage]%)
  Constitution Compliance: [X/Y checks] ([percentage]%)
  Overall Health:          [GREEN / AMBER / RED]

  ✅ PASSING
  - [What's working well]

  ⚠️ WARNINGS
  - [Non-critical issues that should be addressed]

  ❌ FAILURES
  - [Critical issues that must be fixed]

  📋 PRIORITY ACTIONS
  1. [Most important fix]
  2. [Second priority]
  3. [Third priority]

  💡 RECOMMENDATIONS
  - [Strategic improvements]

  📈 TECHNICAL DEBT
  - [Shortcuts identified with remediation cost]

═══════════════════════════════════════════
```

---
**END OF AUDIT PROTOCOL**
