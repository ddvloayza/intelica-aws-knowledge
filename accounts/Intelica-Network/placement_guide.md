# Intelica-Network — Placement Guide

_Use this document when creating new resources in this account._  
_Last updated: 2026-07-12 01:20 UTC_

## Creating a Lambda Function

### Use this VPC: itl-0002-shared-network-all-vpc-02
**ID:** `vpc-000f7f02c4d4819a3`  
**CIDR:** `10.18.0.0/16`

### Recommended subnets (private, 2 AZs for HA)

| Name | ID | CIDR | AZ | Free IPs |
|---|---|---|---|---|
| itl-0002-shared-network-all-private-2a | `subnet-06e26c7cc455004c5` | 10.18.3.0/24 | 2a | 247 |
| itl-0002-shared-network-all-private-2b | `subnet-0624a59dbcfc36798` | 10.18.4.0/24 | 2b | 215 |

### IAM Execution Roles available for Lambda

- **aws-controltower-ForwardSnsNotificationRole** — policies: AWSLambdaBasicExecutionRole

_If none fits, create a new role with trust policy for `lambda.amazonaws.com`_

### KMS encryption
- Default key: **alias/alias/itl-0002-shared-network-all-kms-general-02**

### VPC Endpoints available (avoid NAT Gateway costs)
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

| Name | ID | CIDR | AZ | Free IPs |
|---|---|---|---|---|
| itl-0002-shared-network-all-restricted-2a | `subnet-0c9fc58aab4d826c2` | 10.18.5.0/24 | 2a | 251 |
| itl-0002-shared-network-all-restricted-2b | `subnet-011ec58c1a72d1d92` | 10.18.6.0/24 | 2b | 251 |

---

## Adding a service to EKS

### Cluster: itl-0002-shared-network-all-eks-pritunl-02
- **VPC:** `vpc-000f7f02c4d4819a3`
- **Status:** ACTIVE
- **Existing namespaces:** —

**To add a new service:** create a new namespace or deploy into an existing one.  
The ALB Ingress Controller creates ALBs automatically from Ingress resources.  
Use tag `elbv2.k8s.aws/cluster: itl-0002-shared-network-all-eks-pritunl-02` to associate an existing ALB.

---

## Creating an S3 Bucket

### Recommended configuration based on existing patterns
- **Region:** eu-south-2
- **Encryption:** SSE-KMS with key **alias/alias/itl-0002-shared-network-all-kms-general-02**
- **Block all public access:** Yes (all 4 settings enabled)
- **Versioning:** Enabled for critical data
- **Logging:** Enabled pointing to a dedicated logs bucket
