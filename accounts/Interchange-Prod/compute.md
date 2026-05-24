# Interchange-Prod — Compute

_Last updated: 2026-05-24 19:32 UTC_

## Lambda Functions

| Name | Runtime | Memory | Timeout | VPC | SGs |
|---|---|---|---|---|---|
| aws-controltower-NotificationForwarder | python3.13 | 128MB | 60s | **No VPC** | — |
| itl-0004-itx-prd-lambda-pg-audit-02 | python3.12 | 128MB | 60s | Yes | itl-0004-itx-prd-lambda-pg-audit-02-sg |
| itl-0004-itx-prd-lmbd-app-02 | python3.10 | 128MB | 3s | Yes | itl-0004-itx-prd-lmbd-app-02-sg |
| itl-0004-itx-prd-lmbd-file-load-02 | python3.10 | 128MB | 3s | Yes | itl-0004-itx-prd-lmbd-file-load-02-sg |
| itl-0004-itx-prd-lmbd-sendmail-02 | python3.10 | 128MB | 3s | Yes | itl-0004-itx-prd-lmbd-sendmail-02-sg |

### Lambda VPC Details

**itl-0004-itx-prd-lmbd-app-02**
- Runtime: python3.10 | Memory: 128MB | Timeout: 3s
- Subnets: itl-0004-itx-prod-private-2b, itl-0004-itx-prod-private-2a
- Execution role: `itl-0004-itx-prd-lmbd-app-02-role`
- KMS: alias/alias/itl-0004-itx-prd-kms-general-02
- Environment variable keys: QUEUES_URL_MAP

**itl-0004-itx-prd-lmbd-file-load-02**
- Runtime: python3.10 | Memory: 128MB | Timeout: 3s
- Subnets: itl-0004-itx-prod-private-2b, itl-0004-itx-prod-private-2a
- Execution role: `itl-0004-itx-prd-lmbd-file-load-02-role`
- KMS: alias/alias/itl-0004-itx-prd-kms-general-02
- Environment variable keys: INTERCHANGE_DATABASE_SECRET_ARN, BUCKET_NAME

**itl-0004-itx-prd-lmbd-sendmail-02**
- Runtime: python3.10 | Memory: 128MB | Timeout: 3s
- Subnets: itl-0004-itx-prod-private-2b, itl-0004-itx-prod-private-2a
- Execution role: `itl-0004-itx-prd-lmbd-sendmail-02-role`
- KMS: alias/alias/itl-0004-itx-prd-kms-general-02
- Environment variable keys: SMTP_SECRET_ARN

**itl-0004-itx-prd-lambda-pg-audit-02**
- Runtime: python3.12 | Memory: 128MB | Timeout: 60s
- Subnets: itl-0004-itx-prod-restricted-2b, itl-0004-itx-prod-restricted-2a
- Execution role: `itl-0004-itx-prd-lambda-pg-audit-02-role`
- KMS: _none_
- Environment variable keys: ACCOUNT_ID, PREFIX, LOG_GROUP, BUCKET_NAME

## EC2 Instances

| Name | Type | State | Subnet | Private IP |
|---|---|---|---|---|
| itl-0004-itx-prd-ec2-app-02 | r6g.2xlarge | running | itl-0004-itx-prod-private-2a | 10.13.3.233 |
| itl-0004-itx-prod-ec2-london-01 | x2iedn.4xlarge | running | itl-0004-itx-prod-private-2a | 10.13.3.231 |

## Load Balancers

### itl-0004-itx-prd-nlb-sftp-02 (NETWORK)
- **DNS:** `itl-0004-itx-prd-nlb-sftp-02-f9f0bec89a01e51a.elb.eu-south-2.amazonaws.com`
- **Scheme:** internet-facing
- **AZs:** eu-south-2a, eu-south-2b
