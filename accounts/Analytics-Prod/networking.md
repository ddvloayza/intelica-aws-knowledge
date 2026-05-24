# Analytics-Prod — Networking

_Last updated: 2026-05-24 19:32 UTC_

## VPC: itl-0005-ana-prd-vpc-02

**ID:** `vpc-0008aceba2432ab91`  
**CIDR:** `10.15.0.0/16`  
**Default VPC:** No (production)

### Public Subnets (route to Internet Gateway — for ALBs, NAT GWs)

| Name | ID | CIDR | AZ | Free IPs |
|---|---|---|---|---|
| itl-0005-ana-prd-vpc-02-public-eu-south-2a | `subnet-077cb8f42729b95bb` | 10.15.10.0/24 | 2a | 248 |
| itl-0005-ana-prd-vpc-02-public-eu-south-2b | `subnet-0d2f2112cc95f756e` | 10.15.11.0/24 | 2b | 251 |
| itl-0005-ana-prd-vpc-02-public-eu-south-2c | `subnet-0a7d571bb2360baed` | 10.15.12.0/24 | 2c | 251 |

### Private Subnets (route through NAT — recommended for Lambda, EC2, EKS nodes)

| Name | ID | CIDR | AZ | Free IPs |
|---|---|---|---|---|
| itl-0005-ana-prd-vpc-02-private-eu-south-2a | `subnet-0d85a80ddb479d2fb` | 10.15.0.0/24 | 2a | 244 |
| itl-0005-ana-prd-vpc-02-private-eu-south-2b | `subnet-08d029e0c1f7e782e` | 10.15.1.0/24 | 2b | 235 |
| itl-0005-ana-prd-vpc-02-private-eu-south-2c | `subnet-04c4e78c5fef9f756` | 10.15.2.0/24 | 2c | 222 |

### Internet Gateway

- `igw-0eff82aaffadad80f` — provides inbound/outbound internet for public subnets

### NAT Gateway

- `nat-0beb17b37f7133346` in **itl-0005-ana-prd-vpc-02-public-eu-south-2a** (available)
  - Provides outbound internet for private subnets
  - Cost: ~$0.045/hour + $0.045/GB processed (eu-south-2)

### VPC Endpoints (avoid NAT costs for AWS services)

- **s3** () — ~$0.01/hour per AZ
- **api** () — ~$0.01/hour per AZ
- **dkr** () — ~$0.01/hour per AZ
- **guardduty-data** () — ~$0.01/hour per AZ

### Transit Gateway Attachments (cross-account connectivity)

- Attachment `tgw-attach-0075738dd2bed67c3` → TGW `tgw-042a72cb246bebf1e`
  - Enables routing to other accounts (Interchange, Network, Analytics)

## VPC: vpc-0ede3f28262280a93

**ID:** `vpc-0ede3f28262280a93`  
**CIDR:** `172.31.0.0/16`  
**Default VPC:** Yes — avoid for production workloads

### Unknown Subnets

| Name | ID | CIDR | AZ | Free IPs |
|---|---|---|---|---|
| subnet-0234f424bc7b4795e | `subnet-0234f424bc7b4795e` | 172.31.32.0/20 | 2a | 4091 |
| subnet-05ced23f76cfe459c | `subnet-05ced23f76cfe459c` | 172.31.16.0/20 | 2b | 4091 |
| subnet-098f112a26aa4f4a2 | `subnet-098f112a26aa4f4a2` | 172.31.0.0/20 | 2c | 4091 |

### Internet Gateway

- `igw-09126b47c08cf232c` — provides inbound/outbound internet for public subnets
