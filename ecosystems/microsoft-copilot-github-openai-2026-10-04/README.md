# Microsoft Copilot / GitHub / OpenAI Dev Ecosystem — Learning Pack

**Date of scan:** 2026-10-04

## Purpose

A structured, public-safe summary of the Microsoft Copilot ecosystem
(Copilot, Microsoft 365 Copilot, Copilot Studio, Agent Builder,
plugins/connectors, governance, dev tooling), the official GitHub
repositories that implement it, and the comparable/complementary parts
of OpenAI's current developer platform — compared against NEXUS's own
architecture.

## Scope and honesty note

This is a **representative, well-sourced research pass**, not an
exhaustive crawl of every Microsoft Copilot Blog post ever published.
Real WebSearch/WebFetch calls were made against official sources
(`learn.microsoft.com`, `techcommunity.microsoft.com`,
`devblogs.microsoft.com`, `github.com/microsoft/*`,
`developers.openai.com`), and every claim below is labeled with where
it came from. Nothing here should be read as "every Microsoft Copilot
capability that exists" — it's what this pass actually found and
verified. `CHANGELOG_SCAN.md` states the real coverage achieved against
the task's own termination criteria, honestly, rather than claiming a
saturation point that wasn't actually reached.

## Source rules followed

- Public, official sources only (`learn.microsoft.com`,
  `techcommunity.microsoft.com`, `devblogs.microsoft.com`,
  `developers.openai.com`, `github.com` official org repos). No
  authenticated/subscriber access was used or available.
- No login, paywall, CAPTCHA, or DRM was bypassed.
- No full article/doc was reproduced — everything here is summarized
  and transformed, with source URLs preserved so the original can be
  read directly.
- No private NEXUS data (Notion URLs, emails, local paths, tokens,
  secrets, private OneDrive/Outlook data) appears anywhere in this pack.

## Source classification legend

- **MICROSOFT_VERIFIED** — from an official Microsoft page fetched during this scan.
- **GITHUB_VERIFIED** — from an official Microsoft/Microsoft-org GitHub repo fetched during this scan.
- **OPENAI_VERIFIED** — from an official OpenAI page fetched during this scan.
- **CROSS_SOURCE_VERIFIED** — corroborated by more than one of the above during this scan.
- **INFERENCE** — a reasonable conclusion drawn from verified facts, not stated outright by any source.
- **NEXUS_IDEA** — my own suggestion for NEXUS; never a claim about Microsoft/GitHub/OpenAI.
- **UNVERIFIED** — could not be confirmed from a public source this pass; not fabricated to fill the gap.

## File map

| File | Contents |
|---|---|
| `SOURCE_INDEX.md` | Every source used, with URL, date accessed, type, classification, relevance |
| `MICROSOFT_COPILOT_OVERVIEW.md` | Microsoft Copilot / Microsoft 365 Copilot — what it is, recent model-choice changes |
| `MICROSOFT_COPILOT_STUDIO.md` | Copilot Studio — low-code agent building platform |
| `MICROSOFT_AGENT_BUILDER.md` | Agent Builder — natural-language agent creation inside M365 Copilot |
| `MICROSOFT_PLUGINS_CONNECTORS.md` | Plugins, synced connectors, federated (MCP-based) connectors |
| `MICROSOFT_M365_INTEGRATIONS.md` | SharePoint/OneDrive/Outlook/Teams/Word/Excel/PowerPoint integration points |
| `MICROSOFT_GOVERNANCE_SECURITY.md` | Agent 365, Copilot Control System, Entra ID auth, admin controls |
| `MICROSOFT_DEV_TOOLING.md` | Microsoft 365 Agents SDK/Toolkit, Teams SDK, Semantic Kernel → Microsoft Agent Framework, AutoGen |
| `GITHUB_REPO_MAP.md` | Every official repo found, with status and relevance |
| `OPENAI_DEV_PLATFORM_COMPARISON.md` | OpenAI's current dev platform (Codex/Codex Cloud, Responses/Agents API, MCP support, computer-use) vs. Microsoft |
| `CAPABILITY_MATRIX.md` | Capability-by-capability table: Microsoft / GitHub / OpenAI / NEXUS / gap / recommendation |
| `NEXUS_GAP_ANALYSIS.md` | Gaps grouped NOW / NEXT / LATER / SKIP |
| `NEXUS_RECOMMENDATIONS.md` | Each recommendation with evidence, risk, complexity, final verdict |
| `NEXUS_ACTION_ITEMS.md` | Candidate tasks only — nothing implemented |
| `CHANGELOG_SCAN.md` | Honest record of what was actually scanned, counts, and where coverage stopped |

## Copyright note

All content here is original summary/analysis/comparison. Source URLs
are preserved throughout so anyone can read the original material
directly; nothing here substitutes for or reproduces it.
