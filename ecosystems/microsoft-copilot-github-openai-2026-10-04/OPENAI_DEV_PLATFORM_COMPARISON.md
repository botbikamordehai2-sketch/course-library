# OpenAI Developer Platform — Comparison to Microsoft Copilot Ecosystem

**Naming note, per the task's explicit instruction:** the task's own
"GPT Dev Cloud" terminology is **not** OpenAI's actual product name.
Verified via WebSearch + cross-reference: the real current product is
**Codex** (CLI, released April 2025) and **Codex Cloud** (announced May
2025, expanded 2026 to support starting/continuing coding tasks from
desktop/web/mobile). "GPT Dev Cloud" does not appear as an official
OpenAI product name anywhere found this pass — noting the alias/
confusion explicitly rather than silently using the task's wrong term.

## OPENAI_VERIFIED facts

### Coding agent

- **Codex** is OpenAI's AI coding agent for software engineering tasks.
  OpenAI was named a **Leader in Gartner's 2026 Magic Quadrant for
  Enterprise AI Coding Agents**, with Codex cited as used by "more than
  4 million people each week" (OPENAI_VERIFIED via openai.com's own
  announcement of the Gartner recognition).

### Agents API / Responses API

- OpenAI has (at minimum) two related but apparently distinct
  surfaces found this pass: the **Responses API** (supports MCP
  natively, has built-in tools including web search/file search/
  computer use) and a separately-announced **Agents API** (got
  computer-use added in September 2026, uses an
  `OpenAI-Beta: agents=v1` header). **UNVERIFIED exactly how these two
  relate** — whether Agents API is a newer evolution of/wrapper around
  Responses API, or a parallel product — the sources found this pass
  described them as separate without clarifying the relationship.
  Flagging this explicitly rather than guessing.

### MCP support (fully fetched: `developers.openai.com/api/docs/guides/tools-connectors-mcp`)

- MCP is supported across **Responses API, Chat Completions API,
  Assistants API**, with Agents API sessions covered in separate
  documentation not fetched this pass.
- A remote MCP server is attached via a `server_url` parameter; the
  API auto-discovers and executes tools, returning results as
  `mcp_call` output items.
- **Security/approval model is tiered and explicit:**
  - Default: OpenAI requests approval before any data is shared with a
    connector or remote MCP server.
  - `require_approval: "always"` vs. `"never"`, plus granular
    `allowed_tools` to bypass approval for specific tools only.
  - Explicit documented warning: "a malicious server can exfiltrate
    sensitive data from anything that enters the model's context" —
    OpenAI's own docs name this risk directly, not just imply caution.

### Built-in connectors

- The Responses API ships **built-in connectors** to: Dropbox, Gmail,
  Google Calendar, Google Drive, Microsoft Teams, Outlook Calendar,
  Outlook Email, SharePoint. Notably, **three of these eight are
  Microsoft products** (Teams, Outlook, SharePoint) — OpenAI has
  first-party connectors into Microsoft's ecosystem, independent of
  Microsoft's own Copilot connector gallery.

### Computer use / browsing

- Added to the Agents API in **September 2026**: agents complete tasks
  in an **OpenAI-hosted browser**. The browser requires **per-website-origin
  user approval** — "one approval covers a whole site" (per a
  cross-referenced but non-official source, flagged as such), and the
  official docs confirm approval is required "before accessing each
  new website origin, including public websites."

## CROSS_SOURCE_VERIFIED

- Both Microsoft (federated connectors) and OpenAI (Responses/Agents
  API) have independently converged on **MCP as the standard mechanism
  for live, non-indexed third-party data access** — this is the
  single clearest point of architectural convergence found across the
  two ecosystems in this entire pass.

## UNVERIFIED

- Precise relationship between OpenAI's Responses API and Agents API.
- Whether OpenAI's computer-use/browsing tool has any equivalent to
  Microsoft's Agent 365 governance/observability layer — nothing
  found this pass suggests OpenAI has a directly comparable dedicated
  governance product; this may be an actual capability gap on OpenAI's
  side rather than something this pass simply missed, but that's not
  confirmed either way.

## NEXUS_IDEA

- **NEXUS_IDEA:** OpenAI's explicit, user-facing warning about MCP
  server data exfiltration risk is a good citation to add to NEXUS's
  own `project_autonomy_policy.py` docs if NEXUS ever connects to a
  third-party MCP server — the risk isn't hypothetical, it's something
  OpenAI itself warns its own developers about in its official docs.
- **NEXUS_IDEA:** the tiered approval model (`always`/`never`/
  `allowed_tools` allowlist) is architecturally similar to NEXUS's own
  `ALLOWED_SCOPES`/`FORBIDDEN_SCOPES` design in
  `project_autonomy_policy.py` — both converge on "default to asking,
  allow explicit narrow exceptions, hard-block some things
  unconditionally." Worth citing as external validation of that
  pattern.
