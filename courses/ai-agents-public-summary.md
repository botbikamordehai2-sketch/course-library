# AI Agents — Public Study Summary

## Source status
This page summarizes the central AI-agent material found in the Notion course library. It is not a transcript and does not claim to reproduce any one course verbatim.

## Architectural distinction
- **LLM:** language/reasoning engine.
- **Chatbot:** conversational interface.
- **RPA:** deterministic automation.
- **AI Agent:** goal-directed loop using reasoning, tools, state, and observations.

## Typical agent loop
Perceive → Reason → Act → Observe → update state → repeat until done or stopped.

## Production layers recorded in the notes
1. Model / reasoning engine
2. Orchestration and state
3. Tools / function calling / MCP
4. Memory and retrieval
5. Observability

## Multi-agent guidance
The Notion material emphasizes using multi-agent only when specialization, independent review, or real parallel work justifies the extra coordination cost.

Common patterns:
- Supervisor / coordinator
- Sequential pipeline
- Writer / critic
- Debate / competing proposals

## Governance themes
- least privilege
- human approval for high-impact actions
- sandboxing
- audit logs
- explicit failure handling
- separation between decision and execution
