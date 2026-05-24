# Analytics-Prod — Placement Guide

_Use this document when creating new resources in this account._  
_Last updated: 2026-05-24 19:32 UTC_

## Creating a Lambda Function

### Use this VPC: itl-0005-ana-prd-vpc-02
**ID:** `vpc-0008aceba2432ab91`  
**CIDR:** `10.15.0.0/16`

### Recommended subnets (private, 2 AZs for HA)

| Name | ID | CIDR | AZ | Free IPs |
|---|---|---|---|---|
| itl-0005-ana-prd-vpc-02-private-eu-south-2a | `subnet-0d85a80ddb479d2fb` | 10.15.0.0/24 | 2a | 244 |
| itl-0005-ana-prd-vpc-02-private-eu-south-2b | `subnet-08d029e0c1f7e782e` | 10.15.1.0/24 | 2b | 235 |
| itl-0005-ana-prd-vpc-02-private-eu-south-2c | `subnet-04c4e78c5fef9f756` | 10.15.2.0/24 | 2c | 222 |

### IAM Execution Roles available for Lambda

- **aws-controltower-ForwardSnsNotificationRole** — policies: AWSLambdaBasicExecutionRole

_If none fits, create a new role with trust policy for `lambda.amazonaws.com`_

### KMS encryption
- Default key: **alias/itl-0005-ana-prd-ebs-02**

### VPC Endpoints available (avoid NAT Gateway costs)
- **s3** — Lambda can reach this service without going through NAT
- **api** — Lambda can reach this service without going through NAT
- **dkr** — Lambda can reach this service without going through NAT
- **guardduty-data** — Lambda can reach this service without going through NAT

### ⚠️ Important considerations
- Lambdas in private subnets use the NAT Gateway for external internet — cost: ~$0.045/GB
- Use the S3 VPC Endpoint to avoid NAT costs for S3 calls
- Use the Logs VPC Endpoint for CloudWatch Logs
- Each Lambda in a VPC needs at least 1 private IP per concurrent execution

### Existing Lambdas (reference patterns)

| Name | Runtime | Memory | Subnets |
|---|---|---|---|

---

## Creating an RDS Instance

### Recommended subnets (isolated — no internet)

_No isolated subnets found — use private subnets and restrict via SG_

### Security Groups used by existing RDS (reuse or create similar)

- `sg-074026ddbbdad7fbb` — sg-074026ddbbdad7fbb

### Existing RDS (reference)

**itl-0005-ana-prd-rds-dbaf-02**
- Engine: postgres 16.8 / Class: db.t3.micro
- Endpoint: `itl-0005-ana-prd-rds-dbaf-02.clkeeaayq0n0.eu-south-2.rds.amazonaws.com:5432`
- KMS: _none_

---

## Adding a service to EKS

### Cluster: itl-0005-ana-prd-eks-af-02
- **VPC:** `vpc-0008aceba2432ab91`
- **Status:** ACTIVE
- **Existing namespaces:** airflow, amazon-cloudwatch, amazon-guardduty, argocd, default

**To add a new service:** create a new namespace or deploy into an existing one.  
The ALB Ingress Controller creates ALBs automatically from Ingress resources.  
Use tag `elbv2.k8s.aws/cluster: itl-0005-ana-prd-eks-af-02` to associate an existing ALB.

---

## Creating an S3 Bucket

### Recommended configuration based on existing patterns
- **Region:** eu-south-2
- **Encryption:** SSE-KMS with key **alias/itl-0005-ana-prd-ebs-02**
- **Block all public access:** Yes (all 4 settings enabled)
- **Versioning:** Enabled for critical data
- **Logging:** Enabled pointing to a dedicated logs bucket

### Naming convention (based on existing buckets)
- Pattern: `itl-<assetid>-<account>-<purpose>-<number>`
- Example: `itl-0005-ana-prd-s3-airflow-logs-02`
