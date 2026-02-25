# KIT AUTO-ACTIVATION CONFIG

**Kit:** Automation  
**Activates when:** `CONTEXT.md` → Project Type = Agentic Workflow  
**Subordinate to:** All Constitution files

## Files Included
- `AUTOMATION_KIT.md` — Workflow architecture, trigger types, platform patterns, error handling, retry strategy, scheduling, monitoring

## What This Kit Provides
The agent uses these patterns as starting points for:
- Workflow architecture (trigger → validate → process → output → log)
- Platform-specific patterns (n8n, Make, Zapier, custom agents)
- Error handling and retry strategies
- Dead letter queue design
- Circuit breaker for workflows
- Data flow security from SECURITY.xml
- Scheduling best practices with jitter
- Monitoring and alerting requirements

## Override Rules
- If AGENTS.md defines specific agent workflows, AGENTS.md wins for those agents
- If TECH_STACK.md specifies a platform, load only that platform's patterns
- If SECURITY.xml conflicts with any kit pattern, SECURITY.xml wins (always)
