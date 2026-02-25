# Ω OMEGA CONSTITUTION PACK — v4.0

**The Seed System. Universal, security-first framework for building anything with AI.**

---

## Two Sides

**`_SYSTEM/`** — The agent's brain. **Do not edit.** 11 constitution files + 10 blueprints.
**`_YOUR_PROJECT/`** — Your project. **Edit freely.** Seeds, phases, kits, skills, MCPs.

---

## Folder Structure

```
omega-pack/
│
├── IGNITION_PROMPT.md               ← START HERE. Edit this. Choose your scenario.
├── README.md                        ← You're reading it
├── OMEGA_TRAINING_MANUAL.md         ← Full training guide (Markdown — canonical)
│
├── _SYSTEM/                         ← DO NOT EDIT
│   ├── constitution/                ← THE 11 LAWS
│   │   ├── SECURITY.xml             ← Supreme Law
│   │   ├── OMEGA_CONSTITUTION.md    ← Framework (OMEGA → FORMULA → STACK)
│   │   ├── OMEGA_PROMPTER.xml      ← Communication Standard
│   │   ├── BEST_PRACTICES.md       ← Operational Wisdom (spiral loops, anti-patterns, accessibility)
│   │   ├── AUDIT_PROTOCOL.md       ← How to audit projects (PRD + Constitution)
│   │   ├── ERROR_TAXONOMY.md       ← Error classification (E1-E7 + category-tuned circuit breaker)
│   │   ├── MULTI_SESSION_PROTOCOL.md ← Resume across AI sessions
│   │   ├── BUILD_PROMPT_TEMPLATE.md ← Instructor (phases + checkpoints + B.L.A.S.T. + context window)
│   │   ├── PROJECT_TEMPLATE.md      ← Folder structure generator
│   │   ├── DEPENDENCY_POLICY.md     ← Install gate
│   │   └── SOURCES.md              ← Truth hierarchy
│   │
│   └── blueprints/                  ← DOCUMENT TEMPLATES
│       ├── PRD_TEMPLATE.md          ← Product Requirements
│       ├── SOP_TEMPLATE.md          ← Standard Operating Procedures
│       ├── TEST_PLAN_TEMPLATE.md    ← Test Plans
│       ├── MVP_SCORECARD_TEMPLATE.md ← Phase completion scorecard
│       ├── HANDOFF_TEMPLATE.md      ← Session/developer handoff
│       ├── ROLLBACK_TEMPLATE.md     ← Deployment rollback plan
│       ├── AGENT_MD_TEMPLATE.md     ← Agent file structure (5-layer)
│       ├── AGENT_WORKFLOW_TEMPLATE.md ← Agent workflow diagram
│       ├── POST_MORTEM_TEMPLATE.md  ← Phase/project retrospective
│       └── COST_ESTIMATE_TEMPLATE.md ← Build + running cost estimate
│
└── _YOUR_PROJECT/                   ← YOU EDIT THIS
    ├── seed/                        ← PLUG-AND-PLAY (swap between projects)
    │   ├── CONTEXT.md              ← ⚡ REQUIRED — project definition
    │   ├── BRAND.md                ← Brand identity
    │   ├── TECH_STACK.md           ← Technology decisions
    │   ├── KNOWLEDGE.md            ← Domain knowledge base
    │   ├── AGENTS.md              ← Agent definitions (agentic only)
    │   ├── PERSONAS.md            ← User personas
    │   ├── CONSTRAINTS.md         ← Hard limits (budget, timeline, performance)
    │   ├── COMPETITORS.md         ← Market analysis
    │   ├── CONTENT.md             ← Content strategy (websites)
    │   └── METRICS.md             ← Success KPIs
    │
    ├── phases/                      ← Pre-define build phases
    │   ├── PHASE_TEMPLATE.md       ← Phase definition template
    │   └── example-taskflow/       ← ★ Complete reference project
    │
    ├── kits/                        ← Pre-made project patterns
    │   ├── KIT_GUIDE.md            ← How kits work
    │   ├── website/                ← Website Kit (SEO, performance, content, launch)
    │   │   ├── WEBSITE_KIT.md
    │   │   └── kit.config.md       ← Auto-activation config
    │   ├── saas/                   ← SaaS Kit (auth, billing, onboarding, multi-tenancy)
    │   │   ├── SAAS_KIT.md
    │   │   └── kit.config.md
    │   ├── api/                    ← API Kit (REST, pagination, webhooks, monitoring)
    │   │   ├── API_KIT.md
    │   │   └── kit.config.md
    │   └── automation/             ← Automation Kit (n8n, Make, Zapier, agents)
    │       ├── AUTOMATION_KIT.md
    │       └── kit.config.md
    │
    ├── skills/                      ← Agent capability extensions
    │   ├── SKILL_GUIDE.md
    │   ├── classifier-agent.md
    │   ├── writer-agent.md
    │   ├── analyst-agent.md
    │   ├── guardian-agent.md
    │   └── orchestrator-agent.md
    │
    └── mcps/                        ← MCP server config
        └── MCP_CONFIG.md           ← Config + 4 example servers
```

---

## How To Use

1. **Read** `OMEGA_TRAINING_MANUAL.md` for the full guide (or jump straight in below)
2. **Open** `IGNITION_PROMPT.md` — choose your scenario (fresh build, import, resume, audit, backend-only, frontend-only)
3. **Fill in** `_YOUR_PROJECT/seed/CONTEXT.md` (required) + any other seeds that apply
4. **Copy** the ignition prompt into your AI tool
5. **Follow checkpoints** — the agent pauses at every gate for your approval

---

*Built by Ed. Powered by the Ω-OMEGA·FORMULA·STACK.*
