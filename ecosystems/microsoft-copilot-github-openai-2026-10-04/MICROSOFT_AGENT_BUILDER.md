# Microsoft Agent Builder

Source: https://learn.microsoft.com/en-us/microsoft-365/copilot/extensibility/agent-builder ,
https://learn.microsoft.com/en-us/microsoft-365/copilot/extensibility/agent-builder-build-agents

## MICROSOFT_VERIFIED facts

- Agent Builder provides "a simple interface for quickly building
  declarative agents using natural language, specifically for use with
  Microsoft 365 Copilot."
- Agent creation is conversational: "the agent's name, description, and
  instructions update automatically as you provide information
  conversationally to refine its behavior" — there is no separate
  code/config step for a basic agent.
- You can specify **dedicated knowledge sources**, explicitly including
  SharePoint content and **Copilot connectors** (see
  `MICROSOFT_PLUGINS_CONNECTORS.md`) as groundable knowledge.
- Agents can be **tested before publishing**.
- **Skills can be added** to an agent, either by selecting an existing
  skill or creating one via natural language — but skills in Agent
  Builder are explicitly stated as **in preview, limited to
  organizations enrolled in the Microsoft Frontier Program** (i.e., not
  generally available).

## INFERENCE

- Agent Builder appears to be Microsoft's answer to "the simplest
  possible agent creation surface," trading configurability for
  natural-language ease — consistent with the three-tier model named in
  `MICROSOFT_COPILOT_STUDIO.md`.

## UNVERIFIED

- What "skills" concretely are at the implementation level (API shape,
  how they differ from a Copilot Studio-built agent's actions) — not
  shown on the pages fetched this pass.
- Exact Frontier Program enrollment requirements.

## NEXUS_IDEA

- **NEXUS_IDEA:** "agent's instructions update automatically as you
  provide information conversationally" is a materially different
  interaction model than NEXUS's current `PROJECT_SYNC`/`TASK:`
  dictation pattern, where the task definition is written once, fully
  formed, up front. Not a recommendation to change NEXUS's model — just
  flagging the contrast, since NEXUS's current pattern trades
  conversational ease for precision/auditability, which seems like the
  right tradeoff for NEXUS's governance-heavy use case specifically.
