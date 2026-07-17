# Interchange-Prod — Placement Guide

_Use this document when creating new resources in this account._  
_Last updated: 2026-07-17 14:42 UTC_

## Creating a Lambda Function

### Use this VPC: itl-0004-itx-prod-vpc-02
**ID:** `vpc-0c6863a32b8db36e0`  
**CIDR:** `10.13.0.0/16`

### Recommended subnets (private, 2 AZs for HA)

| Name | ID | CIDR | AZ | Free IPs |
|---|---|---|---|---|
| itl-0004-itx-prod-restricted-2a | `subnet-0ed8a143f2b994c42` | 10.13.5.0/24 | 2a | 248 |
| itl-0004-itx-prod-private-2a | `subnet-0922b864eefaddb05` | 10.13.3.0/24 | 2a | 238 |
| itl-0004-itx-prod-restricted-2b | `subnet-013b386fa64d33781` | 10.13.6.0/24 | 2b | 249 |
| itl-0004-itx-prod-private-2b | `subnet-03c90b860a79acd5e` | 10.13.4.0/24 | 2b | 241 |

### Security Groups used by existing Lambdas (reuse or create similar)

- `sg-0cf9b3d2905943753` — itl-0004-itx-prd-lmbd-sendmail-02-sg
- `sg-0d132d30a28741e82` — itl-0004-itx-prd-lmbd-app-02-sg
- `sg-0a9badb1aa57f04b6` — itl-0004-itx-prd-lambda-pg-audit-02-sg
- `sg-0fde3398d48e6fdb0` — itl-0004-itx-prd-lmbd-file-load-02-sg
- `sg-05cbf811c7de9d3f3` — itl-0004-itx-prd-lmbd-sbsa-preprocess-02

### IAM Execution Roles available for Lambda

- **app-interchange-lambda-fileload-dev-role-14gv3vwo** — policies: AWSLambdaBasicExecutionRole-12d7bf48-16b0-463f-8574-dff534a5d4ba
- **app-interchange-role-lambda-execution-dev** — policies: AWSLambdaBasicExecutionRole
- **app-interchange-role-lambda-execution-prd** — policies: AWSLambdaBasicExecutionRole
- **app-interchange-lambda-fileload-prod-role** — policies: app-interchange-lambda-fileload-prod-policy, AWSLambdaBasicExecutionRole
- **app-interchange-lambda-send_email-dev-role-n1bqvit1** — policies: AWSLambdaBasicExecutionRole-06969d10-9a60-4f65-8a4e-246a91510b81
- **app-interchange-lambda-fileload-dev-role-wlokah8j** — policies: AWSLambdaBasicExecutionRole-f768eb84-06ff-460c-ba91-f346fed26ddb
- **app-interchange-lambda-sbsa-upload-prd-role** — policies: app-interchange-lambda-upload-prd-role, AWSLambdaBasicExecutionRole
- **app-interchange-lambda-fileload-dev-role-wujayiyr** — policies: AWSLambdaBasicExecutionRole-4bfa6fc0-9368-44a6-af78-ceaf4f5087ce

_If none fits, create a new role with trust policy for `lambda.amazonaws.com`_

### KMS encryption
- Default key: **alias/itl-0004-itx-prd-kms-london-pan-encrypt-02**

### VPC Endpoints available (avoid NAT Gateway costs)
- **s3** — Lambda can reach this service without going through NAT
- **c-0002** — Lambda can reach this service without going through NAT
- **dynamodb** — Lambda can reach this service without going through NAT
- **sqs** — Lambda can reach this service without going through NAT
- **logs** — Lambda can reach this service without going through NAT
- **sns** — Lambda can reach this service without going through NAT
- **secretsmanager** — Lambda can reach this service without going through NAT
- **guardduty-data** — Lambda can reach this service without going through NAT

### ⚠️ Important considerations
- Lambdas in private subnets use the NAT Gateway for external internet — cost: ~$0.045/GB
- Use the S3 VPC Endpoint to avoid NAT costs for S3 calls
- Use the Logs VPC Endpoint for CloudWatch Logs
- Each Lambda in a VPC needs at least 1 private IP per concurrent execution

### Existing Lambdas (reference patterns)

| Name | Runtime | Memory | Subnets |
|---|---|---|---|
| itl-0004-itx-prd-lmbd-app-02 | python3.10 | 128MB | itl-0004-itx-prod-private-2b, itl-0004-itx-prod-private-2a |
| itl-0004-itx-prd-lmbd-file-load-02 | python3.10 | 128MB | itl-0004-itx-prod-private-2b, itl-0004-itx-prod-private-2a |
| itl-0004-itx-prd-lmbd-sendmail-02 | python3.10 | 128MB | itl-0004-itx-prod-private-2b, itl-0004-itx-prod-private-2a |
| itl-0004-itx-prd-lambda-pg-audit-02 | python3.12 | 128MB | itl-0004-itx-prod-restricted-2b, itl-0004-itx-prod-restricted-2a |
| itl-0004-itx-prd-lmbd-sbsa-preprocess-02 | python3.10 | 3000MB | itl-0004-itx-prod-private-2b, itl-0004-itx-prod-private-2a |

---

## Creating an RDS Instance

### Recommended subnets (isolated — no internet)

_No isolated subnets found — use private subnets and restrict via SG_

### Security Groups used by existing RDS (reuse or create similar)

- `sg-06619eddecd66bc23` — sg-06619eddecd66bc23
- `sg-0ddb2e33452d2a5ca` — itl-0004-itx-prd-rds-app-02-sg

### Existing RDS (reference)

**itl-0004-itx-prd-rds-analitycs-02**
- Engine: postgres 17.9 / Class: db.r5.large
- Endpoint: `itl-0004-itx-prd-rds-analitycs-02.cb2wsasugzte.eu-south-2.rds.amazonaws.com:5432`
- KMS: alias/alias/itl-0004-itx-prd-kms-general-02

**itl-0004-itx-prd-rds-app-02-1**
- Engine: aurora-postgresql 16.11 / Class: db.r5.2xlarge
- Endpoint: `itl-0004-itx-prd-rds-app-02-1.cb2wsasugzte.eu-south-2.rds.amazonaws.com:5432`
- KMS: alias/alias/itl-0004-itx-prd-kms-general-02

---

## Adding a service to EKS

_No EKS cluster found in this account._

---

## Creating an S3 Bucket

### Recommended configuration based on existing patterns
- **Region:** eu-south-2
- **Encryption:** SSE-KMS with key **alias/itl-0004-itx-prd-kms-london-pan-encrypt-02**
- **Block all public access:** Yes (all 4 settings enabled)
- **Versioning:** Enabled for critical data
- **Logging:** Enabled pointing to a dedicated logs bucket

### Naming convention (based on existing buckets)
- Pattern: `itl-<assetid>-<account>-<purpose>-<number>`
- Example: `itl-0004-itx-prd-s3-configuration-02`
