# NEXUS Action Items

**Candidate tasks only — nothing in this file has been implemented.**
Per this task's explicit instruction, no code or config was changed
while producing this learning pack.

1. `DIAGNOSE_PLAYWRIGHT_MCP_CONNECTION` — figure out why the Playwright
   MCP server declared in NEXUS's `.mcp.json` isn't callable in a live
   session; fix if straightforward (client reconnect / extension
   install), otherwise document the real blocker precisely. (See
   `NEXUS_RECOMMENDATIONS.md` #1 — ADOPT.)
2. `DOCUMENT_CONNECTOR_VOCABULARY` — add a short note to NEXUS's
   governance docs citing Microsoft's synced-vs-federated connector
   framing, for future reference if NEXUS ever builds a connector. (See
   `NEXUS_RECOMMENDATIONS.md` #2 — ADOPT.)
3. `EVALUATE_AGENT_FRAMEWORK_VS_TASK_LEASE` — a written, honest
   comparison of `task_lease`'s design against Microsoft Agent
   Framework and OpenAI Agents SDK, concluding ADOPT/EVALUATE-further/
   SKIP for any specific idea worth borrowing. Explicitly not a
   migration task. (See `NEXUS_RECOMMENDATIONS.md` #3 — EVALUATE.)
4. `ADD_MCP_SECURITY_CITATION` — add OpenAI's MCP-exfiltration-risk
   warning as an explicit citation in
   `src/core/governance/PROJECT_AUTONOMY_POLICY_README.md`. (See
   `NEXUS_RECOMMENDATIONS.md` #4 — ADOPT.)
5. `DEEP_DIVE_AGENT365_SAMPLES` — individually browse
   `microsoft/Agent365-Samples` and `microsoft/copilot-sdk-samples`
   (both UNKNOWN-status in `GITHUB_REPO_MAP.md` only because they
   weren't individually fetched this pass), to decide whether NEXUS's
   `task_lease/dashboard.py` should grow toward an Agent-365-style
   control plane. (See `NEXUS_GAP_ANALYSIS.md` NEXT #2.)

## Explicitly not recommended as tasks

- Building a low-code or natural-language agent-creation layer (see
  `NEXUS_RECOMMENDATIONS.md` #5 — SKIP).
- Adding a user-facing multi-model picker.
- Pursuing any formal certification/credentialing program.
