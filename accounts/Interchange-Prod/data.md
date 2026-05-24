# Interchange-Prod — Data Layer

_Last updated: 2026-05-24 19:32 UTC_

## RDS Databases

### itl-0004-itx-prd-rds-analitycs-02

**Engine:** postgres 17.8  
**Instance class:** db.r5.large  
**Status:** available  
**Endpoint:** `itl-0004-itx-prd-rds-analitycs-02.cb2wsasugzte.eu-south-2.rds.amazonaws.com:5432` — use this to connect  
**VPC:** `vpc-0c6863a32b8db36e0`  
**Subnet group:** itl-0004-itx-prd-rds-analitycs-02-sng  
**Security Groups:** itl-0004-itx-prd-rds-analitycs-02-sg  
**Multi-AZ:** No  
**Encrypted:** Yes — KMS: alias/alias/itl-0004-itx-prd-kms-general-02  
**Publicly accessible:** No  
**Backup retention:** 7 days  
**Deletion protection:** No

> **To connect:** ensure your resource is in a subnet that can reach the security group `itl-0004-itx-prd-rds-analitycs-02-sg` on port 5432.

### itl-0004-itx-prd-rds-app-02-1

**Engine:** aurora-postgresql 16.11  
**Instance class:** db.r5.2xlarge  
**Status:** available  
**Endpoint:** `itl-0004-itx-prd-rds-app-02-1.cb2wsasugzte.eu-south-2.rds.amazonaws.com:5432` — use this to connect  
**VPC:** `vpc-0c6863a32b8db36e0`  
**Subnet group:** itl-0004-itx-prd-rds-app-02-sng  
**Security Groups:** itl-0004-itx-prd-rds-app-02-sg  
**Multi-AZ:** No  
**Encrypted:** Yes — KMS: alias/alias/itl-0004-itx-prd-kms-general-02  
**Publicly accessible:** No  
**Backup retention:** 7 days  
**Deletion protection:** No

> **To connect:** ensure your resource is in a subnet that can reach the security group `itl-0004-itx-prd-rds-app-02-sg` on port 5432.

## S3 Buckets

**Total:** 16 buckets  
**Encrypted:** 16  
**Versioning enabled:** 12  
**Publicly accessible:** 0

| Bucket | Region | Encryption | Versioning | Public |
|---|---|---|---|---|
| dms-assessment-run-2025-11-25-21-26-44 | eu-south-2 | AES256 | Enabled | No |
| eu-south-2-scan-interchange-logs | eu-south-2 | AES256 | Disabled | No |
| itl-0004-itx-prd-s3-configuration-02 | eu-south-2 | aws:kms | Enabled | No |
| itl-0004-itx-prd-s3-devops-02 | eu-south-2 | aws:kms | Enabled | No |
| itl-0004-itx-prd-s3-enriched-02 | eu-south-2 | aws:kms | Enabled | No |
| itl-0004-itx-prd-s3-landing-02 | eu-south-2 | aws:kms | Enabled | No |
| itl-0004-itx-prd-s3-landing-pre-02 | eu-south-2 | aws:kms | Enabled | No |
| itl-0004-itx-prd-s3-log-02 | eu-south-2 | aws:kms | Enabled | No |
| itl-0004-itx-prd-s3-operational-02 | eu-south-2 | aws:kms | Enabled | No |
| itl-0004-itx-prd-s3-raw-02 | eu-south-2 | aws:kms | Enabled | No |
| itl-0004-itx-prd-s3-scheme-fee-02 | eu-south-2 | aws:kms | Enabled | No |
| itl-0004-itx-prd-s3-structured-02 | eu-south-2 | aws:kms | Enabled | No |
| itx-copy-testing | eu-south-2 | AES256 | Disabled | No |
| terraform-backend-818835242461 | eu-south-2 | AES256 | Disabled | No |
| terraform-backend-818835242461-eu-south-2 | eu-south-2 | AES256 | Disabled | No |
| tfstate-eu-south-2-818835242461 | eu-south-2 | AES256 | Enabled | No |

## Secrets Manager

**Total secrets:** 17

| Secret | KMS Key | Rotation | Last Changed |
|---|---|---|---|
| itl-0004-itx-prd-secret-dashboard-ext-prd-02 | alias/alias/itl-0004-itx-prd-kms-general-02 | No | 2026-01-14 |
| itl-0004-itx-prd-secret-denver-02 | alias/alias/itl-0004-itx-prd-kms-general-02 | No | 2026-01-14 |
| itl-0004-itx-prd-secret-denver-dev-02 | alias/alias/itl-0004-itx-prd-kms-general-02 | No | 2026-01-14 |
| itl-0004-itx-prd-secret-denver-qa-02 | alias/alias/itl-0004-itx-prd-kms-general-02 | No | 2026-01-14 |
| itl-0004-itx-prd-secret-london-02 | alias/alias/itl-0004-itx-prd-kms-general-02 | No | 2026-01-14 |
| itl-0004-itx-prd-secret-millennial-opensearch-02 | alias/alias/itl-0004-itx-prd-kms-general-02 | No | 2025-10-18 |
| itl-0004-itx-prd-secret-opensearch-02 | alias/alias/itl-0004-itx-prd-kms-general-02 | No | 2025-10-16 |
| itl-0004-itx-prd-secret-portal-replication-02 | alias/alias/itl-0004-itx-prd-kms-general-02 | No | 2026-01-14 |
| itl-0004-itx-prd-secret-rds-analitycs-02 | alias/alias/itl-0004-itx-prd-kms-general-02 | No | 2025-10-27 |
| itl-0004-itx-prd-secret-rds-analitycs-replication-02 | alias/alias/itl-0004-itx-prd-kms-general-02 | No | 2026-01-14 |
| itl-0004-itx-prd-secret-rds-app-02 | alias/alias/itl-0004-itx-prd-kms-general-02 | No | 2025-10-25 |
| itl-0004-itx-prd-secret-rds-app-agonzalez-02 | alias/alias/itl-0004-itx-prd-kms-general-02 | No | 2025-10-19 |
| itl-0004-itx-prd-secret-rds-app-dev-02 | alias/alias/itl-0004-itx-prd-kms-general-02 | No | 2026-01-14 |
| itl-0004-itx-prd-secret-rds-app-noti-02 | alias/alias/itl-0004-itx-prd-kms-general-02 | No | 2025-10-19 |
| itl-0004-itx-prd-secret-rds-app-replication-02 | alias/alias/itl-0004-itx-prd-kms-general-02 | No | 2026-01-14 |
| itl-0004-itx-prd-secret-smtp-app-02 | alias/alias/itl-0004-itx-prd-kms-general-02 | No | 2026-01-14 |
| itl-0004-itx-prd-secret-sql-dmk-hash-passwords-02 | alias/alias/itl-0004-itx-prd-kms-general-02 | No | 2026-03-25 |
