# Interchange-Dev — Account Overview

**Account ID:** 861276092327  
**Region:** eu-south-2  
**Last updated:** 2026-07-17 14:42 UTC

## Resource Summary

| Resource | Count |
|---|---|
| VPCs | 2 |
| Subnets | 9 |
| EC2 Instances (active) | 1 |
| EKS Clusters | 0 |
| EKS Node Groups | 0 |
| Lambda Functions | 26 |
| RDS Instances | 1 |
| Load Balancers | 1 |
| S3 Buckets | 20 |
| KMS Keys (customer) | 1 |
| Secrets | 4 |
| Security Groups | 19 |

## Production VPC

**itl-0004-itx-dev-vpc-02** (`vpc-0101d2c447b67e9db`)
- CIDR: `10.14.0.0/16`
- Region: eu-south-2
- Contains all production workloads

## Key Services Running

- **RDS:** itl-0004-itx-dev-rds-app-02-1 (aurora-postgresql 16.11, db.r5.large)
- **Lambda:** 26 functions (16 inside VPC)
- **Load Balancers:** 1 (0 ALB, 1 NLB)
- **S3:** 20 buckets
