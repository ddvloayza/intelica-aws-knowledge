# Portal-Dev — Account Overview

**Account ID:** 891376942769  
**Region:** eu-south-2  
**Last updated:** 2026-07-12 17:54 UTC

## Resource Summary

| Resource | Count |
|---|---|
| VPCs | 2 |
| Subnets | 9 |
| EC2 Instances (active) | 7 |
| EKS Clusters | 1 |
| EKS Node Groups | 4 |
| Lambda Functions | 9 |
| RDS Instances | 1 |
| Load Balancers | 3 |
| S3 Buckets | 15 |
| KMS Keys (customer) | 3 |
| Secrets | 18 |
| Security Groups | 26 |

## Production VPC

**itl-0003-portal-dev-vpc-02** (`vpc-0fbd191d169cc9efb`)
- CIDR: `10.12.0.0/16`
- Region: eu-south-2
- Contains all production workloads

## Key Services Running

- **EKS Cluster:** itl-0003-portal-dev-eks-apps-03 — status: ACTIVE
- **RDS:** itl-0003-portal-dev-rds-apps-03-instance-1 (aurora-postgresql 16.11, db.serverless)
- **Lambda:** 9 functions (5 inside VPC)
- **Load Balancers:** 3 (2 ALB, 1 NLB)
- **S3:** 15 buckets
