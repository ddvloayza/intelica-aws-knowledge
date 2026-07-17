# Analytics-Dev — Account Overview

**Account ID:** 221082197632  
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
| Security Groups | 8 |

## Production VPC

**itl-0005-ana-dev-vpc-02** (`vpc-092dc05179287e08a`)
- CIDR: `10.16.0.0/16`
- Region: eu-south-2
- Contains all production workloads

## Key Services Running

- **EKS Cluster:** itl-0005-ana-dev-eks-af-02 — status: ACTIVE
- **RDS:** itl-0005-ana-dev-rds-dbaf-02 (postgres 16.13, db.t3.micro)
- **Lambda:** 1 functions (0 inside VPC)
- **Load Balancers:** 1 (1 ALB, 0 NLB)
- **S3:** 8 buckets
