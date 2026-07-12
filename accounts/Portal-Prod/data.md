# Portal-Prod — Data Layer

_Last updated: 2026-07-12 01:20 UTC_

## RDS Databases

### itl-0003-portal-prd-rds-apps-02-instance-1

**Engine:** aurora-postgresql 16.11  
**Instance class:** db.serverless  
**Status:** available  
**Endpoint:** `itl-0003-portal-prd-rds-apps-02-instance-1.cp22y2qkmvn2.eu-south-2.rds.amazonaws.com:5432` — use this to connect  
**VPC:** `vpc-0626d66632373c892`  
**Subnet group:** itl-0003-portal-prd-rds-apps-02-sng  
**Security Groups:** itl-0003-portal-prd-rds-apps-02-sg  
**Multi-AZ:** No  
**Encrypted:** Yes — KMS: alias/alias/itl-0003-portal-prd-kms-general-02  
**Publicly accessible:** No  
**Backup retention:** 7 days  
**Deletion protection:** No

> **To connect:** ensure your resource is in a subnet that can reach the security group `itl-0003-portal-prd-rds-apps-02-sg` on port 5432.

## S3 Buckets

**Total:** 25 buckets  
**Encrypted:** 25  
**Versioning enabled:** 13  
**Publicly accessible:** 1  ⚠️

| Bucket | Region | Encryption | Versioning | Public |
|---|---|---|---|---|
| aws-quicksetup-patchpolicy-610944808410-1yqvz | us-east-1 | AES256 | Enabled | No |
| aws-quicksetup-patchpolicy-access-log-610944808410-a0db-1yqvz | us-east-1 | AES256 | Enabled | No |
| fortisiemtmp | eu-south-2 | AES256 | Disabled | No |
| infrastructurestack-artifactbucket7410c9ef-7lkg7u9tttyj | us-east-1 | AES256 | Disabled | No |
| itl-0003-portal-prd-nlb-logging-01 | us-east-1 | AES256 | Disabled | No |
| itl-0003-portal-prd-s3-airflow-logs-02 | eu-south-2 | aws:kms | Disabled | No |
| itl-0003-portal-prd-s3-api-fee-filesharing-02 | eu-south-2 | aws:kms | Enabled | No |
| itl-0003-portal-prd-s3-api-security-documents-02 | eu-south-2 | aws:kms | Enabled | No |
| itl-0003-portal-prd-s3-cuotas-02 | eu-south-2 | aws:kms | Disabled | No |
| itl-0003-portal-prd-s3-denver-02 | eu-south-2 | aws:kms | Disabled | No |
| itl-0003-portal-prd-s3-elb-log-02 | eu-south-2 | AES256 | Disabled | No |
| itl-0003-portal-prd-s3-general-02 | eu-south-2 | aws:kms | Enabled | No |
| itl-0003-portal-prd-s3-infrastructure-backups-general-02 | eu-south-2 | aws:kms | Disabled | No |
| itl-0003-portal-prd-s3-london-02 | eu-south-2 | aws:kms | Enabled | No |
| itl-0003-portal-prd-s3-pub-templates-02 | eu-south-2 | AES256 | Disabled | ⚠️ Yes |
| itl-0003-portal-prd-s3-vienna-02 | eu-south-2 | aws:kms | Disabled | No |
| itl-alb-logs | us-east-1 | AES256 | Enabled | No |
| itl-aws-cloudtrail-logs | us-east-1 | AES256 | Enabled | No |
| itl-aws-elb-log-replica | us-east-1 | AES256 | Enabled | No |
| itl-cuotas | us-east-1 | AES256 | Disabled | No |
| s3-denver | us-east-1 | AES256 | Disabled | No |
| s3-itl-london | us-east-1 | AES256 | Enabled | No |
| terraform-backend-610944808410 | us-east-1 | AES256 | Enabled | No |
| terraform-tf01 | us-east-1 | AES256 | Enabled | No |
| tfstate-eu-south-2-610944808410 | eu-south-2 | AES256 | Enabled | No |

## Secrets Manager

**Total secrets:** 16

| Secret | KMS Key | Rotation | Last Changed |
|---|---|---|---|
| aws-datasync!loc-04223d7f0456f67d3 | _none_ | No | 2025-12-17 |
| aws-datasync!loc-0aaa671a2dff08448 | _none_ | No | 2025-12-17 |
| itl-0003-portal-prd-fsx-ad-credentials | _none_ | No | 2026-01-20 |
| itl-0003-portal-prd-secret-airflow-settings-02 | _none_ | No | 2026-07-06 |
| itl-0003-portal-prd-secret-api-appsmith-02 | _none_ | No | 2026-03-10 |
| itl-0003-portal-prd-secret-connection-strings-02 | _none_ | No | 2026-01-26 |
| itl-0003-portal-prd-secret-email-settings-02 | _none_ | No | 2026-06-22 |
| itl-0003-portal-prd-secret-external-credentials-02 | _none_ | No | 2026-06-05 |
| itl-0003-portal-prd-secret-internal-authentication-02 | _none_ | No | 2026-05-22 |
| itl-0003-portal-prd-secret-jwt-settings-02 | _none_ | No | 2025-11-13 |
| itl-0003-portal-prd-secret-rsa-settings-02 | _none_ | No | 2025-11-13 |
| itl-0003-portal-prd-secret-samba-denver-02 | _none_ | No | 2025-11-13 |
| itl-0003-portal-prd-secret-samba-settings-02 | _none_ | No | 2025-11-15 |
| itl-0003-portal-prd-secret-samba-vienna-02 | _none_ | No | 2025-11-13 |
| itl-0003-portal-prd-secret-sftp-settings-02 | _none_ | No | 2025-11-15 |
| rds!cluster-ef7cb42a-ff9d-412f-9151-46b85d2fdc35 | _none_ | ✅ Yes | 2026-07-08 |
