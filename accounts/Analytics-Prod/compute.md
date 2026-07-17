# Analytics-Prod — Compute

_Last updated: 2026-07-17 14:42 UTC_

## EKS Clusters

### itl-0005-ana-prd-eks-af-02

**ARN:** `arn:aws:eks:eu-south-2:831926623233:cluster/itl-0005-ana-prd-eks-af-02`  
**VPC:** `vpc-0008aceba2432ab91`  
**Status:** ACTIVE  
**Version:** 

**Node Groups:**

- `itl-0005-ana-prd-ng-dags-02-20251017032808088700000026` — ['c7i.large'] — desired:1 min:1 max:5

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
| itl-0005-ana-prd-ng-dags-02 | c7i.large | running | itl-0005-ana-prd-vpc-02-private-eu-south-2a | 10.15.0.154 |

## Load Balancers

### itl-0005-ana-prd-alb-apps-02 (APPLICATION)
- **DNS:** `internal-itl-0005-ana-prd-alb-apps-02-2014865631.eu-south-2.elb.amazonaws.com`
- **Scheme:** internal
- **AZs:** eu-south-2c, eu-south-2b, eu-south-2a
