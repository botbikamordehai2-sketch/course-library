# GitHub Repo Map

Only official Microsoft-org repos are included, per the task's explicit
instruction not to add unrelated repos just for mentioning "copilot."
Status is GITHUB_VERIFIED where fetched directly, INFERENCE where
based on search-snippet signals only (noted per row).

| Repo | Owner/org | Official? | What it demonstrates | Key folders/examples | Relevance to MS Copilot | Relevance to NEXUS | Status |
|---|---|---|---|---|---|---|---|
| [microsoft/agents](https://github.com/microsoft/agents) | microsoft | Official | Multichannel Agent SDK (M365 Copilot, Teams, Copilot Studio, Webchat) | `samples/`, `docs/`, `agent-plugins/`, `specs/`, `experimental/` | Direct — the code-first path to building Copilot-channel agents | Comparable to NEXUS's own `task_lease`/governance layer, but for multi-channel deployment rather than task ownership | **ACTIVE** (GITHUB_VERIFIED — 1,051+ commits, 88 open issues, 33 open PRs as fetched) |
| [microsoft/semantic-kernel](https://github.com/microsoft/semantic-kernel) | microsoft | Official | Orchestration framework for AI agents/multi-agent systems | `python/`, `dotnet/`, `java/`, `docs/`, `prompt_template_samples/` | Orchestration layer Copilot-adjacent products can build on | Comparable to NEXUS's own orchestration role split (GPT/Claude/Gemini) | **ACTIVE but superseded** (GITHUB_VERIFIED — 28.6k stars, 5,089+ commits; successor is Microsoft Agent Framework, migration guide provided) |
| [microsoft/autogen](https://github.com/microsoft/autogen) | microsoft | Official | Multi-agent orchestration patterns (sequential, concurrent, group chat, handoff, Magentic-One) | not individually browsed this pass | Predecessor/merging into Microsoft Agent Framework | Comparable to NEXUS's multi-agent coordination, at a more generic/framework level | **MERGING** (search-level signal: being merged into Microsoft Agent Framework; not independently confirmed archived) |
| [microsoft/spec-to-agents](https://github.com/microsoft/spec-to-agents) | microsoft | Official | Worked multi-agent example (event planning) on Microsoft Agent Framework | not individually browsed | Demonstrates SK+AutoGen convergence in practice | Example-only; useful as a reference implementation pattern | UNKNOWN (not independently checked for activity) |
| [OfficeDev/microsoft-365-agents-toolkit](https://github.com/OfficeDev/microsoft-365-agents-toolkit) | OfficeDev (Microsoft) | Official | Dev tooling (VS/VS Code/GitHub Copilot extension) for building agents/Teams apps | not individually browsed | The IDE-side tooling for the whole ecosystem | Low direct relevance — NEXUS doesn't build IDE extensions | UNKNOWN |
| [OfficeDev/microsoft-365-agents-toolkit-samples](https://github.com/OfficeDev/microsoft-365-agents-toolkit-samples) | OfficeDev (Microsoft) | Official | Scenario sample apps (proxy agents in C#/Node/Python, coffee-agent, copilot-connector-app) | language-specific sample folders | Worked examples for common agent patterns | Useful reference if NEXUS ever needs a Teams-channel agent | UNKNOWN |
| [microsoft/teams-agent-accelerator-templates](https://github.com/microsoft/teams-agent-accelerator-templates) | microsoft | Official | Templates integrating Teams with various AI agent paradigms | not individually browsed | Teams-specific agent starting points | Low direct relevance unless NEXUS targets Teams | UNKNOWN |
| [microsoft/teams-sdk](https://github.com/microsoft/teams-sdk) | microsoft | Official | AI-based Teams app SDK (renamed from "Teams AI") | not individually browsed | Teams-channel agent development | Low direct relevance unless NEXUS targets Teams | UNKNOWN (renamed recently per search snippet — rename itself GITHUB_VERIFIED, activity level not independently checked) |
| [microsoft/Agent365-Samples](https://github.com/microsoft/Agent365-Samples) | microsoft | Official | Samples for Agent 365 (governance/control-plane product) | not individually browsed | Direct — governance tooling samples | High relevance for comparing against NEXUS's own `task_lease`/governance observability | UNKNOWN |
| [microsoft/copilot-sdk-samples](https://github.com/microsoft/copilot-sdk-samples) | microsoft | Official | "Agents powered by Copilot-SDK and GitHub Agentic Workflow System" | not individually browsed | Direct — Copilot SDK + GitHub workflow integration | Directly comparable to NEXUS's own GitHub-flow-based agent governance | UNKNOWN |
| [microsoftgraph/msgraph-sample-github-connector-dotnet](https://github.com/microsoftgraph/msgraph-sample-github-connector-dotnet) | microsoftgraph (Microsoft) | Official | Sample Copilot connector indexing GitHub issues/repos | single-purpose sample | Direct example of a synced connector | Directly relevant if NEXUS ever indexes its own GitHub issues into a connector-style system | UNKNOWN |
| [microsoftgraph/msgraph-sample-github-connector-python](https://github.com/microsoftgraph/msgraph-sample-github-connector-python) | microsoftgraph (Microsoft) | Official | Same as above, Python | single-purpose sample | Same | Same, and in NEXUS's own primary language | UNKNOWN |
| [microsoftgraph/msgraph-sample-github-connector-typescript](https://github.com/microsoftgraph/msgraph-sample-github-connector-typescript) | microsoftgraph (Microsoft) | Official | Same as above, TypeScript | single-purpose sample | Same | Same | UNKNOWN |

## NEXUS_IDEA

- **NEXUS_IDEA:** of everything in this table, `microsoft/Agent365-Samples`
  and `microsoft/copilot-sdk-samples` are the two most directly worth a
  follow-up deep-dive if NEXUS ever wants external reference material
  for its own governance/GitHub-flow design — both are UNKNOWN status
  here only because this pass didn't individually browse them, not
  because they looked irrelevant.
