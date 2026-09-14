# Source Map

## Atlas durable memory
**Verified:** `hgarchitect/atlas` is Atlas's canonical durable operational/architectural memory. Canonical for curated principles, ADRs, architecture summaries, evidence gaps, focus, handoff, and cross-project routing. Not canonical for current runtime behaviour when stronger owning evidence exists.

## Project routing and control planes
Harvey George and SERPfIX are distinct project/product contexts. Route to the correct owning systems before doing project work; never substitute one workspace for the other.

### SERPfIX
- Atlassian site: `https://serpfix.atlassian.net`.
- Jira project: `DEV`; Jira owns live delivery state.
- Agent control plane: Confluence space `Agents` (space key `AGENTS`) on `serpfix.atlassian.net`.
- Before executing a named agent task, load the current `Agent Operating Model`, `Agent Profile — Atlas`, `Shared Policies`, and the relevant current task definition from that Agents space.
- Do not copy task definitions into this repository; Confluence remains authoritative for them.

### Harvey George
- Uses a separate Atlassian site from SERPfIX.
- Jira/Confluence work must be routed to that Harvey George site. The exact site URL should be recorded here once verified from an owning source/connector.
- HGW is the currently identified Harvey George website delivery Jira project; verify against the connected Harvey George site when live state matters.

### Atlassian connector constraint
The OpenAI Atlassian connector exposes only one Atlassian site at a time. Before Jira or Confluence work:
1. identify the target project;
2. verify the connected Atlassian site matches that project;
3. if it does not, stop rather than using the other workspace, tell Chris which project/site connection must be switched, and follow any task-specific failure procedure available from the control plane.

## Source ownership
- Jira: live delivery state, blockers and acceptance criteria. Jira status alone does not prove completion, production readiness, or runtime conformance.
- Project Confluence: durable project-documented truth.
- Project `Agents` space: current agent operating instructions, profiles, shared policies and executable task definitions.
- `hgarchitect/atlas`: concise cross-project architectural memory and routing; not a duplicate of Jira/Confluence.
- Running systems/AWS/telemetry: actual deployed/runtime behaviour.
- Implementation repositories, contracts, schemas and tests: executable behaviour.

## Slack / HexJack
**Verified:** architecture collaboration channels include `#hg-architect` and `#serpfix-architect`. Bodhi ↔ Atlas HexJack relay is proven end-to-end for substantive multi-turn conversation. Slack/chat is collaboration evidence, not permanent architecture memory; promote durable conclusions here.

## Google Drive
**Verified:** onboarding discovery used temporary documents including `Atlas - Harvey George Source Discovery - 2026-09-09`, `Atlas - Serpfix Source Discovery - 2026-09-09`, and `Atlas - Harvey George Ltd Architecture Baseline - 2026-09-09`. These are transitional working memory, not competing sources of truth.

## Implementation / architecture repositories
**Needs verification:** Harvey George main application repository exact slug/content. `wereonit/harveygeorge-architecture` is the identified intended Harvey George architecture repository identity, pending direct inspection/review state.

**Reported:** active SERPfIX repository identities include `serpfix-seo-intelligence`, `serpfix-portal`, `serpfix-terraform`, `serpfix-platform-architecture`, and `serpfix-seo-intelligence-architecture`; important product repositories are reported Bitbucket-hosted and have not yet been directly inspected. Do not describe them as inspected GitHub sources.

## AWS/runtime
For both products, direct AWS/runtime evidence owns what is actually running. Exact accounts, regions, resource topology, IAM, alarms and deployed revisions remain Needs verification.

## Security
Do not store credentials, tokens or secrets here.
