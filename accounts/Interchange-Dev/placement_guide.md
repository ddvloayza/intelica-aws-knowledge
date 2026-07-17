# Interchange-Dev — Placement Guide

_Use this document when creating new resources in this account._  
_Last updated: 2026-07-17 14:42 UTC_

## Creating a Lambda Function

### Use this VPC: itl-0004-itx-dev-vpc-02
**ID:** `vpc-0101d2c447b67e9db`  
**CIDR:** `10.14.0.0/16`

### Recommended subnets (private, 2 AZs for HA)

| Name | ID | CIDR | AZ | Free IPs |
|---|---|---|---|---|
| itl-0004-itx-dev-private-2a | `subnet-0b02ad525f046501b` | 10.14.3.0/24 | 2a | 231 |
| itl-0004-itx-dev-private-2b | `subnet-03cb8477fb39f639e` | 10.14.4.0/24 | 2b | 233 |

### Security Groups used by existing Lambdas (reuse or create similar)

- `sg-0f93fba3d7978e8d6` — itl-0004-itx-dev-lmbd-app-02-sg
- `sg-08e80112c0389743c` — itl-0004-itx-dev-lmbd-sendmail-02-sg
- `sg-0e1edda6ab1eed290` — itl-0004-itx-dev-lambda-pg-audit-02-sg
- `sg-0ea832a8a272949c3` — sg-0ea832a8a272949c3
- `sg-0671b8f0fb5aa27ca` — sg-0671b8f0fb5aa27ca
- `sg-0d9bb259e3a608ad0` — sg-0d9bb259e3a608ad0
- `sg-0b8b779c168840f49` — itl-0004-itx-dev-lmbd-sbsa-preprocess-02
- `sg-07565e1ecf3294bf9` — sg-07565e1ecf3294bf9
- `sg-0ad22b09c390c7209` — itl-0004-itx-dev-lmbd-file-load-02-sg

### IAM Execution Roles available for Lambda

- **AWS-QuickSetup-SSM-LifecycleManagement-LA-us-east-1** — policies: AWSQuickSetupSSMLifecycleManagementExecutionPolicy
- **aws-controltower-ForwardSnsNotificationRole** — policies: AWSLambdaBasicExecutionRole
- **itl-0004-itx-dev-intchg-02-lmbd-mc-exchange-rates-role**
- **itl-0004-itx-dev-intchg-02-lmbd-mc-role**
- **itl-0004-itx-dev-intchg-02-lmbd-vi-exchange-rates-role**
- **itl-0004-itx-dev-intchg-02-lmbd-vi-role**
- **itl-0004-itx-dev-lmbd-app-02-role**
- **itl-0004-itx-dev-lambda-pg-audit-02-role**

_If none fits, create a new role with trust policy for `lambda.amazonaws.com`_

### KMS encryption
- Default key: **alias/alias/itl-0004-itx-dev-kms-general-02**

### VPC Endpoints available (avoid NAT Gateway costs)
- **c-0002** — Lambda can reach this service without going through NAT
- **s3** — Lambda can reach this service without going through NAT
- **dynamodb** — Lambda can reach this service without going through NAT
- **sns** — Lambda can reach this service without going through NAT
- **sqs** — Lambda can reach this service without going through NAT
- **secretsmanager** — Lambda can reach this service without going through NAT
- **logs** — Lambda can reach this service without going through NAT
- **guardduty-data** — Lambda can reach this service without going through NAT
- **states** — Lambda can reach this service without going through NAT
- **lambda** — Lambda can reach this service without going through NAT

### ⚠️ Important considerations
- Lambdas in private subnets use the NAT Gateway for external internet — cost: ~$0.045/GB
- Use the S3 VPC Endpoint to avoid NAT costs for S3 calls
- Use the Logs VPC Endpoint for CloudWatch Logs
- Each Lambda in a VPC needs at least 1 private IP per concurrent execution

### Existing Lambdas (reference patterns)

| Name | Runtime | Memory | Subnets |
|---|---|---|---|
| itl-0004-itx-dev-intchg-02-lmbd-unzip | python3.11 | 1024MB | itl-0004-itx-dev-private-2b, itl-0004-itx-dev-private-2a |
| itl-0004-itx-dev-lmbd-sendmail-02 | python3.10 | 128MB | itl-0004-itx-dev-private-2b, itl-0004-itx-dev-private-2a |
| itl-0004-itx-dev-intchg-02-lmbd-vi-transform | python3.11 | 10240MB | itl-0004-itx-dev-private-2b, itl-0004-itx-dev-private-2a |
| itl-0004-itx-dev-intchg-02-lmbd-mc-exchange-rates | python3.11 | 512MB | itl-0004-itx-dev-private-2b, itl-0004-itx-dev-private-2a |
| itl-0004-itx-dev-intchg-02-lmbd-vi-extract | python3.11 | 10240MB | itl-0004-itx-dev-private-2b, itl-0004-itx-dev-private-2a |
| itl-0004-itx-dev-lambda-pg-audit-02 | python3.12 | 128MB | itl-0004-itx-dev-restricted-2b, itl-0004-itx-dev-restricted-2a |
| itl-0004-itx-dev-intchg-02-lmbd-test-1 | python3.11 | 512MB | itl-0004-itx-dev-private-2b, itl-0004-itx-dev-private-2a |
| itl-0004-itx-dev-intchg-02-lmbd-router | python3.11 | 8192MB | itl-0004-itx-dev-private-2b, itl-0004-itx-dev-private-2a |
| itl-0004-itx-dev-intchg-02-lmbd-vi-exchange-rates |  | 2048MB | itl-0004-itx-dev-private-2b, itl-0004-itx-dev-private-2a |
| itl-0004-itx-dev-intchg-02-lmbd-vi-clean | python3.11 | 10240MB | itl-0004-itx-dev-private-2b, itl-0004-itx-dev-private-2a |
| itl-0004-itx-dev-intchg-02-lmbd-archive-file | python3.11 | 8192MB | itl-0004-itx-dev-private-2b, itl-0004-itx-dev-private-2a |
| itl-0004-itx-dev-lmbd-file-load-02 | python3.10 | 128MB | itl-0004-itx-dev-private-2b, itl-0004-itx-dev-private-2a |
| itl-0004-itx-dev-lmbd-sbsa-preprocess-02 | python3.10 | 512MB | itl-0004-itx-dev-private-2b, itl-0004-itx-dev-private-2a |
| itl-0004-itx-dev-lmbd-app-02 | python3.10 | 128MB | itl-0004-itx-dev-private-2b, itl-0004-itx-dev-private-2a |
| itl-0004-itx-dev-intchg-02-lmbd-test-2 | python3.11 | 512MB | itl-0004-itx-dev-private-2b, itl-0004-itx-dev-private-2a |
| itl-0004-itx-dev-intchg-02-lmbd-vi-store | python3.11 | 10240MB | itl-0004-itx-dev-private-2b, itl-0004-itx-dev-private-2a |

---

## Creating an RDS Instance

### Recommended subnets (isolated — no internet)

| Name | ID | CIDR | AZ | Free IPs |
|---|---|---|---|---|
| itl-0004-itx-dev-restricted-2a | `subnet-09162acc62b24d7cb` | 10.14.5.0/24 | 2a | 249 |
| itl-0004-itx-dev-restricted-2b | `subnet-05dae71c2f90dc501` | 10.14.6.0/24 | 2b | 250 |

### Security Groups used by existing RDS (reuse or create similar)

- `sg-07040d29e788f886d` — itl-0004-itx-dev-rds-app-02-sg

### Existing RDS (reference)

**itl-0004-itx-dev-rds-app-02-1**
- Engine: aurora-postgresql 16.11 / Class: db.r5.large
- Endpoint: `itl-0004-itx-dev-rds-app-02-1.ct2k6yaewech.eu-south-2.rds.amazonaws.com:5432`
- KMS: alias/alias/itl-0004-itx-dev-kms-general-02

---

## Adding a service to EKS

_No EKS cluster found in this account._

---

## Creating an S3 Bucket

### Recommended configuration based on existing patterns
- **Region:** eu-south-2
- **Encryption:** SSE-KMS with key **alias/alias/itl-0004-itx-dev-kms-general-02**
- **Block all public access:** Yes (all 4 settings enabled)
- **Versioning:** Enabled for critical data
- **Logging:** Enabled pointing to a dedicated logs bucket

### Naming convention (based on existing buckets)
- Pattern: `itl-<assetid>-<account>-<purpose>-<number>`
- Example: `itl-0004-itx-dev-intchg-02-s3-analytics`
