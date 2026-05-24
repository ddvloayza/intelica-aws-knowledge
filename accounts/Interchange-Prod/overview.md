# Interchange-Prod — Account Overview

**Account ID:** 818835242461  
**Region:** eu-south-2  
**Last updated:** 2026-05-24 19:32 UTC

## Resource Summary

| Resource | Count |
|---|---|
| VPCs | 3 |
| Subnets | 15 |
| EC2 Instances (active) | 2 |
| EKS Clusters | 0 |
| EKS Node Groups | 0 |
| Lambda Functions | 5 |
| RDS Instances | 2 |
| Load Balancers | 1 |
| S3 Buckets | 16 |
| KMS Keys (customer) | 2 |
| Secrets | 17 |
| Security Groups | 22 |

## Production VPC

**itl-0004-itx-prod-vpc-02** (`vpc-0c6863a32b8db36e0`)
- CIDR: `10.13.0.0/16`
- Region: eu-south-2
- Contains all production workloads

## Key Services Running

- **RDS:** itl-0004-itx-prd-rds-analitycs-02 (postgres 17.8, db.r5.large)
- **RDS:** itl-0004-itx-prd-rds-app-02-1 (aurora-postgresql 16.11, db.r5.2xlarge)
- **Lambda:** 5 functions (4 inside VPC)
- **Load Balancers:** 1 (0 ALB, 1 NLB)
- **S3:** 16 buckets
