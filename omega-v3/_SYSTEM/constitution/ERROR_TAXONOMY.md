# Ω — ERROR TAXONOMY
**Version:** 4.0
**Location:** `_SYSTEM/constitution/`
**Purpose:** Classification system for errors. Makes the Repair Loop diagnostic instead of guesswork.

---

## ERROR CATEGORIES

### E1: Configuration Error
**Symptoms:** Works locally, fails in another environment. Missing env vars. Wrong paths.
**Repair Protocol:**
1. Compare .env against .env.example
2. Check all path references are relative, not absolute
3. Verify environment-specific config (dev vs prod)
4. Run in clean environment to reproduce

### E2: Logic Error
**Symptoms:** No crash, but wrong output. Incorrect calculations. Wrong branching.
**Repair Protocol:**
1. Trace the logic flow step by step against the SOP
2. Add logging at each decision point
3. Compare actual vs expected at each step
4. Fix the logic AND update the SOP

### E3: Integration Error
**Symptoms:** API contract mismatch. Service timeout. Authentication failure. Schema drift.
**Repair Protocol:**
1. Compare request/response against INTERFACES.md contract
2. Test the external service independently (handshake test)
3. Check authentication credentials and scoping
4. Verify data format (JSON schema, field types, required fields)

### E4: Data Error
**Symptoms:** Null where expected. Wrong type. Missing fields. Encoding issues.
**Repair Protocol:**
1. Validate input data at the boundary
2. Check schema definitions against actual data
3. Add defensive checks (null guards, type coercion)
4. Add data validation tests

### E5: Security Error
**Symptoms:** Vulnerability found. Injection possible. Auth bypass. Secrets exposed.
**Repair Protocol:**
1. HALT immediately — security errors are CRITICAL
2. Assess blast radius (what could an attacker do?)
3. Fix the vulnerability
4. Check for similar patterns elsewhere
5. Update security tests
6. Log in incident report

### E6: Performance Error
**Symptoms:** Exceeds time budget. Memory leak. Database N+1. Payload too large.
**Repair Protocol:**
1. Profile to find the bottleneck (not guess)
2. Compare against CONSTRAINTS.md performance budget
3. Optimise the specific bottleneck
4. Re-measure to verify improvement
5. Add performance test to prevent regression

### E7: Dependency Error
**Symptoms:** Package conflict. Version mismatch. Deprecated API. Missing peer dependency.
**Repair Protocol:**
1. Check deps.md against actual installed versions
2. Run dependency audit (npm audit / pip audit)
3. Pin versions if floating
4. Update deps.md with resolution

---

## CIRCUIT BREAKER — CATEGORY-TUNED LIMITS

The standard Rule of 3 applies by default, but each error category has a tuned limit based on its nature:

| Category | Max Attempts | Rationale |
| :--- | :--- | :--- |
| **E1: Configuration** | 2 | Config fixes are binary — it's either the right value or it isn't. If 2 attempts fail, you're looking in the wrong place. |
| **E2: Logic** | 3 | Logic errors benefit from trace-based diagnosis. 3 hypotheses with stepped logging is usually enough. |
| **E3: Integration** | 4 | Integration issues often involve multiple moving parts (auth, format, timing). Extra attempt for handshake isolation. |
| **E4: Data** | 3 | Data validation is methodical. 3 attempts with progressive schema tightening. |
| **E5: Security** | 1 | **HALT immediately.** Do not attempt to self-fix security errors without human review. Generate STOP_REPORT. |
| **E6: Performance** | 3 | Profile → optimise → re-measure. 3 cycles is the limit before architectural review. |
| **E7: Dependency** | 2 | Version conflicts are deterministic. If 2 attempts fail, the dependency chain needs human decision. |

### Rules
1. **Each attempt must use a different hypothesis.** Repeating the same fix is not an attempt — it's a waste.
2. **Log each attempt** in `progress.md` with: hypothesis, action taken, result.
3. **On limit reached:** Generate a STOP_REPORT with all attempts documented and await human decision.
4. **Cross-category escalation:** If fixing one error reveals a different category, reset the counter for the new category.

### Edge Cases
5. **E5 override:** If the Pilot instructs you to proceed after an E5 HALT, you MUST log the override in `decision_log.md` with: who approved, why, what risk was accepted. Then proceed with the fix but run security tests immediately after.
6. **Ambiguous classification:** If an error could be E2 (Logic) or E3 (Integration), classify as the one with the higher attempt limit (E3:4) to give yourself more room. Log the ambiguity.
7. **Cascading errors:** If a single change triggers errors in multiple categories, address E5 first (security), then the root-cause category. Do not count cascading errors as separate attempts.

---

## CLASSIFICATION RULES

When an error occurs, classify FIRST, then repair:
1. Read the error message and stack trace completely
2. Identify which category (E1–E7) matches
3. Check the circuit breaker limit for that category
4. Follow that category's repair protocol
5. If the error spans categories, address the root cause category first
6. Log the classification in progress.md for knowledge compounding

---
**END OF ERROR TAXONOMY**

