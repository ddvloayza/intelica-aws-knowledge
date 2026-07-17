# Analytics-Dev — Placement Guide

_Use this document when creating new resources in this account._  
_Last updated: 2026-07-17 14:42 UTC_

## Creating a Lambda Function

### Use this VPC: itl-0005-ana-dev-vpc-02
**ID:** `vpc-092dc05179287e08a`  
**CIDR:** `10.16.0.0/16`

### Recommended subnets (private, 2 AZs for HA)

| Name | ID | CIDR | AZ | Free IPs |
|---|---|---|---|---|
| itl-0005-ana-dev-vpc-02-private-eu-south-2a | `subnet-0b2520e045cf37cb0` | 10.16.0.0/24 | 2a | 237 |
| itl-0005-ana-dev-vpc-02-private-eu-south-2b | `subnet-013034a3fd02e9b17` | 10.16.1.0/24 | 2b | 244 |
| itl-0005-ana-dev-vpc-02-private-eu-south-2c | `subnet-03b22d8fce7ca6076` | 10.16.2.0/24 | 2c | 222 |

### IAM Execution Roles available for Lambda

- **aws-controltower-ForwardSnsNotificationRole** — policies: AWSLambdaBasicExecutionRole

_If none fits, create a new role with trust policy for `lambda.amazonaws.com`_

### KMS encryption
- Default key: **alias/itl-0005-ana-dev-ebs-02**

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

- `sg-085b5a07768a54d37` — sg-085b5a07768a54d37

### Existing RDS (reference)

**itl-0005-ana-dev-rds-dbaf-02**
- Engine: postgres 16.13 / Class: db.t3.micro
- Endpoint: `itl-0005-ana-dev-rds-dbaf-02.clukawgwmnvf.eu-south-2.rds.amazonaws.com:5432`
- KMS: _none_

---

## Adding a service to EKS

### Cluster: itl-0005-ana-dev-eks-af-02
- **VPC:** `vpc-092dc05179287e08a`
- **Status:** ACTIVE
- **Existing namespaces:** airflow, amazon-cloudwatch, amazon-guardduty, argocd, default

**To add a new service:** create a new namespace or deploy into an existing one.  
The ALB Ingress Controller creates ALBs automatically from Ingress resources.  
Use tag `elbv2.k8s.aws/cluster: itl-0005-ana-dev-eks-af-02` to associate an existing ALB.

---

## Creating an S3 Bucket

### Recommended configuration based on existing patterns
- **Region:** eu-south-2
- **Encryption:** SSE-KMS with key **alias/itl-0005-ana-dev-ebs-02**
- **Block all public access:** Yes (all 4 settings enabled)
- **Versioning:** Enabled for critical data
- **Logging:** Enabled pointing to a dedicated logs bucket

### Naming convention (based on existing buckets)
- Pattern: `itl-<assetid>-<account>-<purpose>-<number>`
- Example: `itl-0005-ana-dev-pub-s3-static-02`
