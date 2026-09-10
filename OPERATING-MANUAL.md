# Atlas Operating Manual

## Memory model
`hgarchitect/atlas` is curated durable architecture memory. Promote architectural meaning here when it will matter in future sessions. Temporary Drive handoffs are transitional discovery aids, not permanent competing memory.

Implementation and runtime truth remain in their owning systems.

## Question-specific authority
Authority depends on the question, not simply recency or document location:
- running system/AWS/telemetry: what is actually deployed and behaving now
- implementation repositories, contracts, schemas, tests: executable behaviour
- infrastructure-as-code/configuration: intended infrastructure
- accepted architecture/ADRs: governing architectural intent
- Jira: delivery status, blockers, acceptance criteria
- product/Confluence material: product definition and classified supporting context
- Drive: working/business/historical material unless explicitly authoritative
- Atlas repo: curated architectural understanding, decisions, source map, evidence gaps

Governing architecture and deployed conformance are separate questions. Jira Done, Confluence status, IaC intent, or release documentation alone do not prove runtime conformance.

## Evidence classes
**Verified:** supported strongly enough by the strongest available owning evidence.  
**Reported:** current owning/supporting material says it is true, but stronger source/runtime evidence exists and has not been inspected.  
**Inferred:** reasoned conclusion from multiple evidence items.  
**Needs verification:** plausible/material claim without sufficient owning evidence.  
**Historical:** useful past-state evidence; never assume current.

## Workflow
Discover -> verify -> reason -> decide -> implement -> document -> retain.

Before material recommendations, identify the affected boundary, retrieve canonical Atlas context, inspect owning source/runtime evidence where possible, identify conflicts, and make assumptions explicit. Unknown/not-evaluated is a valid outcome.

## Relay operating model
**Verified:** Bodhi ↔ Atlas substantive chat relay works end-to-end through HexJack and Slack and supports multi-turn conversation. Architecture channels are `#hg-architect` and `#serpfix-architect`. Relay messages should be idempotent by inbound relay ID; once successfully delivered, duplicate inbound copies should not be re-sent. A chat-only response is incomplete when the relay instruction requires Slack delivery.

## Security
Never commit credentials, access tokens, private keys, passwords, customer personal data, confidential raw customer data, or transient personal conversation.
