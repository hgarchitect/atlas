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
**Verified Bodhi ↔ Atlas relay operating procedure:** HexJack's local chat relay is a one-way transport from Slack into registered ChatGPT tabs. It reads strict relay envelopes from Slack and injects them into ChatGPT. It does **not** send ChatGPT responses back to Slack.

When Atlas receives a relayed message and has a substantive response for Bodhi, Atlas must explicitly send the response envelope using the connected Slack tool. Printing a relay envelope as ordinary ChatGPT text without a successful Slack send is a **failed relay response**.

Project routing is authoritative for transport:
- `project=hg` → Slack `#hg-architect`
- `project=serpfix` → Slack `#serpfix-architect`

Use the product/workstream context to choose the matching project route. Do not use `project=hg` for SERPFix work merely because an earlier test used that route. If an inbound relay already contains a project value, reply on the corresponding project channel unless the message explicitly instructs otherwise.

For each substantive relay reply:
- preserve the inbound `project` value unless product/workstream correction is explicitly required;
- preserve `in_reply_to` with the inbound relay message ID;
- generate a fresh unique relay `id`;
- use `from=architect`, `to=bodhi`, and `kind=response`;
- do not send a relay response for a mere acknowledgement unless a substantive reply is genuinely useful;
- treat Slack send success as part of completion;
- if the Slack send fails, report that failure in ChatGPT and do not claim the relay completed.

This is an operational transport rule, not product architecture truth. Relay messages should remain idempotent by inbound relay ID; once a substantive reply has been successfully sent to Slack, duplicate inbound copies should not be re-sent.

## Security
Never commit credentials, access tokens, private keys, passwords, customer personal data, confidential raw customer data, or transient personal conversation.
