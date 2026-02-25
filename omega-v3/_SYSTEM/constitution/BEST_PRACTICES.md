# Ω — BEST PRACTICES
**Version:** 4.0
**Location:** `_SYSTEM/constitution/`
**Purpose:** Operational wisdom. How to work well, avoid common failures, and compound knowledge. This file is referenced by BUILD_PROMPT_TEMPLATE.md as required reading.

---

## 1. THE SPIRAL LOOP — HOW EVERYTHING MOVES

The system never moves in straight lines. Every action spirals upward through cycles of increasing precision. This applies to EVERYTHING: filling seed files, generating PRDs, building features, testing, fixing bugs.

```
     ┌──────────────────────────────┐
     │                              │
     ▼                              │
  GATHER ──► DIAGNOSE ──► GENERATE ──► PRESENT ──► APPROVE
     ▲                                                  │
     │                                                  │
     └──────────── REFINE (if gaps found) ◄─────────────┘
```

**Rules:**
- Each spiral produces a concrete, reviewable output
- Each spiral gets human review before the next begins
- If gaps are found at ANY point, loop back to GATHER — do not guess
- Apply the Prompter's 4-D (Deconstruct → Diagnose → Develop → Deliver) inside every spiral
- Spirals compound: each cycle builds on what the previous cycle proved

---

## 2. THE COMMAND PATTERN — HUMAN ↔ AGENT

The Pilot commands the Constructor. When the Constructor needs something, it commands the Pilot back. Communication is structured, never informal.

### Agent → Human (Requesting Input)
```
═══════════════════════════════════════════
  🧑‍✈️ PILOT INPUT REQUIRED
═══════════════════════════════════════════

  📌 What I need from you:
  - [Specific question or decision]

  💡 Why this matters:
  - [What depends on this answer]

  🔀 Options (if applicable):
  A) [Option and consequence]
  B) [Option and consequence]

  ⏳ Waiting for your decision.
═══════════════════════════════════════════
```

### Agent → Prompter (Self-Consultation)
Before generating ANY document, apply internally:
1. **Deconstruct** — What is the core objective? What context exists?
2. **Diagnose** — What's vague, missing, or could be misinterpreted?
3. **Develop** — Select the right technique (role assignment, context layering, positive framing, edge case handling)
4. **Deliver** — Produce with precision. Every word earns its place.

### When to use which:
| Situation | Pattern |
| :--- | :--- |
| Missing information that blocks progress | Command Human |
| Need a decision between options | Command Human |
| Generating a PRD, SOP, or Test Plan | Consult Prompter internally |
| Explaining what you built or why | Consult Prompter for structure |
| Hitting Circuit Breaker (3 failures) | STOP REPORT to Human |
| Unclear requirement that has multiple interpretations | Command Human with options |

---

## 3. FRAMEWORK PHILOSOPHY

These principles govern every decision in the system. They come from the source doctrine.

### Clarity Over Cleverness
Use plain language. No jargon for jargon's sake. If something can be said simply, say it simply. This applies to code comments, SOPs, PRDs, and communication with the Pilot.

### Action Over Theory
Every section of every document includes concrete deliverables: templates, checklists, acceptance criteria. This is not academic — it is a working system for builders.

### Honesty Over Polish
Tell the Pilot what is actually hard, what could go wrong, and what risks need managing. Surprises are worse than uncomfortable truths. This applies to STOP REPORTS, risk assessments, and test results.

### Structure Over Improvisation
Agents need clear prompts. Data needs proper schemas. Workflows need documented logic. Never improvise when a structure exists.

### Iteration Over Perfection
Phase 1 will not be perfect. That is fine. Build, test, learn, update. The system supports continuous improvement through the Spiral Loop, not one-and-done launches.

---

## 4. BEST PRACTICES BY PHASE

### Pre-Production Best Practices

**DO:**
- Read ALL seed files before forming any understanding
- Ask targeted questions — max 3 per round, each must materially change the output
- Propose a phased plan even if the user hasn't asked for one
- Ground every PRD requirement in seed files — cite the source
- Include edge cases and failure modes in every PRD
- Define "done" as a binary test (it passes or it doesn't)
- Present summaries before full documents so the user can course-correct early

**DO NOT:**
- Generate a PRD from incomplete context
- Assume the user wants the most complex solution
- Skip gap detection because the user seems confident
- Write SOPs after code (SOP always comes first)
- Leave acceptance criteria vague ("it should be fast" is not a criterion)

### Production Best Practices

**DO:**
- Write the SOP in `02_architecture/` BEFORE writing any code
- Build the walking skeleton first (end-to-end thin path that proves the architecture works)
- Follow IRONCORE strictly: Function → UX → Form
- Log every dependency with version pin and rationale BEFORE installing
- Make atomic commits — each commit does one verifiable thing
- Test as you go — do not defer testing to a separate phase
- Update STATE.md after every meaningful step

**DO NOT:**
- Install packages without deps.md entry (Install Gate)
- Write UI code before backend logic is tested (IRONCORE violation)
- Fix the same bug twice without updating the SOP
- Repeat a failed approach — each attempt must use a new hypothesis
- Skip handshake tests when integrating services
- Commit .env files or secrets to version control

### Testing Best Practices

**DO:**
- Test happy path, edge cases, error handling, security, and performance for every function
- Produce evidence for every test: logs, screenshots, response codes
- Run regression tests — fixing one thing must not break another
- For agentic systems: test capability boundaries, hallucination containment, prompt injection resistance
- Deliver actionable insights, not just pass/fail (root cause, recommendations, debt identified)
- Store evidence in timestamped folders: `04_tests/results/YYYY-MM-DD_phase_xx/`

**DO NOT:**
- Test manually when automation is possible
- Mark tests as "passed" without evidence
- Add new features during a testing phase (bug fixes only)
- Skip security testing because "it's just a prototype"
- Ignore performance until the end

---

## 5. KNOWLEDGE COMPOUNDING

The system learns from itself. Every project compounds knowledge for the next.

### What Gets Logged
| What | Where | When |
| :--- | :--- | :--- |
| Major decisions with rationale | `decision_log.md` | Every significant choice |
| Discoveries and learnings | `findings.md` | During build and testing |
| Bug fixes and their root causes | `progress.md` | During Repair Loop |
| Validated patterns and reusable assets | `06_vault/` | End of each phase |
| Version changes and their reasons | `00_admin/changelog.md` | Every release |

### The Vault (`06_vault/`)
When something is proven and tested, it gets archived in the vault:
- Validated code patterns
- Tested API contracts
- Working configuration templates
- Reusable SOP sections
- Proven agent prompts

The vault feeds into future projects via `_YOUR_PROJECT/kits/` and `_YOUR_PROJECT/skills/`.

### The Ideas Sandbox (`05_ideas/`)
Creativity is protected from the build. New ideas follow I.D.E.A.S:
- **I**nbox — Raw thoughts go in `inbox.md`
- **D**ivergence — Exploration in `candidates.md`
- **E**valuation — Ranked against mandates
- **A**bsorption — Validated ideas promoted to a Phase PRD
- **S**uspension — Not now, not lost → `parking_lot.md`

---

## 6. VERSIONING BEST PRACTICES

**DO:**
- Check for the latest version before each work session
- Archive old versions but keep them accessible
- Document why you made version updates in the changelog
- Use semantic versioning: MAJOR.MINOR.PATCH
- Tag releases for rollback capability

**DO NOT:**
- Work from outdated cached versions
- Skip version numbers without documenting why
- Make changes without updating the version number
- Delete old versions entirely

---

## 7. SECURITY BEST PRACTICES

**Immediate (minutes, not days):**
- Fill in all placeholder fields in SECURITY.xml (owner, contacts, dates)
- Install pre-commit hooks (gitleaks or detect-secrets) in every repository
- Confirm .env is in .gitignore

**Before any system goes live:**
- Complete the agent capability matrix for all agents
- Configure CI/CD security gates (npm audit / pip audit on every PR)
- Set up centralised logging (even basic)
- Test backup and restore (untested backup is not a backup)
- Walk through the kill protocol in staging

**Within 30 days of launch:**
- Complete the DPIA (Data Protection Impact Assessment)
- Document privacy policy and data retention schedule
- Table-top test the incident response plan
- Set up critical alerts from SECURITY.xml §7.4

---

## 8. COMMUNICATION BEST PRACTICES

When communicating with the Pilot, apply the Prompter's principles:

**Positive Framing:** Say what to do, not what to avoid. "Write in prose" instead of "don't use bullet points."

**Precision:** Every word earns its place. No padding, no filler, no "just to be thorough."

**Context Layering:** Environment → Task → Constraints → Output Format. The Pilot should know WHERE they are, WHAT is happening, WHAT limits apply, and WHAT they'll get.

**Grounding:** Base all statements on project files and evidence. Never say "it should work" — say "here is the test result."

**Edge Cases:** When presenting options or plans, include what could go wrong and what the fallback is.

**Directiveness:** Be specific. "Implement JWT authentication with 24-hour expiry using the jose library" is better than "add authentication."

---

## 9. ANTI-PATTERNS — WHAT THE SYSTEM NEVER DOES

| Anti-Pattern | Why It's Dangerous |
| :--- | :--- |
| Generating code before SOP exists | Logic has no documented source of truth |
| Installing packages not in deps.md | Uncontrolled dependency surface |
| Skipping CP-1 because context "seems clear" | Misunderstandings multiply downstream |
| Using "it works on my machine" as evidence | Not reproducible, not auditable |
| Building UI before Function is tested | IRONCORE violation — fixing a foundation under a house |
| Repeating a failed approach | Insanity loop — Circuit Breaker exists for this |
| Assuming context carries forward | LLMs have no persistent memory — restate essentials |
| Padding responses to seem thorough | Dilutes signal, wastes Pilot's time |
| Generating multiple options when one is asked for | Indecision disguised as thoroughness |
| Skipping security testing on prototypes | Prototypes become production faster than expected |

---

## 10. ACCESSIBILITY & INCLUSIVITY

**Accessibility is a functional requirement, not a nice-to-have. WCAG compliance applies from Phase 1, not as a post-launch fix.**

### Mandatory Standards
- **WCAG 2.1 Level AA** is the minimum for all web-based projects
- **WCAG 2.2 Level AA** is the target for new projects starting from 2025+
- Compliance is tested, not assumed — use Lighthouse, axe DevTools, or pa11y

### Build Practices

**DO:**
- Use semantic HTML elements (`<nav>`, `<main>`, `<article>`, `<button>`) — not `<div>` for everything
- Ensure all interactive elements are keyboard-accessible (Tab, Enter, Escape)
- Provide `alt` text for every meaningful image; use `alt=""` for decorative images
- Maintain a minimum 4.5:1 colour contrast ratio for normal text, 3:1 for large text
- Use `aria-label` and `aria-describedby` when semantic HTML alone is insufficient
- Test with a screen reader (VoiceOver on Mac, NVDA on Windows) at least once per phase
- Ensure focus indicators are visible — never remove `outline` without providing a replacement
- Provide skip-to-content links for keyboard users
- Ensure forms have associated `<label>` elements and meaningful error messages

**DO NOT:**
- Rely on colour alone to convey information (add icons, text, or patterns)
- Use `placeholder` text as a substitute for `<label>`
- Auto-play audio or video without user control
- Create interactions that require precise mouse movement (e.g., tiny click targets)
- Break zoom — pages must be usable at 200% browser zoom

### Internationalisation (i18n)
If the project serves multiple languages or may expand to them:
- Externalise all user-facing strings — no hardcoded text in components
- Use `lang` attributes on HTML elements
- Design layouts that accommodate text expansion (German/Finnish text is ~30% longer than English)
- Support RTL (right-to-left) layouts if Arabic, Hebrew, or similar languages are in scope
- Use `Intl` APIs for dates, numbers, and currency formatting

### Testing
- Add accessibility checks to the Test Plan Template (section 3, UX Tests)
- Lighthouse accessibility score must be ≥90 at CP-7 (Phase Complete)
- Screen reader walkthrough for all critical user flows at CP-9 (Test Results)

---
**END OF BEST PRACTICES**

