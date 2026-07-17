# Portal-Dev — Security

_Last updated: 2026-07-17 14:42 UTC_

## KMS Keys (Customer Managed)

### alias/alias/itl-0003-portal-dev-kms-general-03
- **Key ID:** `01234c6d-f41e-45d2-9e78-dae042d00859`  
- **Usage:** ENCRYPT_DECRYPT  
- **Rotation:** Enabled  
- **Multi-region:** No  
- **Description:** KMS customer managed key

### alias/itl-0003-itx-prd-kms-london-pan-hmac-03
- **Key ID:** `3f05357c-ffea-4fea-af56-a639106c56a4`  
- **Usage:** ENCRYPT_DECRYPT  
- **Rotation:** Disabled  
- **Multi-region:** No  
- **Description:** PCI DSS 4.0.1 - CMK HMAC PAN - itl-0003-portal-dev - Rotacion MANUAL

### alias/itl-0003-itx-prd-kms-london-pan-encrypt-03
- **Key ID:** `de0c1d02-85ac-46a6-93f5-ab5f1f033b7b`  
- **Usage:** ENCRYPT_DECRYPT  
- **Rotation:** Disabled  
- **Multi-region:** No  
- **Description:** PCI DSS 4.0.1 - CMK encriptacion PAN - Rotacion MANUAL

## IAM Roles by Trusted Service

### lambda.amazonaws.com

- **aws-controltower-ForwardSnsNotificationRole** — policies: AWSLambdaBasicExecutionRole
- **django-app-role-ximfljqh** — policies: AWSLambdaBasicExecutionRole-2d785db2-d053-40d6-a23b-a30dda6831c4
- **f_cole-role-eysgoxjk** — policies: AWSLambdaBasicExecutionRole-3e1ad495-c34e-411b-949f-bebdb41e45ae
- **itl-0003-portal-dev-lambda-pg-audit-03-role** — policies: —
- **itl-0003-portal-dev-lambda-fee-external-custom-alert-03-role** — policies: —
- **itl-0003-portal-dev-lambda-pgaudit-01-role** — policies: AWSQuickSightIAMPolicy, AmazonSageMakerQuickSightVPCPolicy
- **itl-0003-portal-dev-lambda-sync-buk-absence-03-role** — policies: —
- **itl-0003-portal-dev-lambda-sync-buk-organization-03-role** — policies: —
- **itl-0003-portal-dev-lambda-sync-jira-03-role** — policies: —
- **lambdaQuicksight** — policies: AWSQuickSightIAMPolicy, AWSLambdaBasicExecutionRole-91fde2aa-0f16-46b9-833e-7f871c2e3377
  _(+ 3 more)_

### ec2.amazonaws.com

- **EC2-ClickHousePatch-Test-Role** — policies: AmazonSSMManagedInstanceCore
- **eksctl-eks-cluster-zealous-nodegro-NodeInstanceRole-SALR7sLl34KM** — policies: AmazonSSMManagedInstanceCore, AmazonEKS_CNI_Policy, AmazonEC2ContainerRegistryReadOnly...
- **itl-0003-portal-dev-ec2-apps-01-appsmith-role** — policies: itl-0003-portal-dev-ec2-apps-01-role-ebs-pol, CloudWatchAgentServerPolicy, AmazonSSMManagedInstanceCore...
- **itl-0003-portal-dev-ec2-apps-01-metabase-role** — policies: itl-0003-portal-dev-ec2-apps-01-role-ebs-pol, CloudWatchAgentServerPolicy, AmazonSSMManagedInstanceCore...
- **itl-0003-portal-dev-ec2-apps-03-airflow-role** — policies: itl-0003-portal-dev-ec2-apps-03-role-ebs-pol, CloudWatchAgentServerPolicy, AmazonSSMManagedInstanceCore...
- **itl-0003-portal-dev-ec2-apps-01-portal-role** — policies: itl-0003-portal-dev-ec2-apps-01-role-ebs-pol, CloudWatchAgentServerPolicy, AmazonSSMManagedInstanceCore...
- **itl-0003-portal-dev-ec2-apps-03-appsmith-role** — policies: itl-0003-portal-dev-ec2-apps-03-role-ebs-pol, CloudWatchAgentServerPolicy, AmazonSSMManagedInstanceCore...
- **itl-0003-portal-dev-ec2-apps-03-portal-role** — policies: itl-0003-portal-dev-ec2-apps-03-role-ebs-pol, CloudWatchAgentServerPolicy, AmazonSSMManagedInstanceCore...
- **itl-0003-portal-dev-ec2-apps-03-metabase-role** — policies: itl-0003-portal-dev-ec2-apps-03-role-ebs-pol, CloudWatchAgentServerPolicy, AmazonSSMManagedInstanceCore...
- **itl-0003-portal-dev-ec2-denver-03-role** — policies: CloudWatchAgentServerPolicy, AmazonSSMManagedInstanceCore
  _(+ 3 more)_

### eks.amazonaws.com

- **AWSServiceRoleForAmazonEKS** — policies: AmazonEKSServiceRolePolicy
- **eks-cluster-role** — policies: AmazonEKSClusterPolicy
- **eksctl-eks-cluster-zealous-cluster-ServiceRole-YMFecAfhlW2o** — policies: AmazonEKSClusterPolicy, AmazonEKSVPCResourceController
- **itl-0003-portal-dev-eks-apps-01-api-interchange-role** — policies: itl-0003-portal-dev-eks-apps-01-api-interchange-policy
- **itl-0003-portal-dev-eks-apps-01-role** — policies: itl-0003-portal-dev-eks-apps-01-role-ClusterEncryption20250109174108647000000009, itl-0003-portal-dev-eks-apps-01-role, AmazonEKSClusterPolicy...
- **itl-0003-portal-dev-eks-apps-03-role** — policies: itl-0003-portal-dev-eks-apps-01-role, itl-0003-portal-dev-eks-apps-03-role-ClusterEncryption2025092623222913650000002c, AmazonEKSClusterPolicy

### rds.amazonaws.com

- **AWSServiceRoleForRDS** — policies: AmazonRDSServiceRolePolicy

### scheduler.amazonaws.com

- **itl-0003-portal-dev-role-event-bridge-ec2-03** — policies: itl-0003-portal-dev-role-event-bridge-ec2-03-inline
- **itl-0009-prtlgy-dev-role-scheduler-onoff-01** — policies: itl-0009-prtlgy-dev-policy-ec2-01

## Security Groups (key ones)

- **eks-cluster-sg-itl-0003-portal-dev-eks-apps-03-1649377597** (`sg-036eadb8fba73b4ac`) — 1 inbound rules, 1 outbound rules
    - IN  ALL all ports ← sg:sg-036eadb8fba73b4ac
    - OUT ALL all ports ← 0.0.0.0/0, sg:sg-036eadb8fba73b4ac
- **itl-0003-portal-dev-alb-apps-02-sg** (`sg-0693ad8e5b1345db6`) — 2 inbound rules, 1 outbound rules
    - IN  TCP port 80 ← 0.0.0.0/0
    - IN  TCP port 443 ← 0.0.0.0/0
    - OUT ALL all ports ← 0.0.0.0/0
- **itl-0003-portal-dev-denver-sg-03** (`sg-0922640d2a80f5742`) — 6 inbound rules, 7 outbound rules
    - IN  TCP port 1433 ← 10.0.3.100/32, sg:sg-097a391d184cf49cd, sg:sg-0aa6d55bd394447f6, sg:sg-036eadb8fba73b4ac, sg:sg-0145ab9baeae304ea, sg:sg-0964ec984f5d5efbc, sg:sg-01976563e41df450b, sg:sg-0e8cd582b4803bcfc, sg:sg-075a4dc84874b3be0, sg:sg-05975d35e046ca0bf, sg:sg-076cc56f6b3e12257, sg:sg-0f97b556d1e01ca15
    - IN  TCP port 22 ← sg:sg-076cc56f6b3e12257, sg:sg-0e219160bc1d471cf
    - IN  TCP port 1435 ← sg:sg-0aa6d55bd394447f6, sg:sg-05975d35e046ca0bf
    - IN  TCP port 2222 ← sg:sg-0aa6d55bd394447f6, sg:sg-01976563e41df450b, sg:sg-076cc56f6b3e12257
    - IN  TCP port 445 ← sg:sg-0e219160bc1d471cf, sg:sg-076cc56f6b3e12257
    - _(+ 1 more inbound)_
    - OUT TCP port 80 ← 0.0.0.0/0
    - OUT ALL all ports ← 172.8.3.32/32, 0.0.0.0/0
    - OUT TCP port 25 ← 0.0.0.0/0
    - OUT TCP port 587 ← 0.0.0.0/0
    - OUT TCP port 443 ← 10.12.0.0/16, 0.0.0.0/0
    - _(+ 2 more outbound)_
- **itl-0003-portal-dev-ec2-apps-03-sg** (`sg-01976563e41df450b`) — 11 inbound rules, 1 outbound rules
    - IN  TCP port 6443 ← sg:sg-0145ab9baeae304ea
    - IN  TCP port 9443 ← sg:sg-0145ab9baeae304ea
    - IN  TCP ports 1025-65535 ← sg:sg-01976563e41df450b
    - IN  TCP port 8443 ← sg:sg-0145ab9baeae304ea
    - IN  TCP ports 80-31909 ← sg:sg-0a19a117a93bc3291
    - _(+ 6 more inbound)_
    - OUT ALL all ports ← 0.0.0.0/0
- **itl-0003-portal-dev-ec2-clickhouse-03-sg** (`sg-05d2473cae7a50fab`) — 5 inbound rules, 1 outbound rules
    - IN  TCP port 9000 ← sg:sg-0aa6d55bd394447f6, sg:sg-05975d35e046ca0bf, sg:sg-01976563e41df450b, sg:sg-076cc56f6b3e12257
    - IN  TCP port 22 ← sg:sg-0aa6d55bd394447f6
    - IN  TCP port 5000 ← sg:sg-0922640d2a80f5742
    - IN  TCP port 8123 ← 10.10.0.0/16, sg:sg-0922640d2a80f5742, sg:sg-0aa6d55bd394447f6, sg:sg-01976563e41df450b
    - IN  TCP port 9004 ← sg:sg-0f97b556d1e01ca15
    - OUT ALL all ports ← 0.0.0.0/0
- **itl-0003-portal-dev-eks-apps-03-sg** (`sg-0145ab9baeae304ea`) — 1 inbound rules, 0 outbound rules
    - IN  TCP port 443 ← sg:sg-01976563e41df450b
- **itl-0003-portal-dev-lambda-fee-external-custom-alert-03-sg** (`sg-0454300e4d0c1f411`) — 0 inbound rules, 4 outbound rules
    - OUT TCP port 5432 ← 10.12.0.0/16
    - OUT TCP port 53 ← 10.12.0.0/16
    - OUT UDP port 53 ← 10.12.0.0/16
    - OUT TCP port 443 ← 0.0.0.0/0, sg:sg-02aab67c133afef91
- **itl-0003-portal-dev-lambda-pg-audit-03-sg** (`sg-054b6a28f76db503c`) — 0 inbound rules, 3 outbound rules
    - OUT UDP port 53 ← 10.12.0.0/16
    - OUT TCP port 53 ← 10.12.0.0/16
    - OUT TCP port 443 ← sg:sg-02aab67c133afef91, sg:sg-086fdd7e4b3d71f5f, pl:pl-64a5400d
- **itl-0003-portal-dev-lambda-sync-buk-absence-03-sg** (`sg-06717f2261d9bef36`) — 0 inbound rules, 4 outbound rules
    - OUT TCP port 5432 ← 10.12.0.0/16
    - OUT TCP port 53 ← 10.12.0.0/16
    - OUT UDP port 53 ← 10.12.0.0/16
    - OUT TCP port 443 ← 0.0.0.0/0, sg:sg-02aab67c133afef91
- **itl-0003-portal-dev-lambda-sync-buk-organization-03-sg** (`sg-0a4a3d94379c8d963`) — 0 inbound rules, 4 outbound rules
    - OUT TCP port 5432 ← 10.12.0.0/16
    - OUT UDP port 53 ← 10.12.0.0/16
    - OUT TCP port 53 ← 10.12.0.0/16
    - OUT TCP port 443 ← 0.0.0.0/0, sg:sg-02aab67c133afef91
- **itl-0003-portal-dev-lambda-sync-jira-03-sg** (`sg-01f1fa4ca795113d8`) — 0 inbound rules, 4 outbound rules
    - OUT TCP port 5432 ← 10.12.0.0/16
    - OUT TCP port 53 ← 10.12.0.0/16
    - OUT UDP port 53 ← 10.12.0.0/16
    - OUT TCP port 443 ← 0.0.0.0/0, sg:sg-02aab67c133afef91
- **itl-0003-portal-dev-rds-apps-03-sg** (`sg-0964ec984f5d5efbc`) — 1 inbound rules, 1 outbound rules
    - IN  TCP port 5432 ← 10.0.3.100/32, 10.11.3.12/32, sg:sg-097a391d184cf49cd, sg:sg-0aa6d55bd394447f6, sg:sg-01976563e41df450b, sg:sg-05975d35e046ca0bf, sg:sg-0e8cd582b4803bcfc, sg:sg-0f97b556d1e01ca15, sg:sg-04aac9e78d6520b80, sg:sg-0454300e4d0c1f411, sg:sg-06717f2261d9bef36, sg:sg-01f1fa4ca795113d8, sg:sg-0a4a3d94379c8d963, sg:sg-05d2473cae7a50fab
    - OUT ALL all ports ← 0.0.0.0/0
- **itl-0003-portal-dev-vpc-endpoints-03-sg** (`sg-086fdd7e4b3d71f5f`) — 1 inbound rules, 1 outbound rules
    - IN  TCP port 443 ← sg:sg-054b6a28f76db503c
    - OUT ALL all ports ← 0.0.0.0/0
- **itl-0003-portal-dev-vpc-endpoints-03-sg** (`sg-0f030a669cff63734`) — 0 inbound rules, 1 outbound rules
    - OUT ALL all ports ← 0.0.0.0/0
- **itl-0003-portal-dev-vpc-endpoints-03-sg** (`sg-02aab67c133afef91`) — 2 inbound rules, 1 outbound rules
    - IN  TCP ports 1024-1064 ← 10.12.0.0/16
    - IN  TCP port 443 ← 10.12.0.0/16
    - OUT ALL all ports ← 0.0.0.0/0
- **itl-0003-portal-dev-vpc-endpoints-03-sg** (`sg-03be85899ca6402c1`) — 0 inbound rules, 1 outbound rules
    - OUT ALL all ports ← 0.0.0.0/0
- **sg-07f51d4b2389dc8ca** (`sg-07f51d4b2389dc8ca`) — 2 inbound rules, 1 outbound rules
    - IN  TCP port 22 ← 0.0.0.0/0
    - IN  TCP port 443 ← 0.0.0.0/0
    - OUT ALL all ports ← 0.0.0.0/0
- **sg-0e9085264a5e2e241** (`sg-0e9085264a5e2e241`) — 2 inbound rules, 1 outbound rules
    - IN  UDP port 53 ← sg:sg-03bed10a7bf7da98d, sg:sg-0f97b556d1e01ca15
    - IN  TCP port 53 ← sg:sg-03bed10a7bf7da98d, sg:sg-0f97b556d1e01ca15
    - OUT ALL all ports ← 0.0.0.0/0
- **sg-0f97b556d1e01ca15** (`sg-0f97b556d1e01ca15`) — 0 inbound rules, 1 outbound rules
    - OUT ALL all ports ← 0.0.0.0/0
