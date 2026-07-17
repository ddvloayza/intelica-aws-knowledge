# Portal-Prod — Security

_Last updated: 2026-07-17 14:42 UTC_

## KMS Keys (Customer Managed)

### alias/pci_2026
- **Key ID:** `00747795-c66b-4d97-bdc7-455be5638aa5`  
- **Usage:** ENCRYPT_DECRYPT  
- **Rotation:** Disabled  
- **Multi-region:** No  
- **Description:** 

### alias/alias/itl-0003-portal-prd-kms-general-02
- **Key ID:** `2c0f162d-26d5-4799-8c84-033bf5204000`  
- **Usage:** ENCRYPT_DECRYPT  
- **Rotation:** Enabled  
- **Multi-region:** No  
- **Description:** KMS customer managed key

### 5cbf839b-c721-4cc9-a87e-67002de7ef17
- **Key ID:** `5cbf839b-c721-4cc9-a87e-67002de7ef17`  
- **Usage:** ENCRYPT_DECRYPT  
- **Rotation:** Enabled  
- **Multi-region:** No  
- **Description:** KMS customer managed key

## IAM Roles by Trusted Service

### lambda.amazonaws.com

- **aws-controltower-ForwardSnsNotificationRole** — policies: AWSLambdaBasicExecutionRole
- **AWS-QuickSetup-BaselineOverrides-LambdaRole-1yqvz** — policies: —
- **AWS-QuickSetup-PatchPolicy-RoleForLambda-NT-us-east-1-1yqvz** — policies: AWSLambdaBasicExecutionRole
- **DatadogIntegration-ForwarderStack-WC-ForwarderRole-JSQA8ZV8AQME** — policies: AWSLambdaVPCAccessExecutionRole, AWSLambdaBasicExecutionRole
- **DatadogIntegration-Datado-LambdaExecutionRoleDatad-3YVYFQKD2081** — policies: AWSLambdaBasicExecutionRole
- **itl-0003-portal-prd-lambda-fsx-log-export-02-role** — policies: —
- **itl-0003-portal-prd-lambda-sync-buk-absence-02-role** — policies: —
- **itl-0003-portal-prd-lambda-pg-audit-02-role** — policies: —
- **itl-0003-portal-prd-lambda-sync-buk-organization-02-role** — policies: —
- **itl-0003-portal-prd-lambda-sync-jira-02-role** — policies: —
  _(+ 7 more)_

### ec2.amazonaws.com

- **AmazonEC2RoleForLaunchWizard** — policies: AmazonSSMManagedInstanceCore, AmazonEC2RolePolicyForLaunchWizard
- **AmazonSSMRoleForInstancesQuickSetup** — policies: AmazonSSMManagedInstanceCore, AWSQuickSetupPatchPolicyBaselineAccess
- **AWSApplicationMigrationConversionServerRole** — policies: AWSApplicationMigrationConversionServerPolicy
- **AWSApplicationMigrationLaunchInstanceWithDrsRole** — policies: AmazonSSMManagedInstanceCore, AWSElasticDisasterRecoveryEc2InstancePolicy
- **AWSApplicationMigrationLaunchInstanceWithSsmRole** — policies: AmazonSSMManagedInstanceCore
- **AWSApplicationMigrationReplicationServerRole** — policies: AWSApplicationMigrationReplicationServerPolicy
- **AWSCloud9SSMAccessRole** — policies: AWSCloud9SSMInstanceProfile
- **ecsInstanceRole** — policies: AmazonEC2ContainerServiceforEC2Role
- **ECS_EC2Role** — policies: AmazonEC2ContainerServiceforEC2Role
- **itl-0003-portal-prd-ec2-apps-01-metabase-role** — policies: itl-0003-portal-prd-ec2-apps-01-role-ebs-pol, CloudWatchAgentServerPolicy, AmazonSSMManagedInstanceCore...
  _(+ 32 more)_

### eks.amazonaws.com

- **AWSServiceRoleForAmazonEKS** — policies: AmazonEKSServiceRolePolicy
- **itl-0003-portal-prd-eks-apps-01-role** — policies: itl-0003-portal-prd-eks-apps-01-role, itl-0003-portal-prd-eks-apps-01-role-ClusterEncryption20250423202220913700000010, AmazonEKSClusterPolicy...
- **itl-0003-portal-prd-eks-apps-02-role** — policies: itl-0003-portal-prd-eks-apps-02-role, itl-0003-portal-prd-eks-apps-02-role-ClusterEncryption20251112150646433600000002, AmazonEKSClusterPolicy...

### ecs-tasks.amazonaws.com

- **ECSRole_TaskExecution** — policies: AmazonECSTaskExecutionRolePolicy
- **ecsTaskExecutionRole** — policies: AmazonECSTaskExecutionRolePolicy

### rds.amazonaws.com

- **AWSServiceRoleForRDS** — policies: AmazonRDSServiceRolePolicy
- **dbaccesss3role** — policies: sqlNativeBackup-2023-04-25-11.20.18.258

### scheduler.amazonaws.com

- **Amazon_EventBridge_Scheduler_LAMBDA_37d890556a** — policies: Amazon-EventBridge-Scheduler-Execution-Policy-e8f35682-2353-4728-9747-924601c0f5f7
- **Amazon_EventBridge_Scheduler_LAMBDA_3592d775ef** — policies: Amazon-EventBridge-Scheduler-Execution-Policy-bd41431d-bdcf-49fa-91b7-98be4f86f576
- **Amazon_EventBridge_Scheduler_LAMBDA_a4eea9b444** — policies: Amazon-EventBridge-Scheduler-Execution-Policy-6dd59e7d-c9dc-42dd-b301-c0f384951eea
- **Amazon_EventBridge_Scheduler_LAMBDA_d116d46235** — policies: Amazon-EventBridge-Scheduler-Execution-Policy-f92064a3-c35e-4c2a-b594-e104bc773df5
- **itl-policy-to-schedule-restart-ec2-role** — policies: itl-policy-to-schedule-restart-ec2-policy
- **itl-0003-portal-prd-role-event-bridge-ec2-02** — policies: itl-0003-portal-prd-role-event-bridge-ec2-02-inline

## Security Groups (key ones)

- **AWS Application Migration Service default Replication Server Security Group** (`sg-00dc78ebf8c5726bd`) — 1 inbound rules, 2 outbound rules
    - IN  TCP port 1500 ← 0.0.0.0/0
    - OUT UDP port 53 ← 0.0.0.0/0
    - OUT TCP port 443 ← 0.0.0.0/0
- **ITL-Server-FortiSIEM-sg** (`sg-06407a58a795a0fc2`) — 5 inbound rules, 1 outbound rules
    - IN  TCP port 514 ← 10.0.0.0/16
    - IN  TCP port 22 ← 10.0.3.100/32, 10.18.4.81/32
    - IN  TCP port 161 ← 10.0.0.0/16
    - IN  TCP port 443 ← 10.0.3.100/32
    - IN  UDP port 514 ← 10.0.0.0/16
    - OUT ALL all ports ← 0.0.0.0/0
- **VM-1-sg** (`sg-08494443881f463eb`) — 0 inbound rules, 0 outbound rules
- **VM-10-sg** (`sg-0ce8fbf4007100fd6`) — 1 inbound rules, 1 outbound rules
    - IN  TCP port 3389 ← 10.18.4.81/32, 10.0.3.100/32
    - OUT ALL all ports ← 0.0.0.0/0
- **VM-2-sg** (`sg-0a96d436ac3cce15a`) — 1 inbound rules, 1 outbound rules
    - IN  TCP port 3389 ← 10.0.3.100/32, 10.18.4.81/32
    - OUT ALL all ports ← 0.0.0.0/0
- **VM-3-sg** (`sg-05477e0120952808e`) — 1 inbound rules, 1 outbound rules
    - IN  TCP port 3389 ← 10.18.4.81/32, 10.0.3.100/32
    - OUT ALL all ports ← 0.0.0.0/0
- **VM-4-sg** (`sg-01b60b6075b9422b2`) — 1 inbound rules, 1 outbound rules
    - IN  TCP port 3389 ← 10.0.3.100/32, 10.18.4.81/32
    - OUT ALL all ports ← 0.0.0.0/0
- **VM-5-sg** (`sg-0373c8b39326439e7`) — 1 inbound rules, 1 outbound rules
    - IN  TCP port 3389 ← 10.0.3.100/32, 10.18.4.81/32
    - OUT ALL all ports ← 0.0.0.0/0
- **VM-6-sg** (`sg-018c523ed2199f54c`) — 1 inbound rules, 1 outbound rules
    - IN  TCP port 3389 ← 10.0.3.100/32, 10.18.4.81/32
    - OUT ALL all ports ← 0.0.0.0/0
- **VM-7-sg** (`sg-011b2fc8b6dcd08c0`) — 1 inbound rules, 1 outbound rules
    - IN  TCP port 3389 ← 10.18.4.81/32, 10.0.3.100/32
    - OUT ALL all ports ← 0.0.0.0/0
- **VM-8-sg** (`sg-09fafdc5ed122c78a`) — 1 inbound rules, 1 outbound rules
    - IN  TCP port 3389 ← 10.0.3.100/32, 10.18.4.81/32
    - OUT ALL all ports ← 0.0.0.0/0
- **VM-9-sg** (`sg-00b87ac4a91c8a2d8`) — 1 inbound rules, 1 outbound rules
    - IN  TCP port 3389 ← 10.18.4.81/32, 10.0.3.100/32
    - OUT ALL all ports ← 0.0.0.0/0
- **VM11-sg** (`sg-0b6f4362125cb52cb`) — 1 inbound rules, 1 outbound rules
    - IN  TCP port 3389 ← 10.0.3.100/32, 10.18.4.81/32
    - OUT ALL all ports ← 0.0.0.0/0
- **VM12-sg** (`sg-077f9142b25203033`) — 1 inbound rules, 1 outbound rules
    - IN  TCP port 3389 ← 10.18.4.81/32, 10.0.3.100/32
    - OUT ALL all ports ← 0.0.0.0/0
- **VM13-sg** (`sg-0fc494c48d467ab08`) — 1 inbound rules, 1 outbound rules
    - IN  TCP port 3389 ← 10.18.4.81/32, 10.0.3.100/32
    - OUT ALL all ports ← 0.0.0.0/0
- **VMNN-sg** (`sg-03fdf9a2a3a970875`) — 1 inbound rules, 0 outbound rules
    - IN  TCP port 3389 ← sg:sg-0aa6d55bd394447f6
- **eks-cluster-sg-itl-0003-portal-prd-eks-apps-02-2029633073** (`sg-0e8864e42cb1e54d7`) — 1 inbound rules, 1 outbound rules
    - IN  ALL all ports ← sg:sg-0e8864e42cb1e54d7
    - OUT ALL all ports ← 0.0.0.0/0, sg:sg-0e8864e42cb1e54d7
- **itl-0003-portal-prd--sg-02** (`sg-06c94aeac9c2cf00a`) — 0 inbound rules, 0 outbound rules
- **itl-0003-portal-prd-alb-apps-01-sg** (`sg-09d2e75a3a87befdf`) — 2 inbound rules, 1 outbound rules
    - IN  TCP port 80 ← 0.0.0.0/0
    - IN  TCP port 443 ← 0.0.0.0/0
    - OUT ALL all ports ← 0.0.0.0/0
- **itl-0003-portal-prd-denver-sg-02** (`sg-04aac9e78d6520b80`) — 5 inbound rules, 1 outbound rules
    - IN  TCP port 1433 ← 10.12.0.0/16, sg:sg-0aa6d55bd394447f6, sg:sg-067b9fd88018f9db1, sg:sg-0175bf9584150c48d, sg:sg-0becff9d6790cf669, sg:sg-05d2473cae7a50fab, sg:sg-023d0e02fd0b67e82, sg:sg-097a391d184cf49cd, sg:sg-0e8cd582b4803bcfc, sg:sg-05f186888e83ce35d
    - IN  ALL all ports ← sg:sg-0d760cd30300debca
    - IN  TCP port 22 ← sg:sg-0aa6d55bd394447f6, sg:sg-035300560ba0db669, sg:sg-064588145926737f4, sg:sg-0e8864e42cb1e54d7, sg:sg-0175bf9584150c48d, sg:sg-0becff9d6790cf669
    - IN  TCP port 3389 ← sg:sg-0aa6d55bd394447f6
    - IN  TCP port 445 ← sg:sg-0175bf9584150c48d, sg:sg-067b9fd88018f9db1, sg:sg-0e84f073bfa8dde00
    - OUT ALL all ports ← 0.0.0.0/0

_(+ 24 more security groups)_
