# Analytics-Prod — Security

_Last updated: 2026-07-17 14:42 UTC_

## KMS Keys (Customer Managed)

### alias/itl-0005-ana-prd-ebs-02
- **Key ID:** `746658b3-5dd0-4c98-b05d-2ace2021dc74`  
- **Usage:** ENCRYPT_DECRYPT  
- **Rotation:** Enabled  
- **Multi-region:** No  
- **Description:** KMS key for EBS volume encryption in EKS nodes

### alias/eks/itl-0005-ana-prd-eks-af-02
- **Key ID:** `d5972fe1-ae4d-446d-9ee7-d8c60f9ee511`  
- **Usage:** ENCRYPT_DECRYPT  
- **Rotation:** Enabled  
- **Multi-region:** No  
- **Description:** itl-0005-ana-prd-eks-af-02 cluster encryption key

## IAM Roles by Trusted Service

### lambda.amazonaws.com

- **aws-controltower-ForwardSnsNotificationRole** — policies: AWSLambdaBasicExecutionRole

### ec2.amazonaws.com

- **itl-0005-ana-prd-ng-dags-02-role-20251017031718273000000001** — policies: CloudWatchAgentServerPolicy, AmazonEKS_CNI_Policy, AmazonEC2ContainerRegistryReadOnly...

### eks.amazonaws.com

- **AWSServiceRoleForAmazonEKS** — policies: AmazonEKSServiceRolePolicy
- **itl-0005-ana-prd-eks-af-02-role-20251017031718274000000003** — policies: itl-0005-ana-prd-eks-af-02-role-ClusterEncryption2025101703174642380000000e, itl-0005-ana-prd-eks-af-02-role-20251017031718273400000002, AmazonEKSClusterPolicy...

### rds.amazonaws.com

- **AWSServiceRoleForRDS** — policies: AmazonRDSServiceRolePolicy

## Security Groups (key ones)

- **default** (`sg-083547b121cc43193`) — 0 inbound rules, 0 outbound rules
- **eks-cluster-sg-itl-0005-ana-prd-eks-af-02-1193014442** (`sg-005bad6e329e4bc98`) — 2 inbound rules, 1 outbound rules
    - IN  TCP port 8080 ← sg:sg-09e84fe96301bd6fb
    - IN  ALL all ports ← sg:sg-005bad6e329e4bc98
    - OUT ALL all ports ← 0.0.0.0/0, sg:sg-005bad6e329e4bc98
- **itl-0005-ana-prd-evpc-02-sg** (`sg-0e0494efc97b8b13d`) — 1 inbound rules, 1 outbound rules
    - IN  TCP port 443 ← 10.15.0.0/24, 10.15.1.0/24, 10.15.2.0/24
    - OUT ALL all ports ← 0.0.0.0/0
- **itl-0005-ana-prd-sg-windows-test-02** (`sg-0ea3d643b45650c9a`) — 2 inbound rules, 1 outbound rules
    - IN  ALL all ports ← 10.15.0.0/16
    - IN  TCP port 3389 ← 190.130.103.217/32
    - OUT ALL all ports ← 0.0.0.0/0
- **sg-074026ddbbdad7fbb** (`sg-074026ddbbdad7fbb`) — 1 inbound rules, 1 outbound rules
    - IN  TCP port 5432 ← 10.15.1.0/24, 10.15.0.0/24, 10.15.2.0/24
    - OUT ALL all ports ← 0.0.0.0/0
