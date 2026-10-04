# Microsoft Plugins & Connectors

Primary source (fully fetched):
https://learn.microsoft.com/en-us/microsoft-365/copilot/extensibility/overview-copilot-connector

## MICROSOFT_VERIFIED facts

### Two connector models

| | Synced connector | Federated connector |
|---|---|---|
| Data movement | Content synced into Microsoft Graph | No data movement; query-time fetch |
| Semantic indexing | Supported | Not supported |
| Schema | `externalItem` schema | Defined by MCP server tools |
| Use case | Knowledge repos, document stores, LOB systems | Dynamic/regulated data that must stay in source |
| Auth | Microsoft Entra ID app registration | MCP-supported methods (OAuth 2.0 or service-specific) |
| Retrieval | Indexed search + synthesis | Real-time API calls |

**Federated connectors are explicitly MCP-based** — Microsoft's own
docs state they "retrieve content in real time by using Model Context
Protocol (MCP) without indexing data into Microsoft Graph." This is a
direct, first-party Microsoft adoption of MCP as a connector transport,
not a third-party integration.

### Plugins

- "A Copilot connector can provide external data access as a
  capability of a Microsoft 365 Copilot **plugin**." Plugins are the
  higher-level packaging concept; connectors, agents, skills, and
  MCP-based capabilities can all be brought together inside one plugin.
- Authentication guidance differs by model: "Authentication
  requirements differ between synced connectors, federated connectors,
  MCP plugins, and agent connectors" — Microsoft explicitly warns that
  MCP/API plugin auth guidance does **not** automatically apply to
  Copilot connectors; each has its own auth path.

### Availability

Copilot connectors work in commercial, GCC, GCCH, and DoD environments
(government cloud tiers) — availability varies by specific connector.

### Connector gallery

"More than 100 connectors available," covering Azure services, Box,
Confluence, Google services, MediaWiki, Salesforce, ServiceNow, and
more, via the Copilot connectors gallery
(`learn.microsoft.com/en-us/microsoft-365/copilot/connectors/connectors-gallery`).

### Official samples (GitHub, see `GITHUB_REPO_MAP.md` for detail)

- `.NET` and `Python` and `TypeScript` versions of a GitHub-issues
  connector sample (`microsoftgraph/msgraph-sample-github-connector-*`)
  — explicitly described as powering "Microsoft Search, Copilot in
  Teams, the Microsoft 365 Copilot app, and more."

## NEXUS_IDEA

- **NEXUS_IDEA:** Microsoft's synced-vs-federated split is a clean,
  directly-reusable framing for any future NEXUS connector design:
  "do we index this data (synced-style), or query it live via MCP at
  request time (federated-style)?" is exactly the design question
  NEXUS would face building its own connector to, say, GitHub issues or
  an external trading data source. Worth citing this exact
  vocabulary rather than inventing new terms.
- **NEXUS_IDEA:** Microsoft's explicit warning that "MCP plugin auth
  guidance doesn't automatically apply to connectors" is a useful
  caution for NEXUS too — if NEXUS ever builds both an MCP-facing
  capability and a separate data-sync capability, don't assume one
  auth model covers both; this session's own `.mcp.json` only has
  Playwright today, so this isn't an active issue, just a forward
  warning.
