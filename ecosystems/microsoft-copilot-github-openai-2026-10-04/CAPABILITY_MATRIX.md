# Capability Matrix

Labels per capability are per-cell classification shorthand; full
sourcing is in the individual `MICROSOFT_*.md` / `OPENAI_DEV_PLATFORM_COMPARISON.md`
files. "NEXUS current state" is read from this repo's actual code
(`src/core/governance/`, `src/core/task_lease/`, `.mcp.json`), not
memory.

| Capability | Microsoft | GitHub implementation/examples | OpenAI equivalent | NEXUS current state | Gap | Recommendation |
|---|---|---|---|---|---|---|
| Multi-model selection | Copilot picks from GPT/Claude/Grok models (MICROSOFT_VERIFIED) | n/a | Model selection via API `model` param (OPENAI_VERIFIED) | NEXUS assigns fixed roles per model (GPT/Claude/Gemini), not end-user-selectable (NEXUS_CURRENT) | NEXUS has no user-facing model picker | SKIP — NEXUS's fixed-role model is deliberate governance, not a missing feature |
| Low-code agent builder | Copilot Studio (MICROSOFT_VERIFIED) | — | No direct equivalent found this pass | None (NEXUS_CURRENT — code-first only) | Real gap vs. Microsoft, not vs. OpenAI | SKIP for now — single-operator context doesn't need low-code |
| Natural-language agent creation | Agent Builder (MICROSOFT_VERIFIED) | — | Not found this pass | None (NEXUS_CURRENT — `PROJECT_SYNC`/`TASK:` is structured dictation, not conversational agent creation) | Real gap vs. Microsoft | SKIP — precision/auditability tradeoff favors NEXUS's current approach |
| Code-first agent SDK | Microsoft 365 Agents SDK (GITHUB_VERIFIED) | `microsoft/agents` | OpenAI Agents SDK (OPENAI_VERIFIED) | `src/core/task_lease/` + governance modules (NEXUS_CURRENT) | Partial — NEXUS has its own bespoke equivalent, not a gap exactly | EVALUATE — compare NEXUS's bespoke lease engine against adopting a standard SDK |
| MCP server support (as client) | Federated connectors use MCP (MICROSOFT_VERIFIED) | — | Responses/Agents API MCP support (OPENAI_VERIFIED) | `.mcp.json` declares Playwright MCP, not connected this session (NEXUS_CURRENT, verified via ToolSearch) | Partial — configured but not working | NOW — diagnose the connection gap |
| MCP server authoring | Not found as a Microsoft-authored-server concept this pass | `microsoft/semantic-kernel` supports MCP as a plugin type (GITHUB_VERIFIED) | Not NEXUS-relevant (OpenAI is a consumer here too) | None — NEXUS has never authored an MCP server (NEXUS_CURRENT) | Real gap if ever needed | LATER — no current use case |
| Tiered tool-approval model | Entra ID auth tiers for connectors (MICROSOFT_VERIFIED) | — | `require_approval: always/never` + `allowed_tools` (OPENAI_VERIFIED) | `ALLOWED_SCOPES`/`FORBIDDEN_SCOPES` in `project_autonomy_policy.py` (NEXUS_CURRENT) | NEXUS already has this | — NEXUS already has a comparable pattern |
| Dedicated agent governance/control-plane product | Agent 365 (MICROSOFT_VERIFIED) | `microsoft/Agent365-Samples` | Not found this pass | `src/core/task_lease/dashboard.py` (NEXUS_CURRENT — much smaller scope: lease state only, not full agent telemetry) | Partial | NEXT — consider whether dashboard.py should grow toward this, or stay narrow |
| Push-based progress/notifications for long tasks | Not found this pass (Microsoft side) | — | Not found this pass (OpenAI side) | `task_lease.heartbeat()` is poll-based, writes a file (NEXUS_CURRENT) | Gap exists on all sides, not NEXUS-specific | SKIP — not a competitive disadvantage if nobody else has it either |
| Hosted browser / computer-use | Not found as a named Microsoft Copilot capability this pass | — | Agents API computer-use, per-origin approval (OPENAI_VERIFIED) | Playwright MCP declared but not connected (NEXUS_CURRENT) | Real gap vs. OpenAI specifically | NEXT — once Playwright MCP connection is fixed, compare its approval model to OpenAI's per-origin approval |
| Per-user data permission inheritance (no separate ACL system) | Explicit design principle (MICROSOFT_VERIFIED) | — | Not directly addressed this pass | `github_access_policy.py` gates on GitHub's own repo ACLs; `project_autonomy_policy.py` requires Moti approval, doesn't invent a parallel user-permission system (NEXUS_CURRENT) | NEXUS already follows this principle | — validated, no action needed |
| Formal agent-builder certification/credentialing | Copilot Studio certification exists (MICROSOFT_VERIFIED) | — | Not found this pass | None (NEXUS_CURRENT — single-operator project, no certification need) | Not applicable | SKIP — not relevant at NEXUS's scale |
| Synced vs. federated connector distinction | Explicit two-model framework (MICROSOFT_VERIFIED) | sample connectors in 3 languages | Built-in connectors appear federated-style only (query-time) per what was found (OPENAI_VERIFIED, partial) | No connector concept exists in NEXUS yet (NEXUS_CURRENT) | Real gap, but no current use case | LATER |

## NEXUS_IDEA

- **NEXUS_IDEA:** this matrix's clearest actionable row is the
  MCP-client one — NEXUS already *intends* to have MCP client
  capability (Playwright is declared) but it isn't working, which is a
  concrete, scoped, low-risk fix candidate rather than a big
  architecture question. See `NEXUS_GAP_ANALYSIS.md`'s `NOW` bucket.
