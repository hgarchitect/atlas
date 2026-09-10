# Serpfix — Current State

**Snapshot:** 2026-09-10  
**Confidence:** mixed; exact implementation/runtime remains to be inspected.

## Verified at current evidence level
- Shared platform is a thin boundary around portal/front door, identity/trust, control plane, tenant/product access, routing and product handoff; SEO Intelligence internals sit outside it.
- Current architecture/runtime patterns strongly support AWS-hosted ECS/container execution, DynamoDB durable state/evidence, asynchronous queue-backed processing, Terraform-managed infrastructure, shared scheduled-workload dispatch and independent external-observation lifecycles.
- DEV is the current engineering delivery project.
- Governing architecture and deployed conformance must be evaluated separately.

## Reported
- Feed Intelligence is a separate Serpfix product/capability stream with its own intended architecture/runtime repositories.

## Historical / superseded
- Older wording that `serpfix-platform-architecture` describes the platform as a whole is superseded by the thin-platform interpretation, pending direct repo confirmation.
- “Missing Canonical first” is stale delivery ordering. Current Jira prefers renderer-independent `non_200_status` first; `canonical_missing` is deferred pending authoritative rendered evidence.
- DEV-384 is a durable production-drift precedent: Terraform/configuration intent and deployed ECS application revisions can diverge.

## Needs verification
Exact repo contents/branches/ADRs/contracts/tests; Terraform state; DynamoDB keys/indexes; queue/event topology; ECS services/tasks/images; schedules; IAM/alarms; post-DEV-384 runtime conformance; Feed Intelligence implementation/runtime detail.
