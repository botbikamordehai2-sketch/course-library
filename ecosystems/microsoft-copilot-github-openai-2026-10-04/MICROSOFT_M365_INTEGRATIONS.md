# Microsoft 365 App Integrations (SharePoint, OneDrive, Outlook, Teams, Word, Excel, PowerPoint)

## MICROSOFT_VERIFIED facts

- **SharePoint:** has its own dedicated Copilot changelog series
  separate from the general M365 Copilot one (e.g. "What's new in
  Copilot in SharePoint: August 2026" and "...October 2026" —
  `techcommunity.microsoft.com/blog/spblog/...`), implying SharePoint
  gets Copilot feature updates frequently enough to warrant its own
  dedicated series rather than being folded into the general one.
- **Synced connectors power "Microsoft Search, Copilot in Excel, and
  the Researcher agent"** specifically named alongside general M365
  Copilot (per the connectors overview page) — Excel and a
  Copilot-native "Researcher agent" are explicitly called out as
  connector-consuming surfaces, not just the general chat experience.
- **Teams:** has the most GitHub-visible dev-tooling investment of any
  single M365 app found this pass — `OfficeDev/Microsoft-Teams-Samples`,
  `microsoft/teams-agent-accelerator-templates`, `microsoft/teams-sdk`
  (renamed from "Teams AI") all exist as dedicated repos (see
  `GITHUB_REPO_MAP.md`).
- **Outlook:** appears in this pass mainly as a target channel/surface
  (e.g. in the OpenAI connector list, Outlook Email and Outlook
  Calendar are both separately listed as OpenAI-side connectors — see
  `OPENAI_DEV_PLATFORM_COMPARISON.md`) rather than as a Microsoft-side
  deep-dive source in this pass; no dedicated Outlook-Copilot blog
  series was found distinctly from the general M365 Copilot one.

## UNVERIFIED

- Word- and PowerPoint-specific Copilot extensibility details — neither
  came up with dedicated material in this pass beyond being named
  generically as part of "Microsoft 365" in the product list. Not
  claiming they lack features; just that this pass didn't surface
  product-specific material for them the way it did for SharePoint,
  Excel, and Teams.

## NEXUS_IDEA

- **NEXUS_IDEA:** NEXUS's own stated architecture
  (per the FINALIZE_PROJECT_SCOPED_AUTONOMY task history) already names
  "OneDrive / SharePoint file plane," "Outlook intake," and "Notion
  knowledge plane" as distinct layers — this maps reasonably well onto
  how Microsoft itself separates these surfaces (each with its own
  connector/plugin path rather than one unified mechanism). Validates
  NEXUS's existing separation rather than suggesting a change.
