# Portal-Prod — Networking

_Last updated: 2026-05-23 18:52 UTC_

## VPC: vpc-0a2328aacb75cfc60

**ID:** `vpc-0a2328aacb75cfc60`  
**CIDR:** `172.31.0.0/16`  
**Default VPC:** Yes — avoid for production workloads

### Unknown Subnets

| Name | ID | CIDR | AZ | Free IPs |
|---|---|---|---|---|
| subnet-0d4d210f456e5c247 | `subnet-0d4d210f456e5c247` | 172.31.32.0/20 | 2a | 4091 |
| subnet-0c69299494134215d | `subnet-0c69299494134215d` | 172.31.16.0/20 | 2b | 4091 |
| subnet-03a0a390d332a497b | `subnet-03a0a390d332a497b` | 172.31.0.0/20 | 2c | 4091 |

### Internet Gateway

- `igw-05d074c79cc6687d0` — provides inbound/outbound internet for public subnets

## VPC: itl-0003-portal-prd-vpc-02

**ID:** `vpc-0626d66632373c892`  
**CIDR:** `10.10.0.0/16`  
**Default VPC:** No (production)

### Public Subnets (route to Internet Gateway — for ALBs, NAT GWs)

| Name | ID | CIDR | AZ | Free IPs |
|---|---|---|---|---|
| itl-0003-portal-prd-public-2a | `subnet-03d18c5b1df70087a` | 10.10.1.0/24 | 2a | 248 |
| itl-0003-portal-prd-public-2b | `subnet-0c54894493d118e63` | 10.10.2.0/24 | 2b | 248 |
| itl-0003-portal-prd-public-2c | `subnet-0268210322395563d` | 10.10.7.0/24 | 2c | 251 |

### Private Subnets (route through NAT — recommended for Lambda, EC2, EKS nodes)

| Name | ID | CIDR | AZ | Free IPs |
|---|---|---|---|---|
| itl-0003-portal-prd-private-2a | `subnet-042f934568c455b4c` | 10.10.3.0/24 | 2a | 130 |
| itl-0003-portal-prd-private-2b | `subnet-0c396a6c940028849` | 10.10.4.0/24 | 2b | 172 |
| itl-0003-portal-prd-private-2c | `subnet-00fec6232d3dc188d` | 10.10.8.0/24 | 2c | 249 |

### Isolated Subnets (no internet route — recommended for RDS, restricted workloads)

| Name | ID | CIDR | AZ | Free IPs |
|---|---|---|---|---|
| itl-0003-portal-prd-restricted-2a | `subnet-0588eba1879cd168c` | 10.10.5.0/24 | 2a | 249 |
| itl-0003-portal-prd-restricted-2b | `subnet-0362f83b46f047126` | 10.10.6.0/24 | 2b | 248 |
| itl-0003-portal-prd-restricted-2c | `subnet-043e3fb731d433446` | 10.10.9.0/24 | 2c | 251 |

### Internet Gateway

- `igw-0b25b41f515013c5b` — provides inbound/outbound internet for public subnets

### NAT Gateway

- `nat-07f69a860188add0f` in **itl-0003-portal-prd-public-2a** (available)
  - Provides outbound internet for private subnets
  - Cost: ~$0.045/hour + $0.045/GB processed (eu-south-2)

### VPC Endpoints (avoid NAT costs for AWS services)

- **datasync** () — ~$0.01/hour per AZ
- **guardduty-data** () — ~$0.01/hour per AZ
- **logs** () — ~$0.01/hour per AZ
- **s3** () — ~$0.01/hour per AZ

### Transit Gateway Attachments (cross-account connectivity)

- Attachment `tgw-attach-051b6928615862d2a` → TGW `tgw-042a72cb246bebf1e`
  - Enables routing to other accounts (Interchange, Network, Analytics)
