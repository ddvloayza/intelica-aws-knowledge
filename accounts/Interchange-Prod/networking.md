# Interchange-Prod — Networking

_Last updated: 2026-05-24 19:32 UTC_

## VPC: vpc-0e628fe72b4175720

**ID:** `vpc-0e628fe72b4175720`  
**CIDR:** `172.31.0.0/16`  
**Default VPC:** Yes — avoid for production workloads

### Unknown Subnets

| Name | ID | CIDR | AZ | Free IPs |
|---|---|---|---|---|
| subnet-0a841673111368598 | `subnet-0a841673111368598` | 172.31.32.0/20 | 2a | 4091 |
| subnet-044a2704c0387e2b5 | `subnet-044a2704c0387e2b5` | 172.31.16.0/20 | 2b | 4091 |
| subnet-057ebce9596b3bf36 | `subnet-057ebce9596b3bf36` | 172.31.0.0/20 | 2c | 4091 |

### Internet Gateway

- `igw-0f1155ffd0b58b243` — provides inbound/outbound internet for public subnets

## VPC: itl-0004-itx-prod-vpc-02

**ID:** `vpc-0c6863a32b8db36e0`  
**CIDR:** `10.13.0.0/16`  
**Default VPC:** No (production)

### Public Subnets (route to Internet Gateway — for ALBs, NAT GWs)

| Name | ID | CIDR | AZ | Free IPs |
|---|---|---|---|---|
| itl-0004-itx-prod-public-2a | `subnet-01e1b509ce04c5bb2` | 10.13.1.0/24 | 2a | 249 |
| itl-0004-itx-prod-public-2b | `subnet-0951555575751a819` | 10.13.2.0/24 | 2b | 248 |

### Private Subnets (route through NAT — recommended for Lambda, EC2, EKS nodes)

| Name | ID | CIDR | AZ | Free IPs |
|---|---|---|---|---|
| itl-0004-itx-prod-restricted-2a | `subnet-0ed8a143f2b994c42` | 10.13.5.0/24 | 2a | 248 |
| itl-0004-itx-prod-private-2a | `subnet-0922b864eefaddb05` | 10.13.3.0/24 | 2a | 239 |
| itl-0004-itx-prod-restricted-2b | `subnet-013b386fa64d33781` | 10.13.6.0/24 | 2b | 249 |
| itl-0004-itx-prod-private-2b | `subnet-03c90b860a79acd5e` | 10.13.4.0/24 | 2b | 242 |

### Internet Gateway

- `igw-01ee7a6bfe96bfbb1` — provides inbound/outbound internet for public subnets

### NAT Gateway

- `nat-00f93b8b61457d10d` in **itl-0004-itx-prod-public-2a** (available)
  - Provides outbound internet for private subnets
  - Cost: ~$0.045/hour + $0.045/GB processed (eu-south-2)

### VPC Endpoints (avoid NAT costs for AWS services)

- **s3** () — ~$0.01/hour per AZ
- **c-0002** () — ~$0.01/hour per AZ
- **dynamodb** () — ~$0.01/hour per AZ
- **sqs** () — ~$0.01/hour per AZ
- **logs** () — ~$0.01/hour per AZ
- **sns** () — ~$0.01/hour per AZ
- **secretsmanager** () — ~$0.01/hour per AZ
- **guardduty-data** () — ~$0.01/hour per AZ

### Transit Gateway Attachments (cross-account connectivity)

- Attachment `tgw-attach-099db8323944dbd48` → TGW `tgw-042a72cb246bebf1e`
  - Enables routing to other accounts (Interchange, Network, Analytics)

## VPC: itl-0004-itx-prod-vpc-01

**ID:** `vpc-09cd0eff0b0a7a363`  
**CIDR:** `172.9.0.0/16`  
**Default VPC:** No (production)

### Public Subnets (route to Internet Gateway — for ALBs, NAT GWs)

| Name | ID | CIDR | AZ | Free IPs |
|---|---|---|---|---|
| itl-0004-itx-prod-public-2a | `subnet-014840bef902a667c` | 172.9.1.0/24 | 2a | 250 |
| itl-0004-itx-prod-public-2b | `subnet-0d83e06465f5db5e0` | 172.9.2.0/24 | 2b | 251 |

### Private Subnets (route through NAT — recommended for Lambda, EC2, EKS nodes)

| Name | ID | CIDR | AZ | Free IPs |
|---|---|---|---|---|
| itl-0004-itx-prod-private-2a | `subnet-01799deb0a8d8f211` | 172.9.3.0/24 | 2a | 251 |
| itl-0004-itx-prod-private-2b | `subnet-0a6a896434731d1de` | 172.9.4.0/24 | 2b | 251 |

### Isolated Subnets (no internet route — recommended for RDS, restricted workloads)

| Name | ID | CIDR | AZ | Free IPs |
|---|---|---|---|---|
| itl-0004-itx-prod-restricted-2a | `subnet-079acbb9ff15d4baf` | 172.9.5.0/24 | 2a | 251 |
| itl-0004-itx-prod-restricted-2b | `subnet-0c4fd47c211461df6` | 172.9.6.0/24 | 2b | 251 |

### Internet Gateway

- `igw-0840f656c99b08f58` — provides inbound/outbound internet for public subnets

### NAT Gateway

- `nat-087cf87c9fdf098b8` in **itl-0004-itx-prod-public-2a** (available)
  - Provides outbound internet for private subnets
  - Cost: ~$0.045/hour + $0.045/GB processed (eu-south-2)
