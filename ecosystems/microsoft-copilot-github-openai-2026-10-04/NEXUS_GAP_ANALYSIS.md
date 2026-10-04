# NEXUS Gap Analysis

Everything in this file is NEXUS_IDEA / INFERENCE grouping of gaps
already identified in `CAPABILITY_MATRIX.md`. No code or config was
changed to produce this.

## NOW

1. **Diagnose why Playwright MCP isn't connected.** `.mcp.json`
   declares it, `ToolSearch` confirms it's not callable this session.
   This is the single most concrete, scoped gap found across the
   entire scan — not a new capability to build, a connection problem to
   fix on something already intended.

## NEXT

2. **Decide whether `task_lease/dashboard.py` should grow toward an
   Agent-365-style control plane, or stay narrow.** Microsoft's Agent
   365 is a dedicated governance/observability product; NEXUS's
   dashboard is lease-state-only. Not urgent, but worth a deliberate
   decision rather than organic scope creep either direction.
3. **Compare Playwright MCP's approval model (once connected) against
   OpenAI's per-website-origin computer-use approval.** OpenAI's model
   is explicit and documented; NEXUS's Playwright MCP's actual
   approval behavior hasn't been exercised yet since it isn't
   connected. Worth doing once gap #1 is fixed, not before.

## LATER

4. **Evaluate NEXUS's bespoke `task_lease` engine against adopting a
   standard agent SDK** (Microsoft 365 Agents SDK or OpenAI Agents SDK
   as reference points, not necessarily adoption candidates). NEXUS's
   engine is small, tested, and fits NEXUS's specific governance model
   exactly — this is a "does a real gap exist" question, not an
   assumption that NEXUS should switch to someone else's SDK.
5. **Consider a synced-vs-federated-style connector framework if NEXUS
   ever needs one.** No current use case exists; premature to build.
6. **Consider authoring an MCP server if NEXUS ever needs to expose its
   own data/capabilities to an external MCP client.** No current use
   case; Microsoft's own docs don't show this as a Copilot-specific
   pattern either, so there's no urgency pressure from the ecosystem
   scan itself.

## SKIP

7. **Low-code/no-code agent builder (Copilot Studio equivalent).**
   NEXUS's single-operator, code-first, governance-heavy context
   doesn't benefit from this — the precision/auditability of the
   current `PROJECT_SYNC`/`TASK:` dictation pattern is a better fit
   than natural-language agent creation would be.
8. **Natural-language agent creation (Agent Builder equivalent).** Same
   reasoning as #7.
9. **Formal agent-builder certification program.** Not relevant at
   NEXUS's scale (one operator, one codebase).
10. **User-facing multi-model picker.** NEXUS's fixed role-per-model
    design (GPT=Orchestrator, Claude=Engineer, Gemini=Analyst) is a
    deliberate governance choice, not a missing feature to backfill.
11. **Push-based progress notifications for long-running tasks.**
    Neither Microsoft nor OpenAI's public material showed a clear
    equivalent either, so this isn't competitively urgent — NEXUS's
    poll-based `heartbeat()` is roughly at parity with what's visible
    in the broader ecosystem right now, not obviously behind it.
