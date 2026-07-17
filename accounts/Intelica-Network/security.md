# Intelica-Network — Security

_Last updated: 2026-07-17 14:42 UTC_

## KMS Keys (Customer Managed)

### alias/alias/itl-0002-shared-network-all-kms-general-02
- **Key ID:** `e6812e57-52fa-4ffe-aca6-f691711076e8`  
- **Usage:** ENCRYPT_DECRYPT  
- **Rotation:** Enabled  
- **Multi-region:** No  
- **Description:** KMS customer managed key

## IAM Roles by Trusted Service

### lambda.amazonaws.com

- **aws-controltower-ForwardSnsNotificationRole** — policies: AWSLambdaBasicExecutionRole

### ec2.amazonaws.com

- **AD-Windows-2016-Role** — policies: AmazonSSMManagedInstanceCore
- **itl-0001-shared-network-all-ec2-pritunl-01-role** — policies: CloudWatchAgentServerPolicy, AmazonSSMManagedInstanceCore, AmazonEKS_CNI_Policy...
- **itl-0002-shared-network-all-ec2-directory-all-ec2-02-role** — policies: CloudWatchAgentServerPolicy, AmazonSSMDirectoryServiceAccess, AmazonSSMManagedInstanceCore
- **itl-0002-shared-network-all-ec2-pritunl-02-role** — policies: CloudWatchAgentServerPolicy, AmazonSSMManagedInstanceCore, AmazonEKS_CNI_Policy...
- **itl-0006-active-directory-all-ec2-01-role** — policies: AmazonSSMManagedInstanceCore
- **SSm-access** — policies: AmazonSSMFullAccess, AmazonSSMManagedInstanceCore, AmazonEC2RoleforSSM

### eks.amazonaws.com

- **AWSServiceRoleForAmazonEKS** — policies: AmazonEKSServiceRolePolicy
- **itl-0001-shared-network-all-eks-pritunl-01-role** — policies: AmazonEKSClusterPolicy, AmazonEKSVPCResourceController, itl-0001-shared-network-all-eks-pritunl-01-role...
- **itl-0002-shared-network-all-eks-pritunl-02-role** — policies: AmazonEKSClusterPolicy, AmazonEKSVPCResourceController, itl-0002-shared-network-all-eks-pritunl-02-role...

## Security Groups (key ones)

- **eks-cluster-sg-itl-0002-shared-network-all-eks-pritunl-02-1559606019** (`sg-0d8e8df1695843092`) — 1 inbound rules, 1 outbound rules
    - IN  ALL all ports ← sg:sg-0d8e8df1695843092
    - OUT ALL all ports ← 0.0.0.0/0, sg:sg-0d8e8df1695843092
- **itl-0002-shared-network-all-ec2-directory-all-ec2-02-sg** (`sg-03bed10a7bf7da98d`) — 22 inbound rules, 1 outbound rules
    - IN  UDP port 464 ← 0.0.0.0/0
    - IN  TCP port 464 ← 0.0.0.0/0
    - IN  TCP ports 49152-65535 ← 0.0.0.0/0
    - IN  UDP port 389 ← 0.0.0.0/0
    - IN  UDP port 53 ← 0.0.0.0/0
    - _(+ 17 more inbound)_
    - OUT ALL all ports ← 0.0.0.0/0
- **itl-0002-shared-network-all-ec2-pritunl-02-sg** (`sg-0aa6d55bd394447f6`) — 11 inbound rules, 1 outbound rules
    - IN  TCP port 6443 ← sg:sg-04aca11661012920a
    - IN  TCP port 9443 ← sg:sg-04aca11661012920a
    - IN  TCP ports 1025-65535 ← sg:sg-0aa6d55bd394447f6
    - IN  TCP port 8443 ← sg:sg-04aca11661012920a
    - IN  TCP ports 443-30632 ← sg:sg-043f24a24d1750bf7
    - _(+ 6 more inbound)_
    - OUT ALL all ports ← 0.0.0.0/0
- **itl-0002-shared-network-all-eks-pritunl-02-sg** (`sg-04aca11661012920a`) — 1 inbound rules, 0 outbound rules
    - IN  TCP port 443 ← sg:sg-0aa6d55bd394447f6
- **itl-0002-shared-network-all-vpc-endpoints-sg** (`sg-0a459eecd4fa98749`) — 2 inbound rules, 1 outbound rules
    - IN  TCP port 80 ← 10.18.0.0/16
    - IN  TCP port 443 ← 10.18.0.0/16
    - OUT ALL all ports ← 0.0.0.0/0
