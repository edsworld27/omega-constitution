# KIT GUIDE — HOW KITS WORK
**Version:** 4.0

**What:** Kits are pre-made project patterns. They give the agent a head start on structure, conventions, and checklists for specific project types.

**Where:** `_YOUR_PROJECT/kits/[kit-name]/`

**Rule:** Kits are subordinate to the Constitution. If a kit pattern conflicts with `SECURITY.xml`, `OMEGA_CONSTITUTION.md`, or `BEST_PRACTICES.md`, the constitution wins.

---

## Available Kits

| Kit | Folder | Use When |
| :--- | :--- | :--- |
| **Website** | `website/` | Marketing sites, landing pages, blogs |
| **SaaS** | `saas/` | Web apps, dashboards, auth + billing |
| **API** | `api/` | REST APIs, backend services, webhooks |
| **Automation** | `automation/` | n8n, Make, Zapier, agentic workflows |

## How To Use

1. Check `CONTEXT.md` → Project Type
2. The matching kit activates automatically via `kit.config.md`
3. The agent reads the kit's pattern file and uses it as a starting point
4. You can combine kits (e.g., SaaS + API for a full-stack app)

## Kit Structure

Each kit folder contains:
- `[KIT_NAME]_KIT.md` — The pattern file with checklists, templates, and conventions
- `kit.config.md` — Auto-activation config specifying when and how the kit loads

## Creating Your Own Kit

1. Create a new folder in `_YOUR_PROJECT/kits/[your-kit]/`
2. Create `[YOUR_KIT]_KIT.md` with patterns, checklists, and conventions
3. Create `kit.config.md` with activation trigger and override rules
4. Reference it in `CONTEXT.md`
5. The agent will use it alongside the Constitution
