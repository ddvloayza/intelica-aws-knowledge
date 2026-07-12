# Intelica-Network — Compute

_Last updated: 2026-07-12 17:54 UTC_

## EKS Clusters

### itl-0002-shared-network-all-eks-pritunl-02

**ARN:** `arn:aws:eks:eu-south-2:954976322048:cluster/itl-0002-shared-network-all-eks-pritunl-02`  
**VPC:** `vpc-000f7f02c4d4819a3`  
**Status:** ACTIVE  
**Version:** 

**Node Groups:**

- `itl-0002-shared-network-all-ec2-pritunl-02` — ['t3.medium'] — desired:1 min:0 max:1

## EC2 Instances

| Name | Type | State | Subnet | Private IP |
|---|---|---|---|---|
| itl-0002-shared-network-all-ec2-directory-all-ec2-02 | t3.large | running | itl-0002-shared-network-all-private-2a | 10.18.3.147 |
| itl-0002-shared-network-all-ec2-pritunl-02 | t3.medium | running | itl-0002-shared-network-all-private-2b | 10.18.4.194 |

## Load Balancers

### itl-0002-network-all-nlb-pritunl (NETWORK)
- **DNS:** `itl-0002-network-all-nlb-pritunl-4583f4ee7c8e9d99.elb.eu-south-2.amazonaws.com`
- **Scheme:** internet-facing
- **AZs:** eu-south-2a, eu-south-2b

### k8s-pritunl-pritunli-1014a3c469 (APPLICATION)
- **DNS:** `k8s-pritunl-pritunli-1014a3c469-1184641132.eu-south-2.elb.amazonaws.com`
- **Scheme:** internet-facing
- **AZs:** eu-south-2a, eu-south-2b
