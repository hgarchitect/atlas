# Current Architectural Focus

**Updated:** 2026-10-29

Bootstrap has moved from scaffold creation into evidence-backed verification. `hgarchitect/atlas` is now the durable memory target; Drive handoffs are transitional.

## Harvey George priority — confirmed by Chris, 2026-10-29
Build dependable local regression confidence through the existing HGW-258 programme before relying on further upgrades or broad interface changes. Verify a baseline on explicitly selected current application/toolbox revisions; capture Carl's reported admin regressions as executable cases; protect JSON API contracts before retirement. Security verification remains necessary alongside functional tests.

Preserve Save Progress/email recovery (HGW-237) first and referrals/finance worklist (HGW-238) second. Their independent correctness proofs remain in their feature epics. See [Testing and Change Confidence](../products/harvey-george/testing-and-change-confidence.md) for evidence, gaps and unresolved decisions. Detailed delivery state remains in Jira/Confluence.

## Existing cross-product verification backlog
1. Verify implementation repositories: Harvey George main app and Serpfix `serpfix-seo-intelligence` first.
2. Verify infrastructure intent: Serpfix `serpfix-terraform`; Harvey George deployment/infrastructure source and pipeline configuration.
3. Verify governing architecture repositories/ADRs: Harvey George architecture repo, then Serpfix platform and SEO architecture repos.
4. Reconcile intended architecture against direct AWS runtime for both products.
5. Resolve highest-risk conflicts: HG session/cache and observability; Serpfix post-DEV-384 conformance, queue/event topology and renderer/evidence boundaries.
6. Verify architecture-significant external integrations after core source/runtime truth.
7. Promote durable conclusions here with evidence class/conflicts preserved.
8. Redesign/remediate only where evidence establishes a real problem, trade-off or boundary failure.
