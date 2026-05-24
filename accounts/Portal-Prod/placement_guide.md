# Portal-Prod — Placement Guide

_Use this document when creating new resources in this account._  
_Last updated: 2026-05-24 19:32 UTC_

## Creating a Lambda Function

### Use this VPC: itl-0003-portal-prd-vpc-02
**ID:** `vpc-0626d66632373c892`  
**CIDR:** `10.10.0.0/16`

### Recommended subnets (private, 2 AZs for HA)

| Name | ID | CIDR | AZ | Free IPs |
|---|---|---|---|---|
| itl-0003-portal-prd-private-2a | `subnet-042f934568c455b4c` | 10.10.3.0/24 | 2a | 129 |
| itl-0003-portal-prd-private-2b | `subnet-0c396a6c940028849` | 10.10.4.0/24 | 2b | 171 |
| itl-0003-portal-prd-private-2c | `subnet-00fec6232d3dc188d` | 10.10.8.0/24 | 2c | 249 |

### Security Groups used by existing Lambdas (reuse or create similar)

- `sg-0131238705f3bdd7e` — sg-0131238705f3bdd7e
- `sg-08bec69ca1d781aad` — itl-0003-portal-prd-lambda-fsx-log-export-02-sg
- `sg-039aecc570853bb45` — itl-0003-portal-prd-lambda-pg-audit-02-sg
- `sg-0097bc967b64e085e` — itl-0003-portal-prd-lambda-fee-external-custom-alert-02-sg

### IAM Execution Roles available for Lambda

- **aws-controltower-ForwardSnsNotificationRole** — policies: AWSLambdaBasicExecutionRole
- **AWS-QuickSetup-BaselineOverrides-LambdaRole-1yqvz**
- **AWS-QuickSetup-PatchPolicy-RoleForLambda-NT-us-east-1-1yqvz** — policies: AWSLambdaBasicExecutionRole
- **DatadogIntegration-Datado-LambdaExecutionRoleDatad-3YVYFQKD2081** — policies: AWSLambdaBasicExecutionRole
- **DatadogIntegration-ForwarderStack-WC-ForwarderRole-JSQA8ZV8AQME** — policies: AWSLambdaVPCAccessExecutionRole, AWSLambdaBasicExecutionRole
- **itl-0003-portal-prd-lambda-fee-external-custom-alert-02-role**
- **itl-0003-portal-prd-lambda-fsx-log-export-02-role**
- **itl-0003-portal-prd-lambda-pg-audit-02-role**

_If none fits, create a new role with trust policy for `lambda.amazonaws.com`_

### KMS encryption
- Default key: **alias/pci_2026**

### VPC Endpoints available (avoid NAT Gateway costs)
- **datasync** — Lambda can reach this service without going through NAT
- **guardduty-data** — Lambda can reach this service without going through NAT
- **logs** — Lambda can reach this service without going through NAT
- **s3** — Lambda can reach this service without going through NAT

### ⚠️ Important considerations
- Lambdas in private subnets use the NAT Gateway for external internet — cost: ~$0.045/GB
- Use the S3 VPC Endpoint to avoid NAT costs for S3 calls
- Use the Logs VPC Endpoint for CloudWatch Logs
- Each Lambda in a VPC needs at least 1 private IP per concurrent execution

### Existing Lambdas (reference patterns)

| Name | Runtime | Memory | Subnets |
|---|---|---|---|
| itl-0003-portal-prd-lambda-fee-external-custom-alert-02 | dotnet10 | 256MB | itl-0003-portal-prd-private-2b, itl-0003-portal-prd-private-2a |
| itl-0003-portal-prd-lambda-fsx-log-export-02 | python3.12 | 128MB | itl-0003-portal-prd-restricted-2b, itl-0003-portal-prd-restricted-2a |
| itl-0003-portal-prd-lambda-pg-audit-02 | python3.12 | 128MB | itl-0003-portal-prd-restricted-2b, itl-0003-portal-prd-restricted-2a |
| fortisiem-log-extractor | python3.12 | 512MB | itl-0003-portal-prd-private-2a |

---

## Creating an RDS Instance

### Recommended subnets (isolated — no internet)

| Name | ID | CIDR | AZ | Free IPs |
|---|---|---|---|---|
| itl-0003-portal-prd-restricted-2a | `subnet-0588eba1879cd168c` | 10.10.5.0/24 | 2a | 249 |
| itl-0003-portal-prd-restricted-2b | `subnet-0362f83b46f047126` | 10.10.6.0/24 | 2b | 248 |
| itl-0003-portal-prd-restricted-2c | `subnet-043e3fb731d433446` | 10.10.9.0/24 | 2c | 251 |

### Security Groups used by existing RDS (reuse or create similar)

- `sg-0634ee789467ac220` — itl-0003-portal-prd-rds-apps-02-sg

### Existing RDS (reference)

**itl-0003-portal-prd-rds-apps-02-instance-1**
- Engine: aurora-postgresql 16.11 / Class: db.serverless
- Endpoint: `itl-0003-portal-prd-rds-apps-02-instance-1.cp22y2qkmvn2.eu-south-2.rds.amazonaws.com:5432`
- KMS: alias/alias/itl-0003-portal-prd-kms-general-02

---

## Adding a service to EKS

### Cluster: itl-0003-portal-prd-eks-apps-02
- **VPC:** `vpc-0626d66632373c892`
- **Status:** ACTIVE
- **Existing namespaces:** amazon-cloudwatch, amazon-guardduty, appsmith, default, external, external-secrets, internal, metabase, monitoring

**To add a new service:** create a new namespace or deploy into an existing one.  
The ALB Ingress Controller creates ALBs automatically from Ingress resources.  
Use tag `elbv2.k8s.aws/cluster: itl-0003-portal-prd-eks-apps-02` to associate an existing ALB.

---

## Creating an S3 Bucket

### Recommended configuration based on existing patterns
- **Region:** eu-south-2
- **Encryption:** SSE-KMS with key **alias/pci_2026**
- **Block all public access:** Yes (all 4 settings enabled)
- **Versioning:** Enabled for critical data
- **Logging:** Enabled pointing to a dedicated logs bucket

### Naming convention (based on existing buckets)
- Pattern: `itl-<assetid>-<account>-<purpose>-<number>`
- Example: `itl-0003-portal-prd-nlb-logging-01`
