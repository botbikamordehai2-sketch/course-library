# NEXUS Recommendations

Every item is NEXUS_IDEA. Nothing here has been implemented.

---

### 1. Diagnose and fix the Playwright MCP connection gap

- **Why:** `.mcp.json` declares a Playwright MCP server; it's not
  callable in this session (`ToolSearch` confirmed no playwright/
  browser tool exists). This blocks any future task that assumes
  browser access, as already happened twice this session
  (`SCAN_CLAUDE_CODE_COURSES_WITH_SUBSCRIBER_ACCESS`,
  `RESCAN_MCP_COURSES`).
- **Source evidence:** direct observation this session (`ToolSearch`
  + reading `.mcp.json`), not from the Microsoft/OpenAI research —
  this recommendation is NEXUS-internal, surfaced *while* doing the
  ecosystem research, not derived from it.
- **Complexity:** Low–Medium (likely a client reconnect and/or browser
  extension install; exact cause not yet diagnosed).
- **Risk:** Low — diagnosis alone changes nothing; even a fix is
  additive (enables a capability that's supposed to exist already).
- **Expected benefit:** Unblocks any future browser-dependent research
  or automation task.
- **Duplicate-system risk:** None — this is the one declared MCP
  server, not a duplicate of anything.
- **Requires new credentials:** No.
- **Testable in sandbox:** Yes — connect, run a trivial navigation, confirm.
- **Final recommendation: ADOPT** (as a diagnostic task — "fix the
  thing that's supposed to already work," not a new feature decision).

---

### 2. Cite Microsoft's synced-vs-federated connector framing in any future NEXUS connector design

- **Why:** clean, battle-tested vocabulary ("index ahead of time" vs.
  "query live via MCP") that NEXUS would otherwise have to re-derive.
- **Source evidence:** `MICROSOFT_PLUGINS_CONNECTORS.md`
  (MICROSOFT_VERIFIED).
- **Complexity:** Trivial (documentation only).
- **Risk:** None.
- **Expected benefit:** Faster, clearer design discussion if/when NEXUS
  builds a connector.
- **Duplicate-system risk:** None.
- **Requires new credentials:** No.
- **Testable in sandbox:** N/A (documentation).
- **Final recommendation: ADOPT** — but only as a documentation note
  now; no connector exists to apply it to yet.

---

### 3. Evaluate (don't adopt yet) Microsoft Agent Framework / OpenAI Agents SDK as reference points for `task_lease`

- **Why:** both are mature, widely-used orchestration SDKs; worth
  knowing whether NEXUS's bespoke engine is missing something
  important, even if the conclusion is "no, NEXUS's is fine for its
  scope."
- **Source evidence:** `MICROSOFT_DEV_TOOLING.md`,
  `OPENAI_DEV_PLATFORM_COMPARISON.md`.
- **Complexity:** Medium (requires genuine comparative evaluation, not
  a quick read).
- **Risk:** Low to evaluate; replacing `task_lease` with a third-party
  SDK would be Medium-High risk and is explicitly NOT what this
  recommends.
- **Expected benefit:** Confidence that NEXUS's approach is
  deliberate, not just unexamined.
- **Duplicate-system risk:** HIGH if taken too far — adopting a full
  external SDK alongside the existing `task_lease` would create real
  duplication. This is explicitly an *evaluation*, not an adoption,
  recommendation.
- **Requires new credentials:** No (both are open-source, inspectable
  without an account).
- **Testable in sandbox:** Yes, for evaluation purposes.
- **Final recommendation: EVALUATE.**

---

### 4. Add an explicit security-risk note to `project_autonomy_policy.py` docs, citing OpenAI's own MCP exfiltration warning

- **Why:** OpenAI's own official docs explicitly warn that "a malicious
  server can exfiltrate sensitive data from anything that enters the
  model's context" — strong, citable, first-party validation of a risk
  NEXUS's design already defends against structurally
  (`FORBIDDEN_SCOPES`, explicit allowlists) but doesn't call out by
  name anywhere in its docs.
- **Source evidence:** `OPENAI_DEV_PLATFORM_COMPARISON.md`
  (OPENAI_VERIFIED).
- **Complexity:** Trivial.
- **Risk:** None.
- **Expected benefit:** Makes the *reason* for NEXUS's existing
  defensive design explicit and externally corroborated, for anyone
  reading the docs later.
- **Duplicate-system risk:** None.
- **Requires new credentials:** No.
- **Testable in sandbox:** N/A.
- **Final recommendation: ADOPT.**

---

### 5. Do NOT build a low-code/natural-language agent-creation layer

- **Why:** both Copilot Studio and Agent Builder solve a problem NEXUS
  doesn't have (non-engineers creating agents at organizational scale).
  NEXUS is single-operator and governance-heavy; the structured
  `PROJECT_SYNC`/`TASK:` dictation pattern already fits better for this
  context than a conversational agent-creation UI would.
- **Source evidence:** `MICROSOFT_COPILOT_STUDIO.md`,
  `MICROSOFT_AGENT_BUILDER.md`.
- **Complexity:** N/A (recommending against building this).
- **Risk:** N/A.
- **Expected benefit:** N/A.
- **Duplicate-system risk:** Building this WOULD duplicate the
  existing dictation pattern for no benefit.
- **Requires new credentials:** N/A.
- **Testable in sandbox:** N/A.
- **Final recommendation: SKIP.**
