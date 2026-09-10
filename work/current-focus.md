# Current Architectural Focus

**Updated:** 2026-09-10

Bootstrap has moved from scaffold creation into evidence-backed verification. `hgarchitect/atlas` is now the durable memory target; Drive handoffs are transitional.

## Highest-value verification sequence
1. Verify implementation repositories: Harvey George main app and Serpfix `serpfix-seo-intelligence` first.
2. Verify infrastructure intent: Serpfix `serpfix-terraform`; Harvey George deployment/infrastructure source and pipeline configuration.
3. Verify governing architecture repositories/ADRs: Harvey George architecture repo, then Serpfix platform and SEO architecture repos.
4. Reconcile intended architecture against direct AWS runtime for both products.
5. Resolve highest-risk conflicts: HG session/cache and observability; Serpfix post-DEV-384 conformance, queue/event topology and renderer/evidence boundaries.
6. Verify architecture-significant external integrations after core source/runtime truth.
7. Promote durable conclusions here with evidence class/conflicts preserved.
8. Redesign/remediate only where evidence establishes a real problem, trade-off or boundary failure.
