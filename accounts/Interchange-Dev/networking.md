# Interchange-Dev — Networking

_Last updated: 2026-07-12 17:54 UTC_

## VPC: vpc-029134477d2a41610

**ID:** `vpc-029134477d2a41610`  
**CIDR:** `172.31.0.0/16`  
**Default VPC:** Yes — avoid for production workloads

### Unknown Subnets

| Name | ID | CIDR | AZ | Free IPs |
|---|---|---|---|---|
| subnet-03ecb73f969b50b59 | `subnet-03ecb73f969b50b59` | 172.31.32.0/20 | 2a | 4091 |
| subnet-0a7a3b11f34a0fa39 | `subnet-0a7a3b11f34a0fa39` | 172.31.16.0/20 | 2b | 4091 |
| subnet-0821cfff7ba44d34f | `subnet-0821cfff7ba44d34f` | 172.31.0.0/20 | 2c | 4091 |

### Internet Gateway

- `igw-056f50cfcb7b4eaa1` — provides inbound/outbound internet for public subnets

## VPC: itl-0004-itx-dev-vpc-02

**ID:** `vpc-0101d2c447b67e9db`  
**CIDR:** `10.14.0.0/16`  
**Default VPC:** No (production)

### Public Subnets (route to Internet Gateway — for ALBs, NAT GWs)

| Name | ID | CIDR | AZ | Free IPs |
|---|---|---|---|---|
| itl-0004-itx-dev-public-2a | `subnet-0b7a74c150cca70e7` | 10.14.1.0/24 | 2a | 249 |
| itl-0004-itx-dev-public-2b | `subnet-05828a4204425c59b` | 10.14.2.0/24 | 2b | 249 |

### Private Subnets (route through NAT — recommended for Lambda, EC2, EKS nodes)

| Name | ID | CIDR | AZ | Free IPs |
|---|---|---|---|---|
| itl-0004-itx-dev-private-2a | `subnet-0b02ad525f046501b` | 10.14.3.0/24 | 2a | 231 |
| itl-0004-itx-dev-private-2b | `subnet-03cb8477fb39f639e` | 10.14.4.0/24 | 2b | 233 |

### Isolated Subnets (no internet route — recommended for RDS, restricted workloads)

| Name | ID | CIDR | AZ | Free IPs |
|---|---|---|---|---|
| itl-0004-itx-dev-restricted-2a | `subnet-09162acc62b24d7cb` | 10.14.5.0/24 | 2a | 249 |
| itl-0004-itx-dev-restricted-2b | `subnet-05dae71c2f90dc501` | 10.14.6.0/24 | 2b | 250 |

### Internet Gateway

- `igw-049a6140343c8f6d2` — provides inbound/outbound internet for public subnets

### NAT Gateway

- `nat-0c77344696fe6a32a` in **itl-0004-itx-dev-public-2a** (available)
  - Provides outbound internet for private subnets
  - Cost: ~$0.045/hour + $0.045/GB processed (eu-south-2)

### VPC Endpoints (avoid NAT costs for AWS services)

- **c-0002** () — ~$0.01/hour per AZ
- **s3** () — ~$0.01/hour per AZ
- **dynamodb** () — ~$0.01/hour per AZ
- **sns** () — ~$0.01/hour per AZ
- **sqs** () — ~$0.01/hour per AZ
- **secretsmanager** () — ~$0.01/hour per AZ
- **logs** () — ~$0.01/hour per AZ
- **guardduty-data** () — ~$0.01/hour per AZ
- **states** () — ~$0.01/hour per AZ
- **lambda** () — ~$0.01/hour per AZ

### Transit Gateway Attachments (cross-account connectivity)

- Attachment `tgw-attach-07f191cf3bd956294` → TGW `tgw-042a72cb246bebf1e`
  - Enables routing to other accounts (Interchange, Network, Analytics)
