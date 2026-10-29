# Architectural Backlog

## Company
- [ ] Engineer and verify reliable bidirectional Bodhi ↔ Atlas communication. The Slack/HexJack and browser-to-browser experiments are historical and unreliable; neither is operationally established (Chris's correction, 2026-10-29). Agree transport and ownership, identity/authentication and product isolation, delivery/reply semantics, timeout/retry/acknowledgement/duplicate handling, observability and recovery, and measurable reliability acceptance criteria before implementation and operational acceptance. No mechanism is selected or activated by this entry.
- [ ] Confirm remaining technology decision/ownership roles.
- [ ] Keep source authority map current as connectors/repositories become accessible.

## Harvey George
- [ ] Identify and inspect main application repository and production/release branch.
- [ ] Verify exact Laravel/Aimeos/PHP/EB versions.
- [ ] Reconcile CloudFront/WAF/ALB/EB/RDS/Valkey/CloudWatch runtime inventory.
- [ ] Resolve current session/cache ownership.
- [ ] Verify current observability/log shipping and security remediation deployment.
- [ ] Classify HG-ARCH pages and inspect architecture repository.
- [ ] Map 3D builder persistence/configuration/export ownership.

## Serpfix
- [ ] Inspect `serpfix-seo-intelligence`, `serpfix-terraform`, portal and architecture repositories.
- [ ] Map DynamoDB physical design and queue/event topology.
- [ ] Verify ECS task/service/image revisions and post-DEV-384 conformance.
- [ ] Verify schedules, IAM, alarms and diagnostics.
- [ ] Verify Feed Intelligence implementation/runtime boundary.
- [ ] Confirm renderer/evidence boundaries and current issue-detection catalogue.
