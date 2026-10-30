# Source Map

**Access reconciliation:** 2026-10-29. Access checks below are dated observations; recheck availability and permissions before use.

## Atlas durable memory
**Verified:** `hgarchitect/atlas` is Atlas's canonical durable operational/architectural memory. Canonical for curated principles, ADRs, architecture summaries, evidence gaps, focus, handoff, and cross-project routing. Not canonical for current runtime behaviour when stronger owning evidence exists.

## Architectural responsibility
**Agreed with Chris, 2026-10-29:** Atlas is Primary Architect for Harvey George Ltd and Secondary/Supporting Architect for SerpFix. Bodhi remains the primary AI architectural advisor for SerpFix. Both assistants provide independent perspectives and challenge each other's conclusions. See `ATLAS.md` and `OPERATING-MANUAL.md` for the governing charter and operating boundaries.

## Project routing and control planes
Harvey George and SERPfIX are distinct project/product contexts. Route to the correct owning systems before doing project work; never substitute one workspace for the other.

### SERPfIX
- Atlassian site: `https://serpfix.atlassian.net`.
- Jira project: `DEV`; Jira owns live delivery state.
- Agent control plane: Confluence space `Agents` (space key `AGENTS`) on `serpfix.atlassian.net`.
- Before executing a named agent task, load the current `Agent Operating Model`, `Agent Profile — Atlas`, `Shared Policies`, and the relevant current task definition from that Agents space.
- Do not copy task definitions into this repository; Confluence remains authoritative for them.

### Harvey George
- **Verified 2026-10-29:** Harvey George Atlassian site is `https://wereonit.atlassian.net`, separate from SERPfIX.
- Direct authenticated curl checks using the Harvey George environment variables returned HTTP 200 for Jira `GET /rest/api/3/myself` (active account) and Confluence `GET /wiki/rest/api/space?limit=1` (space listing accessible).
- These checks verify authentication and those read endpoints only; they do not establish project-specific permissions, write access, current delivery state or runtime conformance.
- **Verified local access configuration:** `HARVEYGEORGE_JIRA_API_TOKEN`, `HARVEYGEORGE_JIRA_EMAIL` and `HARVEYGEORGE_BASE_URL` are persisted in Chris's existing private shell environment configuration. Values must never be copied into this repository. The email alias was populated from `JIRA_USERNAME` because `JIRA_EMAIL` was absent.
- Explicitly load the private environment when a process has not inherited the aliases; recheck availability without printing values.
- HGW is the currently identified Harvey George website delivery Jira project; verify against the connected Harvey George site when live state matters.

### Atlassian connector constraint
**Verified alternative transport 2026-10-29:** Chris authorised direct curl access to the Harvey George site using the dedicated variables above, and the read checks succeeded. This provides a site-specific access path independently of the Atlassian connector's selected site. Verify the target base URL and use only the matching product credentials; never substitute SERPfIX credentials. This does not expand authority to deploy, alter production or perform unrelated writes.

The connector is documented here as exposing one Atlassian site at a time; its current selected site was not checked during this reconciliation. Before using the connector for Jira or Confluence work:

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

## Bodhi ↔ Atlas communication
**Current position — corrected by Chris, 2026-10-29:** Neither the Slack relay through HexJack nor the subsequent browser-to-browser experiment is an established operational communication capability. Chris reports reliability failures in both; previous claims of a proven end-to-end relay are superseded.

**Historical:** The Slack experiment used `#hg-architect` and `#serpfix-architect`, with one-way Slack-to-ChatGPT injection and a separate explicit return send. These route and implementation notes do not verify current connectivity or reliability. Historical details are retained in `OPERATING-MANUAL.md`; they are not activation or automatic-response instructions.

**Architectural objective / Needs verification:** reliable, bidirectional Bodhi ↔ Atlas communication requires further engineering, agreed acceptance criteria and verification. No replacement mechanism is adopted here. Track open decisions in `work/architectural-backlog.md`. Slack/chat, if used through an authorised path in future, remains collaboration evidence; promote durable architectural conclusions into the appropriate knowledge source.

## Google Drive
**Verified:** onboarding discovery used temporary documents including `Atlas - Harvey George Source Discovery - 2026-09-09`, `Atlas - Serpfix Source Discovery - 2026-09-09`, and `Atlas - Harvey George Ltd Architecture Baseline - 2026-09-09`. These are transitional working memory, not competing sources of truth.

## Implementation / architecture repositories
### Harvey George local workspace
**Verified 2026-10-29:** accessible local Git workspace is `/home/christopher/development/harveygeorge-workspace`. The previously suggested `/home/christopher/harveygeorge-workspace` does not exist on the checked host.

The following checkout paths and configured origin URLs were inspected locally:

| Checkout under `repos/` | Configured Bitbucket origin |
| --- | --- |
| `HG-Web` | `git@bitbucket.org:wereonit/HG-Web.git` |
| `HG-Web-php83-security` | `git@bitbucket.org:wereonit/HG-Web.git` |
| `harveygeorge-architecture` | `git@bitbucket.org:wereonit/harveygeorge-architecture.git` |
| `harveygeorge-terraform` | `git@bitbucket.org:wereonit/harveygeorge-terraform.git` |
| `playwright-tool` | `git@bitbucket.org:wereonit/playwright-tool.git` |
| `playwright-tool-hgw264` | `git@bitbucket.org:wereonit/playwright-tool.git` |

These are six local checkouts of four configured remote repository identities. Local presence and origin configuration do not establish remote reachability, freshness, branch suitability, implementation content, architecture acceptance or deployed revision. Those remain **Needs verification** before relying on them for architectural conclusions.

**Reported:** active SERPfIX repository identities include `serpfix-seo-intelligence`, `serpfix-portal`, `serpfix-terraform`, `serpfix-platform-architecture`, and `serpfix-seo-intelligence-architecture`; important product repositories are reported Bitbucket-hosted and have not yet been directly inspected. Do not describe them as inspected GitHub sources.

## Harvey George regression and change confidence
**Verified source access, 2026-10-29:** the named Bitbucket refs `wereonit/playwright-tool` main and `wereonit/HG-Web` release/production were fetched through local Git and selected source/tests inspected. This establishes read access and those specific observations; it does not establish comprehensive coverage, passing tests or deployed conformance.

- [HGW-258](https://wereonit.atlassian.net/browse/HGW-258): existing local Playwright platform epic.
- **Verified organisation, 2026-10-30:** [Testing Coverage and Stakeholder Overview](https://wereonit.atlassian.net/wiki/spaces/HEC/pages/205717506) is the stakeholder entry point; [Focused Tests and Feature Assurance](https://wereonit.atlassian.net/wiki/spaces/HEC/pages/215547905) owns per-case focused/asset evidence and feature proof/acceptance links; [coverage/backlog/audit](https://wereonit.atlassian.net/wiki/spaces/HEC/pages/215449692) maps platform gaps and retained legacy tasks. The catalogue below has twelve individual default journey pages, refreshed with executed 30 October evidence. These dated documentation/access observations do not establish a new execution or production conformance.
- [Regression authoring guide](https://wereonit.atlassian.net/wiki/spaces/HEC/pages/215580718) and [PW-12 checkout terms](https://wereonit.atlassian.net/wiki/spaces/HEC/pages/215613517): the developer-first worked example and its local evidence. HGW-274 retains the unresolved office report; a synthetic pass does not establish live CMS/deployment parity. Pre-deployment CI/CD remains a future goal.
- [Upgrade Acceptance Profiles and Coverage](https://wereonit.atlassian.net/wiki/spaces/HEC/pages/216498207) / [PB-01 backend contracts](https://wereonit.atlassian.net/wiki/spaces/HEC/pages/216072239) / [HGW-272](https://wereonit.atlassian.net/browse/HGW-272), verified 2026-10-30: delivered local critical/extended/focused baseline-candidate orchestration, coverage/legacy safety inventory and versioned aggregate report. Extended passed all fifteen cases per lane with cleanup/teardown; focused checkout terms and the schema-successor backend comparison also passed. Tool main `c8830c5` publishes tested runtime `4ddda42` plus the additive report-schema successor `ca63574`; both exact fingerprints and same-tree app pins are in the owning evidence/topic. Changed migration/dependency inputs require a specific synthetic upgrade proof; human release sign-off remains separate. HGW-272 is Done, broader epic In Progress, and CI/deployment/production operations remain inactive.
- [PS-01 native sitemap compilation](https://wereonit.atlassian.net/wiki/spaces/HEC/pages/216563714) / [HGW-190](https://wereonit.atlassian.net/browse/HGW-190), verified 2026-10-30: product/category/index generation passed through attested local storage with exact XML/MinIO/HTTP checks and owned cleanup; all twelve default journeys also passed. Scheduled jobs and real S3 publication remain production-only. Chris reviewed and merged [PR #307](https://bitbucket.org/wereonit/hg-web/pull-requests/307) into `feature/chris` at `647f22fc`; Git verified its complete tree equals tested guard `c8a6a088`. HGW-190 is Done for this local scope, with Jira/Confluence read back; no deployment or fresh runtime execution is claimed. Tool main `4912958b` owns the separate-profile `sitemap-integrity` runner/runbook. No production/staging request or release-branch operation occurred. CMS sitemap HGW-189 and CI/CD remain unstarted.
- [Journey catalogue](https://wereonit.atlassian.net/wiki/spaces/HEC/pages/206077953) and [local setup/runbook](https://wereonit.atlassian.net/wiki/spaces/HEC/pages/206045185): detailed test cases, instructions and dated evidence; verify current executable names in Toolbox source.
- [Testing and Change Confidence](../products/harvey-george/testing-and-change-confidence.md): Chris's confirmed architectural priority, feature sequencing, selected source evidence and remaining coverage/migration decisions. Jira/Confluence retain delivery and detailed testing truth.

## AWS/runtime
For both products, direct AWS/runtime evidence owns what is actually running. Exact accounts, regions, resource topology, IAM, alarms and deployed revisions remain Needs verification.

## Security
Do not store credentials, tokens or secrets here.
