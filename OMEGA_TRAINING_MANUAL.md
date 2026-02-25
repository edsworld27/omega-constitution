# Ω OMEGA CONSTITUTION PACK — TRAINING MANUAL
**Version:** 4.0   
**Format:** Markdown (Canonical version. `OMEGA_TRAINING_MANUAL.docx` is the legacy/printable edition.)

---

## 1. WHAT IS THE OMEGA CONSTITUTION PACK?

The Omega Constitution Pack is a **universal, security-first framework** for building software with AI. It governs how an AI agent plans, builds, tests, and ships a project — deterministically, with human oversight at every gate.

It is **not** a code library or a template. It is an **operating system for AI-assisted development**.

### What It Solves
- AI agents running ahead without oversight → **Checkpoint system (CP-0 to CP-10)**
- AI agents guessing at requirements → **Seed System + Spiral Loop**
- Uncontrolled dependency installation → **Install Gate**
- Security as an afterthought → **SECURITY.xml as supreme law**
- Lost context between sessions → **Multi-Session Protocol**
- Trial-and-error debugging → **Error Taxonomy (E1–E7)**

---

## 2. QUICK START (5 MINUTES)

### Step 1: Choose Your Scenario
Open `IGNITION_PROMPT.md`. Pick one:

| Scenario | When to Use |
| :--- | :--- |
| **A: Fresh Build** | Starting a new project from scratch |
| **B: Import Existing** | Bringing an existing project under constitution governance |
| **C: Resume Session** | Continuing work from a previous AI session |
| **D: Audit Only** | Checking an existing project against constitution standards |
| **E: Backend Only** | Frontend exists, building the backend |
| **F: Frontend Only** | Backend exists, building the frontend |

### Step 2: Fill in Your Seeds
Open `_YOUR_PROJECT/seed/CONTEXT.md`. Fill in at minimum:
- Project name
- Project type
- North Star (one sentence goal)
- Who it's for
- Non-goals

### Step 3: Paste the Ignition Prompt
Copy the chosen scenario's prompt from `IGNITION_PROMPT.md` into your AI tool (Claude, GPT, Cursor, Antigravity, etc.).

### Step 4: Follow Checkpoints
The agent will pause at every checkpoint (CP-0 through CP-10) and ask for your approval. Say "Confirmed" or "Approved" to proceed.

---

## 3. THE TWO SIDES

```
omega-pack/
├── _SYSTEM/          ← THE AGENT'S BRAIN (Do NOT edit)
│   ├── constitution/ ← 11 law files
│   └── blueprints/   ← 10 document templates
│
└── _YOUR_PROJECT/    ← YOUR SPACE (Edit freely)
    ├── seed/         ← Project definition files
    ├── phases/       ← Pre-defined build phases
    ├── kits/         ← Ready-made project patterns
    ├── skills/       ← Agent capability extensions
    └── mcps/         ← MCP server configuration
```

**Rule:** Never edit `_SYSTEM/`. Always edit `_YOUR_PROJECT/`.

---

## 4. THE SEED SYSTEM

Seeds are plug-and-play project definitions. Fill in the ones that apply to your project type:

| Seed File | Purpose | Required For |
| :--- | :--- | :--- |
| `CONTEXT.md` | ⚡ Project definition (mandatory) | Everything |
| `BRAND.md` | Brand identity, colours, typography | Websites, Mobile |
| `TECH_STACK.md` | Technology decisions | Apps, Agentic, API |
| `KNOWLEDGE.md` | Domain knowledge base | All (optional) |
| `AGENTS.md` | Agent definitions | Agentic workflows |
| `PERSONAS.md` | User archetypes | All (optional) |
| `COMPETITORS.md` | Market analysis | All (optional) |
| `CONTENT.md` | Content strategy | Websites |
| `CONSTRAINTS.md` | Hard limits | All (optional) |
| `METRICS.md` | Success KPIs | All (optional) |

**You don't need to fill everything.** The agent will ask about blank seeds at CP-1.

---

## 5. THE BUILD LIFECYCLE

### Phase A: Pre-Production (Planning)
No code. Only documents.

```
CP-0: Seed Scan → CP-1: Initialisation → CP-2: Environment →
CP-3: PRD Review → CP-4: SOP Review
```

### Phase B: Production (Building)
Code happens here. Follows B.L.A.S.T.:

```
Blueprint → Link (deps) → Architect (SOP first) → Stylize → Trigger (test)
CP-5: Dependency Approval → CP-6: Function Complete → CP-7: Phase Complete
```

### Phase C: Testing (Proving)
No new features. Only verification.

```
CP-8: Test Plan → CP-9: Test Results → CP-10: Release Gate
```

---

## 6. COMMANDS YOU CAN USE

These commands work at any point during a session:

| Command | What Happens |
| :--- | :--- |
| "Confirmed" / "Approved" | Pass the current checkpoint |
| "Stop" | Immediate halt |
| "Audit the project" | Run a full compliance audit |
| "Generate a handoff document" | Create a session handoff |
| "Estimate the costs" | Generate build + running cost estimate |
| "Run a post-mortem on Phase X" | What went well, what didn't |
| "Move to Testing phase" | Switch to Testing phase |
| "Generate an MVP scorecard" | Phase completion scorecard |
| "Jump to CP-X" | Skip to a specific checkpoint |
| "Classify this error using E1-E7" | Diagnostic error repair |
| "Add this to the IDEAS inbox" | Log an idea without building it |

---

## 7. KEY CONCEPTS

### IRONCORE Priority
**Function → UX → Form.** Always. Backend/logic works first, then usability, then styling. The agent will not build UI until function tests pass.

### The Spiral Loop
Everything spirals: `GATHER → DIAGNOSE → GENERATE → PRESENT → APPROVE → REFINE`. Each loop produces a concrete output and gets human review.

### The Install Gate
No package is installed without being logged in `deps.md` first with: name, version pin, rationale, usage location, and risk assessment.

### The Circuit Breaker
The agent gets category-tuned attempts to fix errors (E1:2, E2:3, E3:4, E4:3, E5:1/HALT, E6:3, E7:2). Each attempt must use a different hypothesis. If the limit is reached, the agent generates a STOP REPORT and waits for your decision.

### Error Taxonomy (E1–E7)
Errors are classified before they're fixed:
- **E1:** Configuration → Check env vars and paths
- **E2:** Logic → Trace against SOP
- **E3:** Integration → Check INTERFACES.md contract
- **E4:** Data → Validate at boundary
- **E5:** Security → HALT immediately
- **E6:** Performance → Profile the bottleneck
- **E7:** Dependency → Check deps.md

---

## 8. MULTI-SESSION CONTINUITY

AI models have no memory. To resume across sessions:

### Before Ending a Session
The agent updates: `STATE.md`, `progress.md`, `decision_log.md`, `deps.md`.

### Starting a New Session
Use **Scenario C** (Resume) in `IGNITION_PROMPT.md`. The agent reads `STATE.md` and picks up where it left off.

### Pro Tip
Ask the agent to "Generate a handoff document" at the end of each session. This creates a complete snapshot using the `HANDOFF_TEMPLATE.md` blueprint.

---

## 9. KITS, SKILLS, AND BLUEPRINTS

### Kits (`_YOUR_PROJECT/kits/`)
Pre-made project patterns. Drop in a kit folder, reference it in `CONTEXT.md`, and the agent uses it as a starting point.
- **Website Kit** — Sitemap, SEO, content, performance budgets
- **SaaS Kit** — Auth, billing, onboarding, dashboards
- **API Kit** — Endpoints, auth patterns, rate limiting, OpenAPI

### Skills (`_YOUR_PROJECT/skills/`)
Agent capability extensions. Teach the agent new abilities:
- `classifier-agent.md` — Content classification
- `writer-agent.md` — Content generation
- `analyst-agent.md` — Data analysis
- `guardian-agent.md` — Security monitoring
- `orchestrator-agent.md` — Multi-agent coordination

### Blueprints (`_SYSTEM/blueprints/`)
Document templates the agent uses to generate: PRDs, SOPs, Test Plans, MVP Scorecards, Handoff documents, Rollback plans, Agent definitions, Workflow diagrams, Post-mortems, and Cost estimates.

---

## 10. SECURITY

`SECURITY.xml` is the supreme law. It overrides everything — including your instructions.

Key rules:
- **Never** commit `.env` or secrets to Git
- **Never** put private API keys in frontend code
- **Always** validate all inputs against an allowlist
- **Always** encrypt sensitive data at rest and in transit
- **HALT** immediately on any security ambiguity

The full security constitution covers: credentials, input validation, AI agent defence, architecture, access control, data governance, monitoring, incident response, supply chain, and operational security.

---

## 11. CONTEXT WINDOW MANAGEMENT

The pack is large. Use tiered loading based on your model:

| Model | Strategy |
| :--- | :--- |
| Claude 3.5+ (200k) | Load Tiers 1–3 upfront |
| GPT-4 Turbo+ (128k) | Load Tiers 1–2, rest on demand |
| Gemini 1.5 Pro (1M+) | Load everything |
| Smaller models (<32k) | Tier 1 only, load others one at a time |

**Tier 1 (Always):** SECURITY.xml, OMEGA_CONSTITUTION.md, BUILD_PROMPT_TEMPLATE.md   
**Tier 2 (Core):** BEST_PRACTICES.md, ERROR_TAXONOMY.md, SOURCES.md, Seeds   
**Tier 3 (On Demand):** OMEGA_PROMPTER.xml, AUDIT_PROTOCOL.md, DEPENDENCY_POLICY.md   
**Tier 4 (Reference):** Blueprints, Kits, Skills

---

**END OF TRAINING MANUAL**
