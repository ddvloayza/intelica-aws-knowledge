# Interchange-Prod — Account Overview

**Account ID:** 818835242461  
**Region:** eu-south-2  
**Last updated:** 2026-07-17 14:42 UTC

## Resource Summary

| Resource | Count |
|---|---|
| VPCs | 3 |
| Subnets | 15 |
| EC2 Instances (active) | 2 |
| EKS Clusters | 0 |
| EKS Node Groups | 0 |
| Lambda Functions | 6 |
| RDS Instances | 2 |
| Load Balancers | 1 |
| S3 Buckets | 17 |
| KMS Keys (customer) | 5 |
| Secrets | 17 |
| Security Groups | 23 |

## Production VPC

**itl-0004-itx-prod-vpc-02** (`vpc-0c6863a32b8db36e0`)
- CIDR: `10.13.0.0/16`
- Region: eu-south-2
- Contains all production workloads

## Key Services Running

- **RDS:** itl-0004-itx-prd-rds-analitycs-02 (postgres 17.9, db.r5.large)
- **RDS:** itl-0004-itx-prd-rds-app-02-1 (aurora-postgresql 16.11, db.r5.2xlarge)
- **Lambda:** 6 functions (5 inside VPC)
- **Load Balancers:** 1 (0 ALB, 1 NLB)
- **S3:** 17 buckets
