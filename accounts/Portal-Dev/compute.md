# Portal-Dev — Compute

_Last updated: 2026-07-17 14:42 UTC_

## EKS Clusters

### itl-0003-portal-dev-eks-apps-03

**ARN:** `arn:aws:eks:eu-south-2:891376942769:cluster/itl-0003-portal-dev-eks-apps-03`  
**VPC:** `vpc-0fbd191d169cc9efb`  
**Status:** ACTIVE  
**Version:** 

**Node Groups:**

- `itl-0003-portal-dev-ec2-apps-03-airflow` — ['m5.xlarge'] — desired:1 min:1 max:5
- `itl-0003-portal-dev-ec2-apps-03-appsmith` — ['m5.2xlarge'] — desired:1 min:0 max:2
- `itl-0003-portal-dev-ec2-apps-03-metabase` — ['c5.large'] — desired:1 min:0 max:2
- `itl-0003-portal-dev-ec2-apps-03-portal` — ['m5.large'] — desired:2 min:0 max:2

**Namespaces (workloads):** airflow, amazon-cloudwatch, amazon-guardduty, appsmith, default, external, external-secrets, internal, metabase
**Deployments:** 80 — **Services:** 90

## Lambda Functions

| Name | Runtime | Memory | Timeout | VPC | SGs |
|---|---|---|---|---|---|
| SharedExternalDayXFunction | dotnet10 | 512MB | 15s | **No VPC** | — |
| SharedExternalMonthXFunction | dotnet10 | 512MB | 15s | **No VPC** | — |
| aws-controltower-NotificationForwarder | python3.13 | 128MB | 60s | **No VPC** | — |
| itl-0003-portal-dev-lambda-fee-external-custom-alert-03 | dotnet10 | 256MB | 120s | Yes | itl-0003-portal-dev-lambda-fee-external-custom-alert-03-sg |
| itl-0003-portal-dev-lambda-pg-audit-03 | python3.12 | 128MB | 60s | Yes | itl-0003-portal-dev-lambda-pg-audit-03-sg |
| itl-0003-portal-dev-lambda-sync-buk-absence-03 | dotnet10 | 256MB | 900s | Yes | itl-0003-portal-dev-lambda-sync-buk-absence-03-sg |
| itl-0003-portal-dev-lambda-sync-buk-organization-03 | dotnet10 | 256MB | 900s | Yes | itl-0003-portal-dev-lambda-sync-buk-organization-03-sg |
| itl-0003-portal-dev-lambda-sync-jira-03 | dotnet10 | 256MB | 900s | Yes | itl-0003-portal-dev-lambda-sync-jira-03-sg |
| quicksightEmbedAndListDashboard | python3.14 | 128MB | 60s | **No VPC** | — |

### Lambda VPC Details

**itl-0003-portal-dev-lambda-sync-jira-03**
- Runtime: dotnet10 | Memory: 256MB | Timeout: 900s
- Subnets: itl-0003-portal-dev-private-2b, itl-0003-portal-dev-private-2a
- Execution role: `itl-0003-portal-dev-lambda-sync-jira-03-role`
- KMS: _none_
- Environment variable keys: AWS__Secrets__ExternalCredentials, ENVIRONMENT, AWS__Secrets__ConnectionString

**itl-0003-portal-dev-lambda-sync-buk-absence-03**
- Runtime: dotnet10 | Memory: 256MB | Timeout: 900s
- Subnets: itl-0003-portal-dev-private-2b, itl-0003-portal-dev-private-2a
- Execution role: `itl-0003-portal-dev-lambda-sync-buk-absence-03-role`
- KMS: _none_
- Environment variable keys: AWS__Secrets__ExternalCredentials, ENVIRONMENT, AWS__Secrets__ConnectionString

**itl-0003-portal-dev-lambda-sync-buk-organization-03**
- Runtime: dotnet10 | Memory: 256MB | Timeout: 900s
- Subnets: itl-0003-portal-dev-private-2b, itl-0003-portal-dev-private-2a
- Execution role: `itl-0003-portal-dev-lambda-sync-buk-organization-03-role`
- KMS: _none_
- Environment variable keys: AWS__Secrets__ExternalCredentials, ENVIRONMENT, AWS__Secrets__ConnectionString

**itl-0003-portal-dev-lambda-pg-audit-03**
- Runtime: python3.12 | Memory: 128MB | Timeout: 60s
- Subnets: itl-0003-portal-dev-restricted-2b, itl-0003-portal-dev-restricted-2a
- Execution role: `itl-0003-portal-dev-lambda-pg-audit-03-role`
- KMS: _none_
- Environment variable keys: ACCOUNT_ID, PREFIX, LOG_GROUP, BUCKET_NAME

**itl-0003-portal-dev-lambda-fee-external-custom-alert-03**
- Runtime: dotnet10 | Memory: 256MB | Timeout: 120s
- Subnets: itl-0003-portal-dev-private-2b, itl-0003-portal-dev-private-2a
- Execution role: `itl-0003-portal-dev-lambda-fee-external-custom-alert-03-role`
- KMS: _none_
- Environment variable keys: ExternsAPIS__Paths__AuthenticationPath, ExternsAPIS__Paths__NotificationCallbackUrl, ENVIRONMENT, AWS__Secrets__InternalAuthentication, ExternsAPIS__Paths__NotificationPath, AWS__Secrets__ConnectionString

## EC2 Instances

| Name | Type | State | Subnet | Private IP |
|---|---|---|---|---|
| itl-0003-portal-dev-ec2-apps-03-airflow | m5.xlarge | running | itl-0003-portal-dev-private-2b | 10.12.4.25 |
| itl-0003-portal-dev-ec2-apps-03-appsmith | m5.2xlarge | running | itl-0003-portal-dev-private-2b | 10.12.4.14 |
| itl-0003-portal-dev-ec2-apps-03-metabase | c5.large | running | itl-0003-portal-dev-private-2a | 10.12.3.202 |
| itl-0003-portal-dev-ec2-apps-03-portal | m5.large | running | itl-0003-portal-dev-private-2a | 10.12.3.175 |
| itl-0003-portal-dev-ec2-apps-03-portal | m5.large | running | itl-0003-portal-dev-private-2b | 10.12.4.107 |
| itl-0003-portal-dev-ec2-clickhouse-03 | t3.large | running | itl-0003-portal-dev-private-2b | 10.12.4.188 |
| itl-0003-portal-dev-ec2-denver-03 | m5.2xlarge | running | itl-0003-portal-dev-private-2a | 10.12.3.127 |

## Load Balancers

### itl-0003-portal-dev-alb-02 (APPLICATION)
- **DNS:** `itl-0003-portal-dev-alb-02-1917574820.eu-south-2.elb.amazonaws.com`
- **Scheme:** internet-facing
- **AZs:** eu-south-2b, eu-south-2a

### itl-0003-portal-dev-alb-03 (APPLICATION)
- **DNS:** `itl-0003-portal-dev-alb-03-858794574.eu-south-2.elb.amazonaws.com`
- **Scheme:** internet-facing
- **AZs:** eu-south-2b, eu-south-2a

### k8s-appsmith-appsmith-65f856c687 (NETWORK)
- **DNS:** `k8s-appsmith-appsmith-65f856c687-3dc64f65cfc5c60d.elb.eu-south-2.amazonaws.com`
- **Scheme:** internal
- **AZs:** eu-south-2a, eu-south-2b
