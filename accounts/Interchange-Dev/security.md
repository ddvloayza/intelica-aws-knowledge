# Interchange-Dev — Security

_Last updated: 2026-07-12 01:20 UTC_

## KMS Keys (Customer Managed)

### alias/alias/itl-0004-itx-dev-kms-general-02
- **Key ID:** `560dd37d-d216-49bb-90ff-8d21f03db55f`  
- **Usage:** ENCRYPT_DECRYPT  
- **Rotation:** Enabled  
- **Multi-region:** No  
- **Description:** KMS customer managed key

## IAM Roles by Trusted Service

### lambda.amazonaws.com

- **AWS-QuickSetup-SSM-LifecycleManagement-LA-us-east-1** — policies: AWSQuickSetupSSMLifecycleManagementExecutionPolicy
- **aws-controltower-ForwardSnsNotificationRole** — policies: AWSLambdaBasicExecutionRole
- **itl-0004-itx-dev-intchg-02-lmbd-mc-exchange-rates-role** — policies: —
- **itl-0004-itx-dev-intchg-02-lmbd-vi-exchange-rates-role** — policies: —
- **itl-0004-itx-dev-intchg-02-lmbd-mc-role** — policies: —
- **itl-0004-itx-dev-intchg-02-lmbd-vi-role** — policies: —
- **itl-0004-itx-dev-lambda-pg-audit-02-role** — policies: —
- **itl-0004-itx-dev-lmbd-sbsa-preprocess-02-role** — policies: —
- **itl-0004-itx-dev-lmbd-file-load-02-role** — policies: AWSXRayDaemonWriteAccess
- **itl-0004-itx-dev-lmbd-sendmail-02-role** — policies: —
  _(+ 3 more)_

### ec2.amazonaws.com

- **AWSApplicationMigrationConversionServerRole** — policies: AWSApplicationMigrationConversionServerPolicy
- **AWSApplicationMigrationLaunchInstanceWithDrsRole** — policies: AmazonSSMManagedInstanceCore, AWSElasticDisasterRecoveryEc2InstancePolicy
- **AWSApplicationMigrationLaunchInstanceWithSsmRole** — policies: AmazonSSMManagedInstanceCore
- **AWSApplicationMigrationReplicationServerRole** — policies: AWSApplicationMigrationReplicationServerPolicy
- **EC2InstanceProfileForImageBuilder** — policies: AmazonSSMManagedInstanceCore, EC2InstanceProfileForImageBuilder, EC2InstanceProfileForImageBuilderECRContainerBuilds
- **itl-0004-itx-dev-ec2-app-02-role** — policies: CloudWatchAgentServerPolicy, AmazonSSMManagedInstanceCore, AmazonS3FullAccess

### rds.amazonaws.com

- **AWSServiceRoleForRDS** — policies: AmazonRDSServiceRolePolicy
- **itl-0004-itx-dev-rds-app-02-s3-import-role** — policies: —
- **itl-0004-itx-dev-rds-app-02-s3-export-role** — policies: —

### scheduler.amazonaws.com

- **itl-0004-itx-dev-intchg-02-lmbd-vi-exchange-rates-scheduler-role** — policies: —
- **itl-0004-itx-dev-intchg-02-lmbd-mc-exchange-rates-scheduler-role** — policies: —

## Security Groups (key ones)

- **itl-0004-itx-dev-02-sg-vpc-endpoints** (`sg-0dc99291db78d868a`) — 0 ingress rules, 0 egress rules
- **itl-0004-itx-dev-ec2-app-02-sg** (`sg-08b45de2d52e4a925`) — 0 ingress rules, 0 egress rules
- **itl-0004-itx-dev-lambda-pg-audit-02-sg** (`sg-0e1edda6ab1eed290`) — 0 ingress rules, 0 egress rules
- **itl-0004-itx-dev-lmbd-app-02-sg** (`sg-0f93fba3d7978e8d6`) — 0 ingress rules, 0 egress rules
- **itl-0004-itx-dev-lmbd-file-load-02-sg** (`sg-0ad22b09c390c7209`) — 0 ingress rules, 0 egress rules
- **itl-0004-itx-dev-lmbd-sbsa-preprocess-02** (`sg-0b8b779c168840f49`) — 0 ingress rules, 0 egress rules
- **itl-0004-itx-dev-lmbd-sendmail-02-sg** (`sg-08e80112c0389743c`) — 0 ingress rules, 0 egress rules
- **itl-0004-itx-dev-nlb-sftp-02-sg** (`sg-0867d4c2525947cec`) — 0 ingress rules, 0 egress rules
- **itl-0004-itx-dev-rds-app-02-sg** (`sg-07040d29e788f886d`) — 0 ingress rules, 0 egress rules
- **itl-0004-itx-dev-tf-sftp-02-sg** (`sg-077c487b85cadb62e`) — 0 ingress rules, 0 egress rules
- **sg-03ed2a33cb1126201** (`sg-03ed2a33cb1126201`) — 0 ingress rules, 0 egress rules
- **sg-0671b8f0fb5aa27ca** (`sg-0671b8f0fb5aa27ca`) — 0 ingress rules, 0 egress rules
- **sg-07565e1ecf3294bf9** (`sg-07565e1ecf3294bf9`) — 0 ingress rules, 0 egress rules
- **sg-08d415670e927e878** (`sg-08d415670e927e878`) — 0 ingress rules, 0 egress rules
- **sg-0d9bb259e3a608ad0** (`sg-0d9bb259e3a608ad0`) — 0 ingress rules, 0 egress rules
- **sg-0ea832a8a272949c3** (`sg-0ea832a8a272949c3`) — 0 ingress rules, 0 egress rules
