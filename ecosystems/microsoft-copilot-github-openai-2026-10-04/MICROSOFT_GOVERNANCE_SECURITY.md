# Microsoft Copilot Governance & Security

Sources: https://learn.microsoft.com/en-us/power-platform/release-plan/2026wave1/power-platform-governance-administration/manage-copilot-security-enhanced-admin-controls ,
https://learn.microsoft.com/en-us/microsoft-365/copilot/microsoft-365-copilot-privacy
(both fetched at search-snippet depth, not full-page)

## MICROSOFT_VERIFIED facts

- **Agent 365** — described as "now generally available," acting as "a
  control plane for observing, governing, and securing AI agents and
  their interactions through existing admin and security workflows."
  This is Microsoft's named product for agent governance specifically
  (distinct from general tenant admin).
- **Entra ID-based agent authentication policy**, settable at
  environment or environment-group level in the Power Platform admin
  center: admins choose one of — require Microsoft Entra ID auth,
  allow approved external auth providers, or prohibit anonymous access
  entirely. This is a tenant-wide default, not per-agent.
- **Copilot Control System** (Microsoft 365 admin center) — tenant-level
  agent policies controlling agent access, sharing, and publishing for
  *all* agents in the tenant. Admins choose which agents are allowed
  org-wide; a user can only access agents their admin allows AND that
  the user has installed/been assigned.
- **Per-user data permission model:** "Microsoft Copilot presenting
  only data that each individual can access using the same underlying
  controls for data access used in other Microsoft 365 services" —
  i.e., Copilot doesn't get its own separate permission system; it
  inherits the same ACLs that already govern the underlying M365 data.
- **Government cloud tiers** (GCC, GCCH, DoD) are explicitly supported
  for Copilot connectors specifically (see
  `MICROSOFT_PLUGINS_CONNECTORS.md`), implying governance/compliance
  posture was a first-class design constraint, not an afterthought.

## INFERENCE

- The combination of Agent 365 (control plane) + Copilot Control System
  (tenant policy) + per-user ACL inheritance suggests Microsoft's
  governance model has (at least) three distinct layers: a dedicated
  agent-observability product, a tenant-wide policy surface, and
  data-level permission inheritance. This three-layer structure is
  inferred from how the sources describe each piece separately, not
  stated as "three layers" by any single source.

## UNVERIFIED

- Exact scope of what Agent 365 actually observes/logs (telemetry
  detail, retention, audit log format).
- Whether Agent 365's "control plane" integrates with non-Microsoft
  agents (e.g. a NEXUS-style external agent) or only Microsoft-hosted
  ones.

## NEXUS_IDEA

- **NEXUS_IDEA:** the per-user ACL-inheritance principle ("Copilot
  doesn't get its own permission system") is exactly the design
  NEXUS's own `github_access_policy.py` and `project_autonomy_policy.py`
  already follow in spirit — NEXUS doesn't invent a parallel permission
  system either; it gates on top of GitHub's own repo access and an
  explicit per-project policy file. Worth citing Microsoft's framing as
  external validation if this design is ever questioned.
- **NEXUS_IDEA:** Agent 365's framing as a dedicated "control plane for
  observing, governing, and securing AI agents" is close to what
  `src/core/task_lease/dashboard.py` does at a much smaller scale
  (observability into lease state). Not a suggestion to build a
  Microsoft-scale product — just noting NEXUS already has a primitive
  version of this concept, worth knowing the market has a name for the
  category.
