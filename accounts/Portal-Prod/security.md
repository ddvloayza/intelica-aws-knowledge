# Portal-Prod — Security

_Last updated: 2026-07-12 01:20 UTC_

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
- **DatadogIntegration-Datado-LambdaExecutionRoleDatad-3YVYFQKD2081** — policies: AWSLambdaBasicExecutionRole
- **DatadogIntegration-ForwarderStack-WC-ForwarderRole-JSQA8ZV8AQME** — policies: AWSLambdaVPCAccessExecutionRole, AWSLambdaBasicExecutionRole
- **itl-0003-portal-prd-lambda-fee-external-custom-alert-02-role** — policies: —
- **itl-0003-portal-prd-lambda-fsx-log-export-02-role** — policies: —
- **itl-0003-portal-prd-lambda-pg-audit-02-role** — policies: —
- **itl-0003-portal-prd-lambda-sync-buk-organization-02-role** — policies: —
- **itl-0003-portal-prd-lambda-sync-buk-absence-02-role** — policies: —
  _(+ 7 more)_

### ec2.amazonaws.com

- **AmazonEC2RoleForLaunchWizard** — policies: AmazonSSMManagedInstanceCore, AmazonEC2RolePolicyForLaunchWizard
- **AmazonSSMRoleForInstancesQuickSetup** — policies: AmazonSSMManagedInstanceCore, AWSQuickSetupPatchPolicyBaselineAccess
- **AWSApplicationMigrationConversionServerRole** — policies: AWSApplicationMigrationConversionServerPolicy
- **AWSApplicationMigrationLaunchInstanceWithDrsRole** — policies: AmazonSSMManagedInstanceCore, AWSElasticDisasterRecoveryEc2InstancePolicy
- **AWSApplicationMigrationLaunchInstanceWithSsmRole** — policies: AmazonSSMManagedInstanceCore
- **AWSCloud9SSMAccessRole** — policies: AWSCloud9SSMInstanceProfile
- **AWSApplicationMigrationReplicationServerRole** — policies: AWSApplicationMigrationReplicationServerPolicy
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
- **Amazon_EventBridge_Scheduler_LAMBDA_d116d46235** — policies: Amazon-EventBridge-Scheduler-Execution-Policy-f92064a3-c35e-4c2a-b594-e104bc773df5
- **Amazon_EventBridge_Scheduler_LAMBDA_a4eea9b444** — policies: Amazon-EventBridge-Scheduler-Execution-Policy-6dd59e7d-c9dc-42dd-b301-c0f384951eea
- **Amazon_EventBridge_Scheduler_LAMBDA_3592d775ef** — policies: Amazon-EventBridge-Scheduler-Execution-Policy-bd41431d-bdcf-49fa-91b7-98be4f86f576
- **itl-0003-portal-prd-role-event-bridge-ec2-02** — policies: itl-0003-portal-prd-role-event-bridge-ec2-02-inline
- **itl-policy-to-schedule-restart-ec2-role** — policies: itl-policy-to-schedule-restart-ec2-policy

## Security Groups (key ones)

- **AWS Application Migration Service default Replication Server Security Group** (`sg-00dc78ebf8c5726bd`) — 0 ingress rules, 0 egress rules
- **ITL-Server-FortiSIEM-sg** (`sg-06407a58a795a0fc2`) — 0 ingress rules, 0 egress rules
- **VM-1-sg** (`sg-08494443881f463eb`) — 0 ingress rules, 0 egress rules
- **VM-10-sg** (`sg-0ce8fbf4007100fd6`) — 0 ingress rules, 0 egress rules
- **VM-2-sg** (`sg-0a96d436ac3cce15a`) — 0 ingress rules, 0 egress rules
- **VM-3-sg** (`sg-05477e0120952808e`) — 0 ingress rules, 0 egress rules
- **VM-4-sg** (`sg-01b60b6075b9422b2`) — 0 ingress rules, 0 egress rules
- **VM-5-sg** (`sg-0373c8b39326439e7`) — 0 ingress rules, 0 egress rules
- **VM-6-sg** (`sg-018c523ed2199f54c`) — 0 ingress rules, 0 egress rules
- **VM-7-sg** (`sg-011b2fc8b6dcd08c0`) — 0 ingress rules, 0 egress rules
- **VM-8-sg** (`sg-09fafdc5ed122c78a`) — 0 ingress rules, 0 egress rules
- **VM-9-sg** (`sg-00b87ac4a91c8a2d8`) — 0 ingress rules, 0 egress rules
- **VM11-sg** (`sg-0b6f4362125cb52cb`) — 0 ingress rules, 0 egress rules
- **VM12-sg** (`sg-077f9142b25203033`) — 0 ingress rules, 0 egress rules
- **VM13-sg** (`sg-0fc494c48d467ab08`) — 0 ingress rules, 0 egress rules
- **VMNN-sg** (`sg-03fdf9a2a3a970875`) — 0 ingress rules, 0 egress rules
- **eks-cluster-sg-itl-0003-portal-prd-eks-apps-02-2029633073** (`sg-0e8864e42cb1e54d7`) — 0 ingress rules, 0 egress rules
- **itl-0003-portal-prd--sg-02** (`sg-06c94aeac9c2cf00a`) — 0 ingress rules, 0 egress rules
- **itl-0003-portal-prd-alb-apps-01-sg** (`sg-09d2e75a3a87befdf`) — 0 ingress rules, 0 egress rules
- **itl-0003-portal-prd-denver-sg-02** (`sg-04aac9e78d6520b80`) — 0 ingress rules, 0 egress rules

_(+ 24 more security groups)_
