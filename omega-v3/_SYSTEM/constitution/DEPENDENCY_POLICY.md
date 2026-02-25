# DEPENDENCY POLICY — G — GOVERNANCE   
**Version:** 4.0   
**Status:** LAW   
**Purpose:** Defines the "Install Gate" protocols. The Agent must strictly adhere to these rules before adding any external code, tool, or service.

---

## 🛑 1. THE INSTALL GATE (Prime Directive)   
**Rule:** It is strictly forbidden to run `npm install`, `pip install`, `brew install`, or pull a Docker image unless the package is **first declared** in `deps.md`.

**The Sequence:**   
1.  **Identify Need:** Discover a gap that requires an external tool.   
2.  **Assess Risk:** Check the library's maintenance status, license, and size.   
3.  **Log Entry:** Create a new row in `deps.md` with a specific version pin.   
4.  **Update Capabilities:** If this adds a major capability (e.g., a database), add it to `stack.md`.   
5.  **Install:** Only *after* the file is saved, execute the install command.

---

## 📋 2. LEDGER REQUIREMENTS (`deps.md`)   
*The `deps.md` file must act as a precise inventory. Vague entries are not allowed.*

### Required Columns   
1.  **Package Name:** The exact name in the registry (e.g., `pandas`, `framer-motion`).   
2.  **Version Pin:** A strict version number (e.g., `2.1.0`).   
   *   *Prohibited:* Ranges like `^1.2.3` or `latest`.   
   *   *Reason:* Determinism. The build must work exactly the same way in 6 months.   
3.  **Rationale:** Why is this needed? (e.g., "Dataframe processing" is valid; "It's standard" is invalid).   
4.  **Used In:** Which part of the system imports it? (e.g., `backend/analysis/`).   
5.  **Risk/Owner:** Who maintains it? (e.g., "Meta", "Vercel", or "Random GitHub User").

### "No Bloat" Rule   
*   Before installing, ask: "Can this be done with a standard library or a simple script?"   
*   If the library is >5MB and used for one function, **reject it**.

---

## 🗺️ 3. CAPABILITY REGISTRY (`stack.md`)   
*While `deps.md` tracks code packages, `stack.md` tracks **Capabilities**.*

**When to update `stack.md`:**   
*   You add a **Service** (e.g., Supabase, Stripe, OpenAI).   
*   You add a **Core Tool** (e.g., Tailwind, Prisma).   
*   You change the **Runtime** (e.g., Node 18 -> 20).

**Format:**   
*   **Service:** Name | Auth Location (`.env`) | SOP Link   
*   **Trigger:** Cron / Webhook   
*   **Storage:** Database / Bucket

---

## 🔒 4. SUPPLY CHAIN SECURITY   
1.  **Trusted Sources Only:**   
   *   Prefer packages from official organizations (e.g., `@google-cloud/storage`).   
   *   Avoid packages with <100 stars or no updates in >12 months.   
2.  **License Compliance:**   
   *   **Permitted:** MIT, Apache 2.0, BSD, ISC.   
   *   **Flag for Review:** GPL, AGPL (Copyleft risk).   
   *   **Forbidden:** Proprietary/Commercial without a license key.   
3.  **Audit Protocol:**   
   *   Run `npm audit` or `pip check` before every major release (Phase completion).   
   *   Critical vulnerabilities block deployment.

---

## 🗑️ 5. REMOVAL & ARCHIVAL   
*When a tool is no longer used, it must be surgically removed.*

1.  **Uninstall:** Run the uninstall command.   
2.  **Clean Code:** Remove all imports and dead code paths.   
3.  **Archive Entry:** Move the row in `deps.md` from "Active" to "Archive/Removed".   
   *   *Log the date and reason for removal.*

---

**END OF POLICY**
