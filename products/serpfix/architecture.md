# Serpfix — Architecture

## Shared platform
Thin customer-facing/control-plane boundary: portal/front door, identity/trust, tenant/product access, routing, cross-product navigation/handoff, and approval of work entering specialist product engines. It does not own specialist engine internals.

## SEO Intelligence
Specialist engine boundary. Current governing evidence places crawl orchestration, fetch/render capability, evidence/snapshot handling, external signal observation, SERP/keyword intelligence, graph analysis, issue lifecycle, prioritisation and related execution here.

Current patterns strongly support ECS/container execution, DynamoDB durable state/evidence, async queue-backed processing, Terraform-managed infrastructure, shared scheduled dispatch and independent observation lifecycles. Exact topology is not yet verified.

## Feed Intelligence
Separate product/capability stream where currently known. Detailed implementation/runtime boundary remains provisional.

Conceptual boundaries do not mandate one deployable service per concept.
