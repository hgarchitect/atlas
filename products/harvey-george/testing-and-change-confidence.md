# Harvey George — Testing and Change Confidence

**Direction agreed with Chris:** 2026-10-29.

## Architectural priority
A dependable, repeatable local regression capability is the enabling priority for security maintenance, framework/dependency upgrades and product development. Capture behaviour as executable assertions rather than relying on humans to rediscover regressions after each change. Human acceptance and visual review remain useful alongside automated checks.

Preserve the existing customer-experience sequence: **Save Progress and email recovery (HGW-237) first; referral vouchers and finance worklist (HGW-238) second.** Chris confirmed both are documented requirements. Testing enables these features; it does not replace their business-specific correctness gates.

Use the existing **HGW-258 Playwright testing platform epic** as the starting point. Do not infer that unrelated/unparented old tickets are obsolete; revalidate their scope and evidence before proposing disposition.

## Owning sources and inspected evidence
- [HGW-258](https://wereonit.atlassian.net/browse/HGW-258) owns the current local browser-testing programme; feature-specific proofs remain [HGW-255](https://wereonit.atlassian.net/browse/HGW-255) and [HGW-256](https://wereonit.atlassian.net/browse/HGW-256).
- [Journey catalogue](https://wereonit.atlassian.net/wiki/spaces/HEC/pages/206077953), [local setup/runbook](https://wereonit.atlassian.net/wiki/spaces/HEC/pages/206045185), and [results/visual regression](https://wereonit.atlassian.net/wiki/spaces/HEC/pages/205914122) own detailed testing instructions and dated acceptance evidence.
- **Verified in code, 2026-10-29:** after fetching Bitbucket main, `wereonit/playwright-tool` at `5d9421745614c20ddee1ab6503eb1ead55ace0fe` registers ten native storefront journeys plus a separate `3d-handle-consistency` scenario in `src/functional/scenarios/catalogue.ts`. `docs/journeys.md` documents extending the suite. This is source verification, not a new test run.
- **Verified in code:** fetched HG-Web `release/production` at `5feea1ae9bdbadb825064d11285029e7a1271e95` contains PHP unit/feature tests, including authentication, profile/delivery address, GLB upload and upgrade-baseline checks. Its lockfile records Laravel v12.33.0 and Aimeos Laravel/JSON API 2025.07.1. These are repository facts, not verified deployed runtime versions or evidence that the suites currently pass.
- Existing journey acceptance material is pinned to HG-Web development integration `1ae532ca92412a49934fc9c760be05279b62f0e5`. A clean compatible run on the selected current release candidate remains **Needs verification**. A local checkout/default branch may lag its fetched reference; always record explicit application/toolbox revisions and preserve existing worktrees.

## Material coverage gaps and next decisions
- **Reported by Chris:** Carl has found admin-panel regressions following a Laravel upgrade. Exact reproducible cases must be captured with expected behaviour, fixture/role, test identifier and linked defect; individual new cases were not independently inspected during this review.
- The inspected native catalogue is storefront-centred. An admin asset-overlay demonstration and PHP checks do not establish comprehensive admin product/variant editing, media upload or bespoke workflow regression coverage.
- [ADR-021](https://wereonit.atlassian.net/wiki/spaces/HA/pages/213385217), version 3, reports PHP-hardening deployment but explicitly says functional upload/login journeys were not exercised. Configuration/deployment success and functional compatibility are separate evidence questions. Browser passes alone do not prove security remediation; retain appropriate dependency, runtime/configuration and focused security checks.
- **Verified in selected source:** JSON API references remain in HG-Web middleware and custom builder/basket/checkout code. Chris wants to retire the old interface. First inventory consumers and characterise authentication/session/CSRF, request/response and commercial behaviour with contract/integration tests, backed by browser journeys. Replacement choice, retirement date and staged migration acceptance remain **unresolved**; do not assert an upstream deadline.
- **Reported by Confluence:** real storefront visual baselines have not been human-approved and CI remains planning-only. Prove repeatable local smoke/regression execution, deterministic synthetic fixtures, meaningful assertions, diagnostic outcomes and cleanup before deciding on additional automation infrastructure.
- Proposed expansion of coverage under HGW-258 is a recommendation awaiting Jira refinement; no new issues, workflow transitions, completion authorisations, CI implementation or deployments were made in this review.

Use unit tests for isolated rules, integration/contract tests for API and persistence boundaries, and browser tests for critical UI journeys. Add an appropriate regression test when fixing a demonstrated defect. Choose acceptance criteria and the first admin coverage slice with Chris and Carl; avoid claiming a coverage percentage or full-system confidence from test counts.

## Boundaries
Follow workspace and repository guidance. Execute only against explicitly selected, disposable local application/fixture environments using the guarded Toolbox. Never automatically target `harvey-george.com` or its subdomains. Do not weaken revision/fixture identity checks to force a run, and scope any HG-Web test-support changes separately from tooling changes.
