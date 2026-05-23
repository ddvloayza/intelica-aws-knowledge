# Portal-Prod — Compute

_Last updated: 2026-05-23 18:52 UTC_

## EKS Clusters

### itl-0003-portal-prd-eks-apps-02

**ARN:** `arn:aws:eks:eu-south-2:610944808410:cluster/itl-0003-portal-prd-eks-apps-02`  
**VPC:** `vpc-0626d66632373c892`  
**Status:** ACTIVE  
**Version:** 

**Node Groups:**

- `itl-0003-portal-prd-ec2-apps-02-appsmith` — ['m7a.2xlarge'] — desired:2 min:1 max:3
- `itl-0003-portal-prd-ec2-apps-02-metabase` — ['c5.large'] — desired:1 min:1 max:3
- `itl-0003-portal-prd-ec2-apps-02-portal` — ['m7a.large'] — desired:2 min:1 max:3

**Namespaces (workloads):** amazon-cloudwatch, amazon-guardduty, appsmith, default, external, external-secrets, internal, metabase, monitoring
**Deployments:** 67 — **Services:** 103

## Lambda Functions

| Name | Runtime | Memory | Timeout | VPC | SGs |
|---|---|---|---|---|---|
| aws-controltower-NotificationForwarder | python3.13 | 128MB | 60s | **No VPC** | — |
| fortisiem-log-extractor | python3.12 | 512MB | 600s | Yes | lambda-log-extractor-sg |
| itl-0003-portal-prd-lambda-fsx-log-export-02 | python3.12 | 128MB | 300s | Yes | itl-0003-portal-prd-lambda-fsx-log-export-02-sg |
| itl-0003-portal-prd-lambda-pg-audit-02 | python3.12 | 128MB | 60s | Yes | itl-0003-portal-prd-lambda-pg-audit-02-sg |

### Lambda VPC Details

**itl-0003-portal-prd-lambda-fsx-log-export-02**
- Runtime: python3.12 | Memory: 128MB | Timeout: 300s
- Subnets: itl-0003-portal-prd-restricted-2b, itl-0003-portal-prd-restricted-2a
- Execution role: `itl-0003-portal-prd-lambda-fsx-log-export-02-role`
- KMS: _none_
- Environment variable keys: PREFIX_RESOURCE_NAME, FSX_FILESYSTEM_ID, LOG_GROUP_NAME, BUCKET_NAME

**itl-0003-portal-prd-lambda-pg-audit-02**
- Runtime: python3.12 | Memory: 128MB | Timeout: 60s
- Subnets: itl-0003-portal-prd-restricted-2b, itl-0003-portal-prd-restricted-2a
- Execution role: `itl-0003-portal-prd-lambda-pg-audit-02-role`
- KMS: _none_
- Environment variable keys: ACCOUNT_ID, PREFIX, LOG_GROUP, BUCKET_NAME

**fortisiem-log-extractor**
- Runtime: python3.12 | Memory: 512MB | Timeout: 600s
- Subnets: itl-0003-portal-prd-private-2a
- Execution role: `LambdaLogExtractorRole`
- KMS: _none_
- Environment variable keys: CROSS_ACCOUNT_ROLE, EC2_INSTANCE_ID, DEST_PREFIX, AWS_REGION_NAME, DEST_BUCKET

## EC2 Instances

| Name | Type | State | Subnet | Private IP |
|---|---|---|---|---|
| ITL-Server-FortiSIEM | m5.2xlarge | running | itl-0003-portal-prd-private-2a | 10.10.3.13 |
| VM-1 | t3.medium | running | itl-0003-portal-prd-private-2a | 10.10.3.106 |
| VM-10 | t3.medium | stopped | itl-0003-portal-prd-private-2a | 10.10.3.159 |
| VM-2 | t3.medium | running | itl-0003-portal-prd-private-2a | 10.10.3.173 |
| VM-3 | t3.medium | stopped | itl-0003-portal-prd-private-2a | 10.10.3.48 |
| VM-4 | t3.medium | stopped | itl-0003-portal-prd-private-2a | 10.10.3.15 |
| VM-5 | t3.medium | stopped | itl-0003-portal-prd-private-2a | 10.10.3.139 |
| VM-6 | t3.medium | stopped | itl-0003-portal-prd-private-2a | 10.10.3.77 |
| VM-7 | t3.medium | stopped | itl-0003-portal-prd-private-2a | 10.10.3.189 |
| VM-8 | t3.medium | stopped | itl-0003-portal-prd-private-2a | 10.10.3.63 |
| VM-9 | t3.medium | stopped | itl-0003-portal-prd-private-2a | 10.10.3.153 |
| VM11 | t3.medium | stopped | itl-0003-portal-prd-private-2a | 10.10.3.169 |
| VM12 | t3.medium | stopped | itl-0003-portal-prd-private-2a | 10.10.3.131 |
| VM13 | t3.medium | running | itl-0003-portal-prd-private-2a | 10.10.3.154 |
| VMNN | t3.medium | running | itl-0003-portal-prd-private-2a | 10.10.3.195 |
| itl-0003-portal-prd-ec2-apps-02-appsmith | m7a.2xlarge | running | itl-0003-portal-prd-private-2a | 10.10.3.200 |
| itl-0003-portal-prd-ec2-apps-02-appsmith | m7a.2xlarge | running | itl-0003-portal-prd-private-2b | 10.10.4.163 |
| itl-0003-portal-prd-ec2-apps-02-metabase | c5.large | running | itl-0003-portal-prd-private-2a | 10.10.3.56 |
| itl-0003-portal-prd-ec2-apps-02-portal | m7a.large | running | itl-0003-portal-prd-private-2a | 10.10.3.109 |
| itl-0003-portal-prd-ec2-apps-02-portal | m7a.large | running | itl-0003-portal-prd-private-2b | 10.10.4.210 |
| itl-0003-portal-prd-ec2-clickhouse-02 | t3.xlarge | running | itl-0003-portal-prd-private-2b | 10.10.4.194 |
| itl-0003-portal-prd-ec2-datasync-agent-main-server-02 | r5.large | running | itl-0003-portal-prd-private-2a | 10.10.3.22 |
| itl-0003-portal-prd-ec2-denver-02 | r5.4xlarge | running | itl-0003-portal-prd-private-2b | 10.10.4.10 |
| itl-0003-portal-prd-ec2-vienna-02 | m5.2xlarge | running | itl-0003-portal-prd-private-2b | 10.10.4.11 |

## Load Balancers

### itl-0003-portal-prd-alb-02 (APPLICATION)
- **DNS:** `itl-0003-portal-prd-alb-02-1591531780.eu-south-2.elb.amazonaws.com`
- **Scheme:** internet-facing
- **AZs:** eu-south-2a, eu-south-2b

### itl-0003-portal-prd-lb-main-02 (APPLICATION)
- **DNS:** `itl-0003-portal-prd-lb-main-02-987560146.eu-south-2.elb.amazonaws.com`
- **Scheme:** internet-facing
- **AZs:** eu-south-2a, eu-south-2b

### itl-0003-portal-prd-nlb-sftp-02 (NETWORK)
- **DNS:** `itl-0003-portal-prd-nlb-sftp-02-4cb864a08f9e8ccf.elb.eu-south-2.amazonaws.com`
- **Scheme:** internet-facing
- **AZs:** eu-south-2b

### k8s-appsmith-appsmith-06d45f1beb (NETWORK)
- **DNS:** `k8s-appsmith-appsmith-06d45f1beb-f3d62eb37ed138ff.elb.eu-south-2.amazonaws.com`
- **Scheme:** internal
- **AZs:** eu-south-2b, eu-south-2a
