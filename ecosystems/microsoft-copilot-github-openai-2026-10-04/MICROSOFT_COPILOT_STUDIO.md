# Microsoft Copilot Studio

Source: https://learn.microsoft.com/en-us/microsoft-copilot-studio/ ,
https://www.microsoft.com/en-us/microsoft-365-copilot/microsoft-copilot-studio
(search-snippet level), https://adoption.microsoft.com/en-us/ai-agents/copilot-studio/

## MICROSOFT_VERIFIED facts

- Copilot Studio is Microsoft's low-code platform for building agents,
  with official Microsoft Learn documentation covering agent creation,
  configuring agent details/instructions, and "usage-based billing with
  Copilot Credits" (i.e., agent usage is metered/billed per-credit, not
  flat-rate).
- A "standard harness" quickstart exists for creating and deploying an
  agent (`learn.microsoft.com/.../fundamentals-get-started`), implying
  more than one deployment "harness" option exists, though only the
  standard one was named in what was fetched this pass.
- Microsoft launched an **AI Agent Builder certification** for Copilot
  Studio (with a beta exam discount) — a formal credentialing program,
  not just documentation.
- **2026-wave governance updates** (per
  `learn.microsoft.com/.../manage-copilot-security-enhanced-admin-controls`):
  admins can centrally define authentication and access policies for
  agents at the environment or environment-group level, explicitly
  choosing between requiring Microsoft Entra ID authentication, allowing
  approved external auth providers, or prohibiting anonymous access
  entirely.

## INFERENCE

- Copilot Studio appears positioned as the **low-code/no-code** agent
  platform, distinct from the **Microsoft 365 Agents SDK** (code-first,
  see `MICROSOFT_DEV_TOOLING.md`) and **Agent Builder** (the most
  lightweight, natural-language-only option, see
  `MICROSOFT_AGENT_BUILDER.md`) — Microsoft appears to offer three tiers
  of agent-building complexity side by side rather than one single tool.
  This is an inference from how the three are described separately
  across sources, not a single page stating this tiering explicitly.

## UNVERIFIED

- Exact pricing/credit-consumption rates.
- The full list of deployment "harness" options beyond "standard."

## NEXUS_IDEA

- **NEXUS_IDEA:** the three-tier complexity model (low-code Copilot
  Studio / natural-language-only Agent Builder / code-first Agents SDK)
  is a useful frame for NEXUS to self-assess: NEXUS today is entirely
  code-first (Python, `task_lease`, governance modules) with no
  low-code or natural-language agent-creation layer at all. That's
  likely fine for NEXUS's current single-operator context, but worth
  naming explicitly as a deliberate choice rather than an oversight if
  NEXUS ever needs non-engineers to create agents/tasks.
