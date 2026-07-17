# Portal-Prod — Account Overview

**Account ID:** 610944808410  
**Region:** eu-south-2  
**Last updated:** 2026-07-17 14:42 UTC

## Resource Summary

| Resource | Count |
|---|---|
| VPCs | 2 |
| Subnets | 12 |
| EC2 Instances (active) | 25 |
| EKS Clusters | 1 |
| EKS Node Groups | 4 |
| Lambda Functions | 8 |
| RDS Instances | 1 |
| Load Balancers | 4 |
| S3 Buckets | 25 |
| KMS Keys (customer) | 3 |
| Secrets | 16 |
| Security Groups | 55 |

## Production VPC

**itl-0003-portal-prd-vpc-02** (`vpc-0626d66632373c892`)
- CIDR: `10.10.0.0/16`
- Region: eu-south-2
- Contains all production workloads

## Key Services Running

- **EKS Cluster:** itl-0003-portal-prd-eks-apps-02 — status: ACTIVE
- **RDS:** itl-0003-portal-prd-rds-apps-02-instance-1 (aurora-postgresql 16.11, db.serverless)
- **Lambda:** 8 functions (7 inside VPC)
- **Load Balancers:** 4 (2 ALB, 2 NLB)
- **S3:** 25 buckets
