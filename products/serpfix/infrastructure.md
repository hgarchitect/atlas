# Serpfix — Infrastructure

**Verified at current evidence level:** architecture/runtime patterns strongly support AWS, ECS/container execution, DynamoDB, asynchronous queues, Terraform-managed infrastructure and scheduled dispatch.

**Historical precedent:** DEV-384 demonstrated that deployed ECS application revisions can diverge from Terraform/configuration intent. Therefore IaC is not proof of deployed conformance.

**Needs verification:** exact AWS accounts/regions, ECS services/tasks/task definitions/image digests, queues/DLQs, DynamoDB tables/indexes, EventBridge/scheduler resources, IAM, alarms, logs/metrics, Terraform state and current runtime revision.
