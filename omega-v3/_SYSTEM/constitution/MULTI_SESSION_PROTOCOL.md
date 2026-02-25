# Ω — MULTI-SESSION PROTOCOL
**Version:** 4.0
**Location:** `_SYSTEM/constitution/`
**Purpose:** How to work across multiple AI sessions without losing context.

---

## THE PROBLEM

LLMs have no memory between sessions. Every new session starts from zero. Without this protocol, you lose: what was built, what was decided, what was tested, what failed and why.

## THE SOLUTION: STATE + HANDOFF

### Before Ending a Session
The agent MUST update:
1. **STATE.md** — Current phase, current checkpoint, current task, blockers
2. **progress.md** — Timestamped log of everything done this session
3. **decision_log.md** — Any decisions made and their rationale
4. **deps.md** — Any new dependencies added

If the user asks, generate a **Handoff Document** using `_SYSTEM/blueprints/HANDOFF_TEMPLATE.md`.

### Starting a New Session
The new session's ignition prompt should include:
1. "Read the constitution" (same as always)
2. "Read STATE.md" (tells you where we are)
3. "Read progress.md" (tells you what's been done)
4. "Read the active PRD" (tells you what we're building)
5. "Resume from [specific checkpoint or task]"

### Resumption Ignition Prompt
```
You are the OMEGA CONSTRUCTOR resuming an active project.

STEP 1: Read all files in _SYSTEM/constitution/ (same as fresh ignition).
STEP 2: Read _SYSTEM/blueprints/ for templates.
STEP 3: Read _YOUR_PROJECT/seed/ for project context.
STEP 4: Read STATE.md — this tells you where we left off.
STEP 5: Read progress.md — this tells you what's been done.
STEP 6: Read the active PRD in 01_phases/.
STEP 7: Read decision_log.md for past decisions.

Report your understanding:
- Current phase (Pre-Production / Production / Testing)
- Current checkpoint
- What's been completed
- What's next
- Any blockers from last session

Wait for my confirmation before proceeding.
```

### Drift Detection
After resuming, the agent must verify:
- [ ] STATE.md matches actual project files
- [ ] deps.md matches actual installed packages
- [ ] No files exist that aren't documented
- [ ] No SOPs are out of date with their code
- [ ] Seed files haven't changed since last session (compare against STATE.md snapshot)
- [ ] Kit configurations still match project type

If drift is detected, flag it immediately. If seed files changed, re-run CP-0 gap detection before continuing.

---
**END OF MULTI-SESSION PROTOCOL**
