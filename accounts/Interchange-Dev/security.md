# Interchange-Dev — Security

_Last updated: 2026-07-17 14:42 UTC_

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
- **itl-0004-itx-dev-intchg-02-lmbd-mc-role** — policies: —
- **itl-0004-itx-dev-intchg-02-lmbd-vi-exchange-rates-role** — policies: —
- **itl-0004-itx-dev-intchg-02-lmbd-vi-role** — policies: —
- **itl-0004-itx-dev-lmbd-app-02-role** — policies: —
- **itl-0004-itx-dev-lambda-pg-audit-02-role** — policies: —
- **itl-0004-itx-dev-lmbd-file-load-02-role** — policies: AWSXRayDaemonWriteAccess
- **itl-0004-itx-dev-lmbd-sbsa-preprocess-02-role** — policies: —
  _(+ 3 more)_

### ec2.amazonaws.com

- **AWSApplicationMigrationConversionServerRole** — policies: AWSApplicationMigrationConversionServerPolicy
- **AWSApplicationMigrationLaunchInstanceWithSsmRole** — policies: AmazonSSMManagedInstanceCore
- **AWSApplicationMigrationLaunchInstanceWithDrsRole** — policies: AmazonSSMManagedInstanceCore, AWSElasticDisasterRecoveryEc2InstancePolicy
- **AWSApplicationMigrationReplicationServerRole** — policies: AWSApplicationMigrationReplicationServerPolicy
- **EC2InstanceProfileForImageBuilder** — policies: AmazonSSMManagedInstanceCore, EC2InstanceProfileForImageBuilder, EC2InstanceProfileForImageBuilderECRContainerBuilds
- **itl-0004-itx-dev-ec2-app-02-role** — policies: CloudWatchAgentServerPolicy, AmazonSSMManagedInstanceCore, AmazonS3FullAccess

### rds.amazonaws.com

- **AWSServiceRoleForRDS** — policies: AmazonRDSServiceRolePolicy
- **itl-0004-itx-dev-rds-app-02-s3-export-role** — policies: —
- **itl-0004-itx-dev-rds-app-02-s3-import-role** — policies: —

### scheduler.amazonaws.com

- **itl-0004-itx-dev-intchg-02-lmbd-mc-exchange-rates-scheduler-role** — policies: —
- **itl-0004-itx-dev-intchg-02-lmbd-vi-exchange-rates-scheduler-role** — policies: —

## Security Groups (key ones)

- **itl-0004-itx-dev-02-sg-vpc-endpoints** (`sg-0dc99291db78d868a`) — 1 inbound rules, 0 outbound rules
    - IN  TCP port 443 ← sg:sg-0d9bb259e3a608ad0, sg:sg-0671b8f0fb5aa27ca, sg:sg-07565e1ecf3294bf9, sg:sg-0ea832a8a272949c3, sg:sg-08b45de2d52e4a925
- **itl-0004-itx-dev-ec2-app-02-sg** (`sg-08b45de2d52e4a925`) — 2 inbound rules, 2 outbound rules
    - IN  ALL all ports ← 10.0.4.0/24, 100.0.4.38/32, 10.0.3.100/32, sg:sg-0aa6d55bd394447f6
    - IN  TCP port 22 ← 0.0.0.0/0
    - OUT ALL all ports ← 0.0.0.0/0
    - OUT TCP port 443 ← sg:sg-0dc99291db78d868a
- **itl-0004-itx-dev-lambda-pg-audit-02-sg** (`sg-0e1edda6ab1eed290`) — 0 inbound rules, 3 outbound rules
    - OUT UDP port 53 ← 10.14.0.0/16
    - OUT TCP port 53 ← 10.14.0.0/16
    - OUT TCP port 443 ← pl:pl-64a5400d
- **itl-0004-itx-dev-lmbd-app-02-sg** (`sg-0f93fba3d7978e8d6`) — 0 inbound rules, 1 outbound rules
    - OUT ALL all ports ← 10.14.0.0/16
- **itl-0004-itx-dev-lmbd-file-load-02-sg** (`sg-0ad22b09c390c7209`) — 0 inbound rules, 1 outbound rules
    - OUT ALL all ports ← 10.14.0.0/16
- **itl-0004-itx-dev-lmbd-sbsa-preprocess-02** (`sg-0b8b779c168840f49`) — 0 inbound rules, 1 outbound rules
    - OUT ALL all ports ← 0.0.0.0/0
- **itl-0004-itx-dev-lmbd-sendmail-02-sg** (`sg-08e80112c0389743c`) — 0 inbound rules, 1 outbound rules
    - OUT ALL all ports ← 10.14.0.0/16
- **itl-0004-itx-dev-nlb-sftp-02-sg** (`sg-0867d4c2525947cec`) — 1 inbound rules, 1 outbound rules
    - IN  TCP port 2222 ← 0.0.0.0/0
    - OUT ALL all ports ← 0.0.0.0/0
- **itl-0004-itx-dev-rds-app-02-sg** (`sg-07040d29e788f886d`) — 1 inbound rules, 1 outbound rules
    - IN  TCP port 5432 ← 10.0.3.100/32, 172.8.3.51/32, 172.2.3.211/32, sg:sg-0ad22b09c390c7209, sg:sg-08b45de2d52e4a925, sg:sg-097a391d184cf49cd, sg:sg-0aa6d55bd394447f6, sg:sg-0922640d2a80f5742
    - OUT ALL all ports ← 0.0.0.0/0
- **itl-0004-itx-dev-tf-sftp-02-sg** (`sg-077c487b85cadb62e`) — 1 inbound rules, 0 outbound rules
    - IN  TCP port 22 ← 0.0.0.0/0
- **sg-03ed2a33cb1126201** (`sg-03ed2a33cb1126201`) — 1 inbound rules, 1 outbound rules
    - IN  ALL all ports ← sg:sg-03ed2a33cb1126201
    - OUT ALL all ports ← 10.14.0.0/16, sg:sg-03ed2a33cb1126201, pl:pl-64a5400d, pl:pl-68a74201
- **sg-0671b8f0fb5aa27ca** (`sg-0671b8f0fb5aa27ca`) — 1 inbound rules, 2 outbound rules
    - IN  TCP port 443 ← 10.14.0.0/16
    - OUT ALL all ports ← 10.14.0.0/16
    - OUT TCP port 443 ← pl:pl-64a5400d, pl:pl-68a74201
- **sg-07565e1ecf3294bf9** (`sg-07565e1ecf3294bf9`) — 1 inbound rules, 2 outbound rules
    - IN  TCP port 443 ← 10.14.0.0/16
    - OUT TCP port 443 ← 0.0.0.0/0
    - OUT TCP port 50100 ← 0.0.0.0/0
- **sg-08d415670e927e878** (`sg-08d415670e927e878`) — 0 inbound rules, 0 outbound rules
- **sg-0d9bb259e3a608ad0** (`sg-0d9bb259e3a608ad0`) — 1 inbound rules, 2 outbound rules
    - IN  TCP port 443 ← 10.14.0.0/16
    - OUT ALL all ports ← 10.14.0.0/16
    - OUT TCP port 443 ← pl:pl-64a5400d, pl:pl-68a74201
- **sg-0ea832a8a272949c3** (`sg-0ea832a8a272949c3`) — 1 inbound rules, 1 outbound rules
    - IN  TCP port 443 ← 10.14.0.0/16
    - OUT TCP port 443 ← 0.0.0.0/0
