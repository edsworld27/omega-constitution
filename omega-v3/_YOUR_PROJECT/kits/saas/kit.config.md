# KIT AUTO-ACTIVATION CONFIG

**Kit:** SaaS  
**Activates when:** `CONTEXT.md` → Project Type = Web Application  
**Subordinate to:** All Constitution files

## Files Included
- `SAAS_KIT.md` — Auth, billing, onboarding, dashboard, emails, multi-tenancy, usage tracking, settings

## What This Kit Provides
The agent uses these patterns as starting points for:
- Authentication and session management flow
- Auth security requirements (from SECURITY.xml)
- Billing and subscription tier structure
- Onboarding wizard design
- Dashboard layout patterns
- Transactional email templates
- Multi-tenancy data isolation
- Usage tracking and limit enforcement
- Settings page structure

## Override Rules
- If TECH_STACK.md specifies a different auth provider, TECH_STACK.md wins
- If CONTEXT.md specifies different subscription tiers, CONTEXT.md wins
- If SECURITY.xml conflicts with any kit pattern, SECURITY.xml wins (always)
