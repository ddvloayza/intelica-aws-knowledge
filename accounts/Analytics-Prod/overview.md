# Analytics-Prod — Account Overview

**Account ID:** 831926623233  
**Region:** eu-south-2  
**Last updated:** 2026-07-17 14:42 UTC

## Resource Summary

| Resource | Count |
|---|---|
| VPCs | 2 |
| Subnets | 9 |
| EC2 Instances (active) | 1 |
| EKS Clusters | 1 |
| EKS Node Groups | 1 |
| Lambda Functions | 1 |
| RDS Instances | 1 |
| Load Balancers | 1 |
| S3 Buckets | 8 |
| KMS Keys (customer) | 2 |
| Secrets | 0 |
| Security Groups | 9 |

## Production VPC

**itl-0005-ana-prd-vpc-02** (`vpc-0008aceba2432ab91`)
- CIDR: `10.15.0.0/16`
- Region: eu-south-2
- Contains all production workloads

## Key Services Running

- **EKS Cluster:** itl-0005-ana-prd-eks-af-02 — status: ACTIVE
- **RDS:** itl-0005-ana-prd-rds-dbaf-02 (postgres 16.13, db.t3.micro)
- **Lambda:** 1 functions (0 inside VPC)
- **Load Balancers:** 1 (1 ALB, 0 NLB)
- **S3:** 8 buckets
