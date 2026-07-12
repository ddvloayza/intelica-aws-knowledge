# Portal-Dev — Networking

_Last updated: 2026-07-12 17:54 UTC_

## VPC: itl-0003-portal-dev-vpc-02

**ID:** `vpc-0fbd191d169cc9efb`  
**CIDR:** `10.12.0.0/16`  
**Default VPC:** No (production)

### Public Subnets (route to Internet Gateway — for ALBs, NAT GWs)

| Name | ID | CIDR | AZ | Free IPs |
|---|---|---|---|---|
| itl-0003-portal-dev-public-2a | `subnet-0c09cafe518adff09` | 10.12.1.0/24 | 2a | 248 |
| itl-0003-portal-dev-public-2b | `subnet-065c0d2ee544988f8` | 10.12.2.0/24 | 2b | 249 |

### Private Subnets (route through NAT — recommended for Lambda, EC2, EKS nodes)

| Name | ID | CIDR | AZ | Free IPs |
|---|---|---|---|---|
| itl-0003-portal-dev-private-2a | `subnet-0c353ee340c3da15e` | 10.12.3.0/24 | 2a | 139 |
| itl-0003-portal-dev-private-2b | `subnet-05c87676a0cbfce54` | 10.12.4.0/24 | 2b | 108 |

### Isolated Subnets (no internet route — recommended for RDS, restricted workloads)

| Name | ID | CIDR | AZ | Free IPs |
|---|---|---|---|---|
| itl-0003-portal-dev-restricted-2a | `subnet-0a244b304a580c5e3` | 10.12.5.0/24 | 2a | 248 |
| itl-0003-portal-dev-restricted-2b | `subnet-085c2712bbea48a30` | 10.12.6.0/24 | 2b | 246 |

### Internet Gateway

- `igw-08de3c6edee36b2db` — provides inbound/outbound internet for public subnets

### NAT Gateway

- `nat-014b4d7d86c3c4692` in **itl-0003-portal-dev-public-2a** (available)
  - Provides outbound internet for private subnets
  - Cost: ~$0.045/hour + $0.045/GB processed (eu-south-2)

### VPC Endpoints (avoid NAT costs for AWS services)

- **s3** () — ~$0.01/hour per AZ
- **datasync** () — ~$0.01/hour per AZ
- **logs** () — ~$0.01/hour per AZ
- **guardduty-data** () — ~$0.01/hour per AZ

### Transit Gateway Attachments (cross-account connectivity)

- Attachment `tgw-attach-08bec69283e6c3018` → TGW `tgw-042a72cb246bebf1e`
  - Enables routing to other accounts (Interchange, Network, Analytics)

## VPC: vpc-086471f116a4c4c20

**ID:** `vpc-086471f116a4c4c20`  
**CIDR:** `172.31.0.0/16`  
**Default VPC:** Yes — avoid for production workloads

### Unknown Subnets

| Name | ID | CIDR | AZ | Free IPs |
|---|---|---|---|---|
| subnet-0455a6c137238d0ec | `subnet-0455a6c137238d0ec` | 172.31.32.0/20 | 2a | 4091 |
| subnet-0f7dbdc1d324142a6 | `subnet-0f7dbdc1d324142a6` | 172.31.16.0/20 | 2b | 4091 |
| subnet-00584f42d1e6f05a7 | `subnet-00584f42d1e6f05a7` | 172.31.0.0/20 | 2c | 4091 |

### Internet Gateway

- `igw-0635c19da966fcd94` — provides inbound/outbound internet for public subnets
