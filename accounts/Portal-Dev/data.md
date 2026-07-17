# Portal-Dev — Data Layer

_Last updated: 2026-07-17 14:42 UTC_

## RDS Databases

### itl-0003-portal-dev-rds-apps-03-instance-1

**Engine:** aurora-postgresql 16.11  
**Instance class:** db.serverless  
**Status:** available  
**Endpoint:** `itl-0003-portal-dev-rds-apps-03-instance-1.cls68qmcosaf.eu-south-2.rds.amazonaws.com:5432` — use this to connect  
**VPC:** `vpc-0fbd191d169cc9efb`  
**Subnet group:** itl-0003-portal-dev-rds-apps-03-sng  
**Security Groups:** itl-0003-portal-dev-rds-apps-03-sg  
**Multi-AZ:** No  
**Encrypted:** Yes — KMS: alias/alias/itl-0003-portal-dev-kms-general-03  
**Publicly accessible:** No  
**Backup retention:** 7 days  
**Deletion protection:** No

> **To connect:** ensure your resource is in a subnet that can reach the security group `itl-0003-portal-dev-rds-apps-03-sg` on port 5432.

## S3 Buckets

**Total:** 15 buckets  
**Encrypted:** 15  
**Versioning enabled:** 8  
**Publicly accessible:** 1  ⚠️

| Bucket | Region | Encryption | Versioning | Public |
|---|---|---|---|---|
| aws-athena-query-results-eu-south-2-891376942769 | eu-south-2 | AES256 | Disabled | No |
| bucketlogss3intelica | us-east-1 | AES256 | Disabled | No |
| itl-0003-portal-dev-s3-airflow-logs-03 | eu-south-2 | aws:kms | Disabled | No |
| itl-0003-portal-dev-s3-api-fee-filesharing-01 | us-east-1 | AES256 | Enabled | No |
| itl-0003-portal-dev-s3-api-fee-filesharing-03 | eu-south-2 | aws:kms | Enabled | No |
| itl-0003-portal-dev-s3-api-security-documents-01 | us-east-1 | AES256 | Enabled | No |
| itl-0003-portal-dev-s3-api-security-documents-03 | eu-south-2 | aws:kms | Enabled | No |
| itl-0003-portal-dev-s3-appsmith-backup-03 | us-east-1 | AES256 | Disabled | No |
| itl-0003-portal-dev-s3-general-01 | us-east-1 | AES256 | Enabled | No |
| itl-0003-portal-dev-s3-general-03 | eu-south-2 | aws:kms | Enabled | No |
| itl-0003-portal-dev-s3-pub-templates-03 | eu-south-2 | AES256 | Disabled | ⚠️ Yes |
| itl-0003-portal-prd-s3-rds-backup-denver-02 | eu-south-2 | AES256 | Disabled | No |
| itl-0009-prtlgy-dev-s3-general-01 | us-east-1 | AES256 | Disabled | No |
| terraform-backend-891376942769 | us-east-1 | AES256 | Enabled | No |
| tfstate-eu-south-2-891376942769 | eu-south-2 | AES256 | Enabled | No |

## Secrets Manager

**Total secrets:** 18

| Secret | KMS Key | Rotation | Last Changed |
|---|---|---|---|
| itl-0003-portal-dev-fsx-ad-credentials | _none_ | No | 2025-12-15 |
| itl-0003-portal-dev-secret-airflow-settings-03 | _none_ | No | 2026-06-25 |
| itl-0003-portal-dev-secret-api-appsmith | _none_ | No | 2025-11-10 |
| itl-0003-portal-dev-secret-api-appsmith-03 | _none_ | No | 2026-02-03 |
| itl-0003-portal-dev-secret-clickhouse-settings-03 | _none_ | No | 2026-01-14 |
| itl-0003-portal-dev-secret-connection-strings-03 | _none_ | No | 2026-04-06 |
| itl-0003-portal-dev-secret-email-settings-03 | _none_ | No | 2026-06-22 |
| itl-0003-portal-dev-secret-external-credentials-03 | _none_ | No | 2026-06-05 |
| itl-0003-portal-dev-secret-internal-authentication-03 | _none_ | No | 2026-05-14 |
| itl-0003-portal-dev-secret-jwt-settings-03 | _none_ | No | 2025-11-13 |
| itl-0003-portal-dev-secret-rsa-settings-03 | _none_ | No | 2025-11-13 |
| itl-0003-portal-dev-secret-samba-denver-03 | _none_ | No | 2025-10-15 |
| itl-0003-portal-dev-secret-samba-settings-03 | _none_ | No | 2025-11-13 |
| itl-0003-portal-dev-secret-samba-vienna-03 | _none_ | No | 2025-10-10 |
| itl-0003-portal-dev-secret-sftp-settings-03 | _none_ | No | 2025-11-13 |
| itl-0003-portal-dev-secret-sharepoint-settings-03 | _none_ | No | 2026-01-27 |
| itl-0003-portal-dev-secret-sql-dmk-hash-passwords-03 | _none_ | No | 2026-03-25 |
| rds!cluster-2d72fbdb-30f4-42b9-abf9-9cb8fdbe5a52 | _none_ | ✅ Yes | 2026-07-09 |
