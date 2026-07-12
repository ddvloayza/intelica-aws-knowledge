# Portal-Dev — Security

_Last updated: 2026-07-12 17:54 UTC_

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
- **itl-0003-portal-dev-lambda-fee-external-custom-alert-03-role** — policies: —
- **itl-0003-portal-dev-lambda-pg-audit-03-role** — policies: —
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
- **itl-0003-portal-dev-ec2-apps-01-portal-role** — policies: itl-0003-portal-dev-ec2-apps-01-role-ebs-pol, CloudWatchAgentServerPolicy, AmazonSSMManagedInstanceCore...
- **itl-0003-portal-dev-ec2-apps-03-appsmith-role** — policies: itl-0003-portal-dev-ec2-apps-03-role-ebs-pol, CloudWatchAgentServerPolicy, AmazonSSMManagedInstanceCore...
- **itl-0003-portal-dev-ec2-apps-03-airflow-role** — policies: itl-0003-portal-dev-ec2-apps-03-role-ebs-pol, CloudWatchAgentServerPolicy, AmazonSSMManagedInstanceCore...
- **itl-0003-portal-dev-ec2-apps-01-metabase-role** — policies: itl-0003-portal-dev-ec2-apps-01-role-ebs-pol, CloudWatchAgentServerPolicy, AmazonSSMManagedInstanceCore...
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

- **eks-cluster-sg-itl-0003-portal-dev-eks-apps-03-1649377597** (`sg-036eadb8fba73b4ac`) — 0 ingress rules, 0 egress rules
- **itl-0003-portal-dev-alb-apps-02-sg** (`sg-0693ad8e5b1345db6`) — 0 ingress rules, 0 egress rules
- **itl-0003-portal-dev-denver-sg-03** (`sg-0922640d2a80f5742`) — 0 ingress rules, 0 egress rules
- **itl-0003-portal-dev-ec2-apps-03-sg** (`sg-01976563e41df450b`) — 0 ingress rules, 0 egress rules
- **itl-0003-portal-dev-ec2-clickhouse-03-sg** (`sg-05d2473cae7a50fab`) — 0 ingress rules, 0 egress rules
- **itl-0003-portal-dev-eks-apps-03-sg** (`sg-0145ab9baeae304ea`) — 0 ingress rules, 0 egress rules
- **itl-0003-portal-dev-lambda-fee-external-custom-alert-03-sg** (`sg-0454300e4d0c1f411`) — 0 ingress rules, 0 egress rules
- **itl-0003-portal-dev-lambda-pg-audit-03-sg** (`sg-054b6a28f76db503c`) — 0 ingress rules, 0 egress rules
- **itl-0003-portal-dev-lambda-sync-buk-absence-03-sg** (`sg-06717f2261d9bef36`) — 0 ingress rules, 0 egress rules
- **itl-0003-portal-dev-lambda-sync-buk-organization-03-sg** (`sg-0a4a3d94379c8d963`) — 0 ingress rules, 0 egress rules
- **itl-0003-portal-dev-lambda-sync-jira-03-sg** (`sg-01f1fa4ca795113d8`) — 0 ingress rules, 0 egress rules
- **itl-0003-portal-dev-rds-apps-03-sg** (`sg-0964ec984f5d5efbc`) — 0 ingress rules, 0 egress rules
- **itl-0003-portal-dev-vpc-endpoints-03-sg** (`sg-086fdd7e4b3d71f5f`) — 0 ingress rules, 0 egress rules
- **itl-0003-portal-dev-vpc-endpoints-03-sg** (`sg-0f030a669cff63734`) — 0 ingress rules, 0 egress rules
- **itl-0003-portal-dev-vpc-endpoints-03-sg** (`sg-02aab67c133afef91`) — 0 ingress rules, 0 egress rules
- **itl-0003-portal-dev-vpc-endpoints-03-sg** (`sg-03be85899ca6402c1`) — 0 ingress rules, 0 egress rules
- **sg-07f51d4b2389dc8ca** (`sg-07f51d4b2389dc8ca`) — 0 ingress rules, 0 egress rules
- **sg-0e9085264a5e2e241** (`sg-0e9085264a5e2e241`) — 0 ingress rules, 0 egress rules
- **sg-0f97b556d1e01ca15** (`sg-0f97b556d1e01ca15`) — 0 ingress rules, 0 egress rules
