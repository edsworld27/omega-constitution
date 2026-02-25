# KIT AUTO-ACTIVATION CONFIG

**Kit:** Website  
**Activates when:** `CONTEXT.md` → Project Type = Website  
**Subordinate to:** All Constitution files

## Files Included
- `WEBSITE_KIT.md` — Sitemap, SEO, performance, content, responsive, cookie consent, launch checklist

## What This Kit Provides
The agent uses these patterns as starting points for:
- Page structure and sitemap generation
- SEO implementation checklist
- Performance budget targets (Core Web Vitals)
- Content hierarchy for each page
- Responsive breakpoint definitions
- Cookie consent / GDPR compliance
- Pre-launch verification checklist

## Override Rules
- If CONTEXT.md specifies different performance targets, CONTEXT.md wins
- If BRAND.md specifies different breakpoints, BRAND.md wins
- If SECURITY.xml conflicts with any kit pattern, SECURITY.xml wins (always)
