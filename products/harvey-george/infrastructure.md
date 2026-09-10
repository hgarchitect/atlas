# Harvey George — Infrastructure

**Verified high-level shape:** CloudFront/WAF -> ALB -> Elastic Beanstalk; RDS participates in production data architecture; deployments are pipeline-driven with EB lifecycle hooks.

**Reported:** ElastiCache/Valkey exists or existed, but consumers and responsibilities are unresolved.

**Needs verification:** exact AWS accounts/regions, CloudFront distributions, WAF/ALB/EB resources and revisions, RDS engine/topology, Valkey topology/use, CloudWatch/log groups/alarms, S3, Route 53, IAM, deployed app commit, and current session/cache configuration.

Direct AWS/runtime evidence owns deployed-state questions. Source-controlled deployment/IaC owns intended configuration where available.
