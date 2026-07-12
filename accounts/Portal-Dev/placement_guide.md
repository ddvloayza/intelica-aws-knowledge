# Portal-Dev — Placement Guide

_Use this document when creating new resources in this account._  
_Last updated: 2026-07-12 17:54 UTC_

## Creating a Lambda Function

### Use this VPC: itl-0003-portal-dev-vpc-02
**ID:** `vpc-0fbd191d169cc9efb`  
**CIDR:** `10.12.0.0/16`

### Recommended subnets (private, 2 AZs for HA)

| Name | ID | CIDR | AZ | Free IPs |
|---|---|---|---|---|
| itl-0003-portal-dev-private-2a | `subnet-0c353ee340c3da15e` | 10.12.3.0/24 | 2a | 139 |
| itl-0003-portal-dev-private-2b | `subnet-05c87676a0cbfce54` | 10.12.4.0/24 | 2b | 108 |

### Security Groups used by existing Lambdas (reuse or create similar)

- `sg-0a4a3d94379c8d963` — itl-0003-portal-dev-lambda-sync-buk-organization-03-sg
- `sg-0454300e4d0c1f411` — itl-0003-portal-dev-lambda-fee-external-custom-alert-03-sg
- `sg-01f1fa4ca795113d8` — itl-0003-portal-dev-lambda-sync-jira-03-sg
- `sg-054b6a28f76db503c` — itl-0003-portal-dev-lambda-pg-audit-03-sg
- `sg-06717f2261d9bef36` — itl-0003-portal-dev-lambda-sync-buk-absence-03-sg

### IAM Execution Roles available for Lambda

- **aws-controltower-ForwardSnsNotificationRole** — policies: AWSLambdaBasicExecutionRole
- **django-app-role-ximfljqh** — policies: AWSLambdaBasicExecutionRole-2d785db2-d053-40d6-a23b-a30dda6831c4
- **f_cole-role-eysgoxjk** — policies: AWSLambdaBasicExecutionRole-3e1ad495-c34e-411b-949f-bebdb41e45ae
- **itl-0003-portal-dev-lambda-fee-external-custom-alert-03-role**
- **itl-0003-portal-dev-lambda-pg-audit-03-role**
- **itl-0003-portal-dev-lambda-pgaudit-01-role** — policies: AWSQuickSightIAMPolicy, AmazonSageMakerQuickSightVPCPolicy
- **itl-0003-portal-dev-lambda-sync-buk-absence-03-role**
- **itl-0003-portal-dev-lambda-sync-buk-organization-03-role**

_If none fits, create a new role with trust policy for `lambda.amazonaws.com`_

### KMS encryption
- Default key: **alias/alias/itl-0003-portal-dev-kms-general-03**

### VPC Endpoints available (avoid NAT Gateway costs)
- **s3** — Lambda can reach this service without going through NAT
- **datasync** — Lambda can reach this service without going through NAT
- **logs** — Lambda can reach this service without going through NAT
- **guardduty-data** — Lambda can reach this service without going through NAT

### ⚠️ Important considerations
- Lambdas in private subnets use the NAT Gateway for external internet — cost: ~$0.045/GB
- Use the S3 VPC Endpoint to avoid NAT costs for S3 calls
- Use the Logs VPC Endpoint for CloudWatch Logs
- Each Lambda in a VPC needs at least 1 private IP per concurrent execution

### Existing Lambdas (reference patterns)

| Name | Runtime | Memory | Subnets |
|---|---|---|---|
| itl-0003-portal-dev-lambda-sync-jira-03 | dotnet10 | 256MB | itl-0003-portal-dev-private-2b, itl-0003-portal-dev-private-2a |
| itl-0003-portal-dev-lambda-sync-buk-absence-03 | dotnet10 | 256MB | itl-0003-portal-dev-private-2b, itl-0003-portal-dev-private-2a |
| itl-0003-portal-dev-lambda-sync-buk-organization-03 | dotnet10 | 256MB | itl-0003-portal-dev-private-2b, itl-0003-portal-dev-private-2a |
| itl-0003-portal-dev-lambda-pg-audit-03 | python3.12 | 128MB | itl-0003-portal-dev-restricted-2b, itl-0003-portal-dev-restricted-2a |
| itl-0003-portal-dev-lambda-fee-external-custom-alert-03 | dotnet10 | 256MB | itl-0003-portal-dev-private-2b, itl-0003-portal-dev-private-2a |

---

## Creating an RDS Instance

### Recommended subnets (isolated — no internet)

| Name | ID | CIDR | AZ | Free IPs |
|---|---|---|---|---|
| itl-0003-portal-dev-restricted-2a | `subnet-0a244b304a580c5e3` | 10.12.5.0/24 | 2a | 248 |
| itl-0003-portal-dev-restricted-2b | `subnet-085c2712bbea48a30` | 10.12.6.0/24 | 2b | 246 |

### Security Groups used by existing RDS (reuse or create similar)

- `sg-0964ec984f5d5efbc` — itl-0003-portal-dev-rds-apps-03-sg

### Existing RDS (reference)

**itl-0003-portal-dev-rds-apps-03-instance-1**
- Engine: aurora-postgresql 16.11 / Class: db.serverless
- Endpoint: `itl-0003-portal-dev-rds-apps-03-instance-1.cls68qmcosaf.eu-south-2.rds.amazonaws.com:5432`
- KMS: alias/alias/itl-0003-portal-dev-kms-general-03

---

## Adding a service to EKS

### Cluster: itl-0003-portal-dev-eks-apps-03
- **VPC:** `vpc-0fbd191d169cc9efb`
- **Status:** ACTIVE
- **Existing namespaces:** airflow, amazon-cloudwatch, amazon-guardduty, appsmith, default, external, external-secrets, internal, metabase

**To add a new service:** create a new namespace or deploy into an existing one.  
The ALB Ingress Controller creates ALBs automatically from Ingress resources.  
Use tag `elbv2.k8s.aws/cluster: itl-0003-portal-dev-eks-apps-03` to associate an existing ALB.

---

## Creating an S3 Bucket

### Recommended configuration based on existing patterns
- **Region:** eu-south-2
- **Encryption:** SSE-KMS with key **alias/alias/itl-0003-portal-dev-kms-general-03**
- **Block all public access:** Yes (all 4 settings enabled)
- **Versioning:** Enabled for critical data
- **Logging:** Enabled pointing to a dedicated logs bucket

### Naming convention (based on existing buckets)
- Pattern: `itl-<assetid>-<account>-<purpose>-<number>`
- Example: `itl-0003-portal-dev-s3-airflow-logs-03`
