# Analytics-Dev — Networking

_Last updated: 2026-07-17 14:42 UTC_

## VPC: vpc-0f4a2881864e2f145

**ID:** `vpc-0f4a2881864e2f145`  
**CIDR:** `172.31.0.0/16`  
**Default VPC:** Yes — avoid for production workloads

### Unknown Subnets

| Name | ID | CIDR | AZ | Free IPs |
|---|---|---|---|---|
| subnet-0f33d1f341d8a345a | `subnet-0f33d1f341d8a345a` | 172.31.32.0/20 | 2a | 4091 |
| subnet-036f5d50f44311202 | `subnet-036f5d50f44311202` | 172.31.16.0/20 | 2b | 4091 |
| subnet-0984e272969bbb21b | `subnet-0984e272969bbb21b` | 172.31.0.0/20 | 2c | 4091 |

### Internet Gateway

- `igw-081bcc0327e5eb2ac` — provides inbound/outbound internet for public subnets

## VPC: itl-0005-ana-dev-vpc-02

**ID:** `vpc-092dc05179287e08a`  
**CIDR:** `10.16.0.0/16`  
**Default VPC:** No (production)

### Public Subnets (route to Internet Gateway — for ALBs, NAT GWs)

| Name | ID | CIDR | AZ | Free IPs |
|---|---|---|---|---|
| itl-0005-ana-dev-vpc-02-public-eu-south-2a | `subnet-0e5476d41014d49de` | 10.16.10.0/24 | 2a | 248 |
| itl-0005-ana-dev-vpc-02-public-eu-south-2b | `subnet-014f964b09f74d08b` | 10.16.11.0/24 | 2b | 249 |
| itl-0005-ana-dev-vpc-02-public-eu-south-2c | `subnet-0feceacea96baa669` | 10.16.12.0/24 | 2c | 251 |

### Private Subnets (route through NAT — recommended for Lambda, EC2, EKS nodes)

| Name | ID | CIDR | AZ | Free IPs |
|---|---|---|---|---|
| itl-0005-ana-dev-vpc-02-private-eu-south-2a | `subnet-0b2520e045cf37cb0` | 10.16.0.0/24 | 2a | 237 |
| itl-0005-ana-dev-vpc-02-private-eu-south-2b | `subnet-013034a3fd02e9b17` | 10.16.1.0/24 | 2b | 244 |
| itl-0005-ana-dev-vpc-02-private-eu-south-2c | `subnet-03b22d8fce7ca6076` | 10.16.2.0/24 | 2c | 222 |

### Internet Gateway

- `igw-0293d75be96041edb` — provides inbound/outbound internet for public subnets

### NAT Gateway

- `nat-03cf9262ac991eff2` in **itl-0005-ana-dev-vpc-02-public-eu-south-2a** (available)
  - Provides outbound internet for private subnets
  - Cost: ~$0.045/hour + $0.045/GB processed (eu-south-2)

### VPC Endpoints (avoid NAT costs for AWS services)

- **s3** () — ~$0.01/hour per AZ
- **api** () — ~$0.01/hour per AZ
- **dkr** () — ~$0.01/hour per AZ
- **guardduty-data** () — ~$0.01/hour per AZ

### Transit Gateway Attachments (cross-account connectivity)

- Attachment `tgw-attach-0b9e3e995cfcca714` → TGW `tgw-042a72cb246bebf1e`
  - Enables routing to other accounts (Interchange, Network, Analytics)
