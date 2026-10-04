# Microsoft Developer Tooling

Sources: https://devblogs.microsoft.com/microsoft365dev/introducing-the-microsoft-365-agents-toolkit/ ,
https://github.com/microsoft/agents (fully fetched),
https://github.com/microsoft/semantic-kernel (fully fetched),
search-level results for AutoGen/Teams SDK.

## MICROSOFT_VERIFIED facts

### Microsoft 365 Agents SDK (`github.com/microsoft/agents`)

- Official SDK for building agents deployable across Microsoft 365
  Copilot, Teams, Copilot Studio, Webchat, and custom channels.
- **A Microsoft 365 Copilot subscription is explicitly NOT required**
  to use the SDK in general — a notable, deliberately-stated
  decoupling of the dev tool from the paid product.
- Language support: C#/.NET, JavaScript/TypeScript, and Python via
  separate language-specific repos.
- Repo health (as fetched): 1,051+ commits on main, 88 open issues, 33
  open PRs — GITHUB_VERIFIED active maintenance signal.
- Key folders: `samples/` (QuickStart recommended as entry point),
  `docs/`, `agent-plugins/` (AI coding-assistant plugins for SDK
  knowledge — i.e., tooling to help an AI coding assistant itself
  understand the SDK), `specs/`, `experimental/`.

### Microsoft 365 Agents Toolkit

- Evolution of the former **Microsoft Teams Toolkit** — same lineage,
  broadened scope. Available for VS Code, Visual Studio, and as a
  GitHub Copilot extension.
- Provides project scaffolding for common extensibility types (agents
  for M365 Copilot, multi-platform chatbots) and integrates with both
  the Agents SDK (self-hosted agents) and the Teams AI Library/SDK
  (Teams-specific agents).
- A separate samples repo (`OfficeDev/microsoft-365-agents-toolkit-samples`)
  provides scenario-focused starter apps (proxy agents in C#/Node/Python,
  "coffee-agent," "copilot-connector-app," etc.).

### Teams SDK (renamed from "Teams AI")

- Microsoft explicitly renamed "Teams AI" to "Teams SDK" to signal
  broader scope — "a comprehensive development framework for building
  all types of Teams applications," not just AI-specific ones.
- Supports TypeScript, C#, Python; covers AI-powered agents, Message
  Extensions, and Graph integrations.

### Semantic Kernel → Microsoft Agent Framework

- **Semantic Kernel is now superseded by Microsoft Agent Framework
  (MAF) v1.0**, described as the "enterprise-ready successor." The SK
  repo itself remains active (28.6k stars, 4.8k forks, 119 open issues,
  5,089+ commits) with a migration guide provided — not abruptly
  deprecated, but clearly positioned as the predecessor now.
- **Microsoft Agent Framework merges Semantic Kernel and AutoGen into
  one codebase, one API set, one GitHub repo** — shipped as "Agent
  Framework 1.0" on April 7 (year not independently confirmed beyond
  the search snippet's own "April 7" reference — flagged as
  **UNVERIFIED which year** exactly, though context strongly implies
  2026).
- AutoGen (pre-merger) provided named orchestration patterns:
  sequential, concurrent, group chat, handoff, and "Magentic-One" for
  complex task decomposition.

## UNVERIFIED

- Exact feature parity between old Semantic Kernel and new Microsoft
  Agent Framework — i.e., whether anything was dropped in the merger.
- The precise year of the "April 7" Agent Framework 1.0 ship date.

## NEXUS_IDEA

- **NEXUS_IDEA:** the SK → Microsoft Agent Framework merger (two
  previously-parallel projects collapsed into one codebase) is a
  cautionary data point for NEXUS's own governance code: NEXUS
  currently has two related-but-separate concepts
  (`task_lease` for execution/ownership, `project_autonomy_policy` for
  authority grants) that have so far stayed cleanly separated by
  design. Worth periodically re-checking whether they're drifting
  toward needing a similar merge, rather than assuming they'll always
  stay cleanly separate just because they started that way.
- **NEXUS_IDEA:** "agent-plugins/" in the M365 Agents SDK repo (tooling
  specifically to help an AI coding assistant understand the SDK) is a
  pattern NEXUS could consider for its own governance modules — e.g. a
  structured summary file that helps a future Claude session understand
  `project_autonomy_policy.py` faster than reading the full source.
  `PROJECT_AUTONOMY_POLICY_README.md` already does this informally;
  worth treating that pattern as deliberate rather than incidental.
