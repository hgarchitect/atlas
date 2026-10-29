# Harvey George — Current State

**Architecture baseline:** 2026-09-10  
**Access/source reconciliation:** 2026-10-29  
**Confidence:** mixed; classifications below are intentional.

## Verified
- Harvey George is a Laravel/Aimeos ecommerce application with substantial custom product-configuration and 3D-builder behaviour; this statement does not assert exact versions.
- Current production architecture is strongly supported at high level as CloudFront/WAF -> ALB -> Elastic Beanstalk with RDS and pipeline-driven deployment through EB lifecycle hooks.
- HGW is the current Harvey George website delivery project.

## Reported
- Laravel 12.x, Aimeos 2025.07, PHP 8.3 and Elastic Beanstalk AL2023 are strongly corroborated but require source/runtime confirmation.
- ElastiCache/Valkey exists or existed as a cache-related resource; current consumers/responsibilities are unresolved.
- 3D engineering material reports Three.js, `hgBuilderConfig`, GLB/config export, Aimeos-backed JSON configuration and Playwright capture; exact ownership/persistence awaits source inspection.

## Historical
- WooCommerce/K-Frame reconstruction is pre-current-platform history and must not be mixed into current Laravel/Aimeos state.
- A database-backed session migration is historical evidence contradicting the bootstrap shorthand “Redis sessions/cache”; current session/cache ownership must not be assumed.

## Needs verification
Authoritative app branch/commit and remote freshness; Laravel/Aimeos/PHP/EB platform versions; session/cache drivers and Valkey usage; AWS topology/resource names/IAM/alarms; RDS details; current observability/log shipping; integration/provider configuration; exact builder persistence/export ownership.

## Access and source discovery — verified 2026-10-29
- Harvey George Jira and Confluence are reachable at `https://wereonit.atlassian.net`. Authenticated curl checks returned HTTP 200 for Jira account identity and Confluence space listing.
- Local source workspace is `/home/christopher/development/harveygeorge-workspace`; the `repos/HG-Web` checkout has configured origin `git@bitbucket.org:wereonit/HG-Web.git`. Architecture, Terraform and Playwright checkouts are also present; see [Source Map](../../sources/SOURCE-MAP.md) for routing and the full inventory.
- This reconciliation establishes access and configured repository identities. It does not reverify the September architecture baseline, inspect application behaviour, establish Jira write permissions or prove production conformance.
