# Analytics-Dev — Compute

_Last updated: 2026-07-17 14:42 UTC_

## EKS Clusters

### itl-0005-ana-dev-eks-af-02

**ARN:** `arn:aws:eks:eu-south-2:221082197632:cluster/itl-0005-ana-dev-eks-af-02`  
**VPC:** `vpc-092dc05179287e08a`  
**Status:** ACTIVE  
**Version:** 

**Node Groups:**

- `itl-0005-ana-dev-ng-dags-02-20251012040132923800000026` — ['c7i.large'] — desired:1 min:1 max:5

**Namespaces (workloads):** airflow, amazon-cloudwatch, amazon-guardduty, argocd, default
**Deployments:** 19 — **Services:** 25

## Lambda Functions

| Name | Runtime | Memory | Timeout | VPC | SGs |
|---|---|---|---|---|---|
| aws-controltower-NotificationForwarder | python3.13 | 128MB | 60s | **No VPC** | — |

### Lambda VPC Details

## EC2 Instances

| Name | Type | State | Subnet | Private IP |
|---|---|---|---|---|
| itl-0005-ana-dev-ng-dags-02 | c7i.large | running | itl-0005-ana-dev-vpc-02-private-eu-south-2c | 10.16.2.180 |

## Load Balancers

### itl-0005-ana-dev-alb-apps-02 (APPLICATION)
- **DNS:** `internal-itl-0005-ana-dev-alb-apps-02-302345601.eu-south-2.elb.amazonaws.com`
- **Scheme:** internal
- **AZs:** eu-south-2b, eu-south-2c, eu-south-2a
