# Interchange-Prod — Security

_Last updated: 2026-07-12 01:20 UTC_

## KMS Keys (Customer Managed)

### alias/itl-0004-itx-prd-kms-london-pan-encrypt-02
- **Key ID:** `1ca62bb5-edb8-4caa-8fda-af42c02bce05`  
- **Usage:** ENCRYPT_DECRYPT  
- **Rotation:** Disabled  
- **Multi-region:** No  
- **Description:** PCI DSS 4.0.1 - CMK ENCRYPT PAN - itl-0004-itx-prod - Rotacion MANUAL

### alias/pci-pan-enc-key
- **Key ID:** `24a02a70-64c6-4426-8b34-a7c11e0f8ce2`  
- **Usage:** ENCRYPT_DECRYPT  
- **Rotation:** Disabled  
- **Multi-region:** No  
- **Description:** PCI DSS 4.0.1 - CMK encriptacion PAN - itl-0004-itx-prd - Rotacion MANUAL

### alias/alias/itl-0004-itx-prd-kms-general-02
- **Key ID:** `371d4f99-41d4-4c91-845d-144e02715fe9`  
- **Usage:** ENCRYPT_DECRYPT  
- **Rotation:** Enabled  
- **Multi-region:** No  
- **Description:** KMS customer managed key

### alias/itl-0004-itx-prd-kms-london-pan-hmac-02
- **Key ID:** `453e020d-a098-4c68-afad-b674007d5740`  
- **Usage:** ENCRYPT_DECRYPT  
- **Rotation:** Disabled  
- **Multi-region:** No  
- **Description:** PCI DSS 4.0.1 - CMK encriptacion PAN - itl-0004-itx-prod - Rotacion MANUAL

### alias/alias/itl-0004-itx-prod-kms-general-01
- **Key ID:** `4f7c2682-b237-46de-9f47-be14a2c6eab5`  
- **Usage:** ENCRYPT_DECRYPT  
- **Rotation:** Enabled  
- **Multi-region:** No  
- **Description:** KMS customer managed key

## IAM Roles by Trusted Service

### lambda.amazonaws.com

- **app-interchange-lambda-fileload-dev-role-14gv3vwo** — policies: AWSLambdaBasicExecutionRole-12d7bf48-16b0-463f-8574-dff534a5d4ba
- **app-interchange-role-lambda-execution-dev** — policies: AWSLambdaBasicExecutionRole
- **app-interchange-role-lambda-execution-prd** — policies: AWSLambdaBasicExecutionRole
- **app-interchange-lambda-sbsa-upload-prd-role** — policies: app-interchange-lambda-upload-prd-role, AWSLambdaBasicExecutionRole
- **app-interchange-lambda-fileload-prod-role** — policies: app-interchange-lambda-fileload-prod-policy, AWSLambdaBasicExecutionRole
- **app-interchange-lambda-send_email-dev-role-n1bqvit1** — policies: AWSLambdaBasicExecutionRole-06969d10-9a60-4f65-8a4e-246a91510b81
- **app-interchange-lambda-fileload-dev-role-wlokah8j** — policies: AWSLambdaBasicExecutionRole-f768eb84-06ff-460c-ba91-f346fed26ddb
- **app-interchange-lambda-fileload-dev-role-wujayiyr** — policies: AWSLambdaBasicExecutionRole-4bfa6fc0-9368-44a6-af78-ceaf4f5087ce
- **app-interchange-lambda-send-email-prod-role** — policies: app-interchange-lambda-send-email-prod-policy, AWSLambdaBasicExecutionRole
- **aws-controltower-ForwardSnsNotificationRole** — policies: AWSLambdaBasicExecutionRole
  _(+ 11 more)_

### ec2.amazonaws.com

- **app-interchange-role-ec2-dev** — policies: CloudWatchAgentServerPolicy, AmazonSSMManagedInstanceCore
- **app-interchange-role-ec2-prd** — policies: CloudWatchAgentServerPolicy, AmazonSSMManagedInstanceCore
- **AWSApplicationMigrationLaunchInstanceWithDrsRole** — policies: AmazonSSMManagedInstanceCore, AWSElasticDisasterRecoveryEc2InstancePolicy
- **AWSApplicationMigrationConversionServerRole** — policies: AWSApplicationMigrationConversionServerPolicy
- **AWSApplicationMigrationLaunchInstanceWithSsmRole** — policies: AmazonSSMManagedInstanceCore
- **AWSApplicationMigrationReplicationServerRole** — policies: AWSApplicationMigrationReplicationServerPolicy
- **EC2InstanceProfileForImageBuilder** — policies: AmazonSSMManagedInstanceCore, EC2InstanceProfileForImageBuilder, EC2InstanceProfileForImageBuilderECRContainerBuilds
- **EC2-SSM-Windows-Role** — policies: itl-0004-itx-prd-london-02-role-secret-pol, CloudWatchAgentServerPolicy, AmazonSSMDirectoryServiceAccess...
- **itl-0004-itx-prd-ec2-app-02-role** — policies: CloudWatchAgentServerPolicy, AmazonSSMManagedInstanceCore
- **ITX_Role_SES** — policies: AmazonSESFullAccess
  _(+ 1 more)_

### ecs-tasks.amazonaws.com

- **jenkins-role-ecs-task-execution-prd** — policies: AmazonECSTaskExecutionRolePolicy
- **jenkins-role-ecs-task-prd** — policies: —

### rds.amazonaws.com

- **app-interchange-role-rds-dev** — policies: —
- **app-interchange-role-export-s3** — policies: app-interchange-role-rds-export-s3
- **app-interchange-role-rds-prd** — policies: —
- **AWSServiceRoleForRDS** — policies: AmazonRDSServiceRolePolicy
- **demo-rds-s3-access-role** — policies: AmazonS3FullAccess
- **itl-0004-itx-prd-rds-app-02-s3-export-role** — policies: —
- **itl-0004-itx-prd-rds-app-02-s3-import-role** — policies: —

## Security Groups (key ones)

- **itl-0004-itx-prd-02-sg-vpc-endpoints** (`sg-01ce57c1fc8749c8b`) — 0 ingress rules, 0 egress rules
- **itl-0004-itx-prd-ec2-app-02-sg** (`sg-0697a3b7e4356aba6`) — 0 ingress rules, 0 egress rules
- **itl-0004-itx-prd-lambda-pg-audit-02-sg** (`sg-0a9badb1aa57f04b6`) — 0 ingress rules, 0 egress rules
- **itl-0004-itx-prd-lmbd-app-02-sg** (`sg-0d132d30a28741e82`) — 0 ingress rules, 0 egress rules
- **itl-0004-itx-prd-lmbd-file-load-02-sg** (`sg-0fde3398d48e6fdb0`) — 0 ingress rules, 0 egress rules
- **itl-0004-itx-prd-lmbd-sbsa-preprocess-02** (`sg-05cbf811c7de9d3f3`) — 0 ingress rules, 0 egress rules
- **itl-0004-itx-prd-lmbd-sendmail-02-sg** (`sg-0cf9b3d2905943753`) — 0 ingress rules, 0 egress rules
- **itl-0004-itx-prd-nlb-sftp-02-sg** (`sg-0a417ccec8040b8f3`) — 0 ingress rules, 0 egress rules
- **itl-0004-itx-prd-rds-app-02-sg** (`sg-0ddb2e33452d2a5ca`) — 0 ingress rules, 0 egress rules
- **itl-0004-itx-prd-sg-quicksight-02** (`sg-00983722a8c6e69af`) — 0 ingress rules, 0 egress rules
- **itl-0004-itx-prd-tf-sftp-02-sg** (`sg-07acdd0a77dde77d8`) — 0 ingress rules, 0 egress rules
- **sg-06619eddecd66bc23** (`sg-06619eddecd66bc23`) — 0 ingress rules, 0 egress rules
- **sg-097a391d184cf49cd** (`sg-097a391d184cf49cd`) — 0 ingress rules, 0 egress rules
- **sg-0becff9d6790cf669** (`sg-0becff9d6790cf669`) — 0 ingress rules, 0 egress rules
