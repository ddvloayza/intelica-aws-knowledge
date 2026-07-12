# Intelica-Network — Networking

_Last updated: 2026-07-12 01:20 UTC_

## VPC: itl-0002-shared-network-all-vpc-02

**ID:** `vpc-000f7f02c4d4819a3`  
**CIDR:** `10.18.0.0/16`  
**Default VPC:** No (production)

### Public Subnets (route to Internet Gateway — for ALBs, NAT GWs)

| Name | ID | CIDR | AZ | Free IPs |
|---|---|---|---|---|
| itl-0002-shared-network-all-public-2a | `subnet-0a157bf35bbf62195` | 10.18.1.0/24 | 2a | 248 |
| itl-0002-shared-network-all-public-2b | `subnet-0f412a52465a75334` | 10.18.2.0/24 | 2b | 249 |

### Private Subnets (route through NAT — recommended for Lambda, EC2, EKS nodes)

| Name | ID | CIDR | AZ | Free IPs |
|---|---|---|---|---|
| itl-0002-shared-network-all-private-2a | `subnet-06e26c7cc455004c5` | 10.18.3.0/24 | 2a | 247 |
| itl-0002-shared-network-all-private-2b | `subnet-0624a59dbcfc36798` | 10.18.4.0/24 | 2b | 215 |

### Isolated Subnets (no internet route — recommended for RDS, restricted workloads)

| Name | ID | CIDR | AZ | Free IPs |
|---|---|---|---|---|
| itl-0002-shared-network-all-restricted-2a | `subnet-0c9fc58aab4d826c2` | 10.18.5.0/24 | 2a | 251 |
| itl-0002-shared-network-all-restricted-2b | `subnet-011ec58c1a72d1d92` | 10.18.6.0/24 | 2b | 251 |

### Internet Gateway

- `igw-054c0fdd7e6602217` — provides inbound/outbound internet for public subnets

### NAT Gateway

- `nat-019b78f30236407b3` in **itl-0002-shared-network-all-public-2a** (available)
  - Provides outbound internet for private subnets
  - Cost: ~$0.045/hour + $0.045/GB processed (eu-south-2)

### VPC Endpoints (avoid NAT costs for AWS services)

- **guardduty-data** () — ~$0.01/hour per AZ

### Transit Gateway Attachments (cross-account connectivity)

- Attachment `tgw-attach-0374276375df2f3c8` → TGW `tgw-042a72cb246bebf1e`
  - Enables routing to other accounts (Interchange, Network, Analytics)

## VPC: vpc-04ef4e1c7cb3cc620

**ID:** `vpc-04ef4e1c7cb3cc620`  
**CIDR:** `172.31.0.0/16`  
**Default VPC:** Yes — avoid for production workloads

### Unknown Subnets

| Name | ID | CIDR | AZ | Free IPs |
|---|---|---|---|---|
| subnet-0cc5df51a602ec5b4 | `subnet-0cc5df51a602ec5b4` | 172.31.32.0/20 | 2a | 4091 |
| subnet-060bccb2e00f66b25 | `subnet-060bccb2e00f66b25` | 172.31.16.0/20 | 2b | 4091 |
| subnet-017059e9a4fe66bd0 | `subnet-017059e9a4fe66bd0` | 172.31.0.0/20 | 2c | 4091 |

### Internet Gateway

- `igw-00982dcc71039f386` — provides inbound/outbound internet for public subnets
