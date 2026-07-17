# Analytics-Dev — Security

_Last updated: 2026-07-17 14:42 UTC_

## KMS Keys (Customer Managed)

### alias/itl-0005-ana-dev-ebs-02
- **Key ID:** `a373bb63-6782-49ba-90f2-a95abc7cea2b`  
- **Usage:** ENCRYPT_DECRYPT  
- **Rotation:** Enabled  
- **Multi-region:** No  
- **Description:** KMS key for EBS volume encryption in EKS nodes

### alias/eks/itl-0005-ana-dev-eks-af-02
- **Key ID:** `e051ccf1-a4fe-4586-b4e3-df092fc7775a`  
- **Usage:** ENCRYPT_DECRYPT  
- **Rotation:** Enabled  
- **Multi-region:** No  
- **Description:** itl-0005-ana-dev-eks-af-02 cluster encryption key

## IAM Roles by Trusted Service

### lambda.amazonaws.com

- **aws-controltower-ForwardSnsNotificationRole** — policies: AWSLambdaBasicExecutionRole

### ec2.amazonaws.com

- **itl-0005-ana-dev-ng-dags-02-role-20251012035013397800000005** — policies: CloudWatchAgentServerPolicy, AmazonEKS_CNI_Policy, AmazonEC2ContainerRegistryReadOnly...
- **itl-0005-ana-dev-role-ec2-ssm-01** — policies: AmazonSSMManagedInstanceCore

### eks.amazonaws.com

- **AWSServiceRoleForAmazonEKS** — policies: AmazonEKSServiceRolePolicy
- **itl-0005-ana-dev-eks-af-02-role-20251012035013387600000002** — policies: AmazonEKSClusterPolicy, AmazonEKSVPCResourceController, itl-0005-ana-dev-eks-af-02-role-ClusterEncryption2025101203504392960000000e...

### rds.amazonaws.com

- **AWSServiceRoleForRDS** — policies: AmazonRDSServiceRolePolicy

## Security Groups (key ones)

- **default** (`sg-0dae416b84554ddd6`) — 0 inbound rules, 0 outbound rules
- **eks-cluster-sg-itl-0005-ana-dev-eks-af-02-755421789** (`sg-08a170933bb288237`) — 2 inbound rules, 4 outbound rules
    - IN  TCP port 8080 ← sg:sg-02006a6eae69e1737
    - IN  ALL all ports ← sg:sg-02006a6eae69e1737, sg:sg-08a170933bb288237
    - OUT ALL all ports ← 0.0.0.0/0, sg:sg-08a170933bb288237
    - OUT TCP port 22 ← 0.0.0.0/0
    - OUT UDP port 53 ← 10.16.0.0/16
    - OUT TCP port 443 ← 10.13.0.0/16, 10.16.0.0/16, 172.5.0.0/16, 172.8.0.0/16, 172.9.0.0/16
- **itl-0005-ana-dev-evpc-02-sg** (`sg-07a758f02116e2f3e`) — 1 inbound rules, 1 outbound rules
    - IN  TCP port 443 ← 10.16.0.0/24, 10.16.1.0/24, 10.16.2.0/24
    - OUT ALL all ports ← 0.0.0.0/0
- **sg-085b5a07768a54d37** (`sg-085b5a07768a54d37`) — 1 inbound rules, 1 outbound rules
    - IN  TCP port 5432 ← 10.16.1.0/24, 10.16.2.0/24, 10.16.0.0/24
    - OUT ALL all ports ← 0.0.0.0/0
