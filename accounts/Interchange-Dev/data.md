# Interchange-Dev — Data Layer

_Last updated: 2026-07-17 14:42 UTC_

## RDS Databases

### itl-0004-itx-dev-rds-app-02-1

**Engine:** aurora-postgresql 16.11  
**Instance class:** db.r5.large  
**Status:** available  
**Endpoint:** `itl-0004-itx-dev-rds-app-02-1.ct2k6yaewech.eu-south-2.rds.amazonaws.com:5432` — use this to connect  
**VPC:** `vpc-0101d2c447b67e9db`  
**Subnet group:** itl-0004-itx-dev-rds-app-02-sng  
**Security Groups:** itl-0004-itx-dev-rds-app-02-sg  
**Multi-AZ:** No  
**Encrypted:** Yes — KMS: alias/alias/itl-0004-itx-dev-kms-general-02  
**Publicly accessible:** No  
**Backup retention:** 7 days  
**Deletion protection:** No

> **To connect:** ensure your resource is in a subnet that can reach the security group `itl-0004-itx-dev-rds-app-02-sg` on port 5432.

## S3 Buckets

**Total:** 20 buckets  
**Encrypted:** 20  
**Versioning enabled:** 12  
**Publicly accessible:** 0

| Bucket | Region | Encryption | Versioning | Public |
|---|---|---|---|---|
| itl-0004-itx-dev-intchg-02-s3-analytics | eu-south-2 | AES256 | Disabled | No |
| itl-0004-itx-dev-intchg-02-s3-archive | eu-south-2 | AES256 | Disabled | No |
| itl-0004-itx-dev-intchg-02-s3-athena | eu-south-2 | AES256 | Disabled | No |
| itl-0004-itx-dev-intchg-02-s3-landing | eu-south-2 | AES256 | Disabled | No |
| itl-0004-itx-dev-intchg-02-s3-operational | eu-south-2 | AES256 | Disabled | No |
| itl-0004-itx-dev-intchg-02-s3-reference | eu-south-2 | AES256 | Disabled | No |
| itl-0004-itx-dev-intchg-02-s3-scheme-fee | eu-south-2 | aws:kms | Enabled | No |
| itl-0004-itx-dev-intchg-02-s3-staging | eu-south-2 | AES256 | Disabled | No |
| itl-0004-itx-dev-s3-configuration-02 | eu-south-2 | aws:kms | Enabled | No |
| itl-0004-itx-dev-s3-devops-02 | eu-south-2 | aws:kms | Enabled | No |
| itl-0004-itx-dev-s3-enriched-02 | eu-south-2 | aws:kms | Enabled | No |
| itl-0004-itx-dev-s3-landing-02 | eu-south-2 | aws:kms | Enabled | No |
| itl-0004-itx-dev-s3-landing-pre-02 | eu-south-2 | aws:kms | Enabled | No |
| itl-0004-itx-dev-s3-log-02 | eu-south-2 | aws:kms | Enabled | No |
| itl-0004-itx-dev-s3-operational-02 | eu-south-2 | aws:kms | Enabled | No |
| itl-0004-itx-dev-s3-raw-02 | eu-south-2 | aws:kms | Enabled | No |
| itl-0004-itx-dev-s3-scheme-fee-02 | eu-south-2 | aws:kms | Enabled | No |
| itl-0004-itx-dev-s3-structured-02 | eu-south-2 | aws:kms | Enabled | No |
| terraform-backend-861276092327-eu-south-2 | eu-south-2 | AES256 | Disabled | No |
| tfstate-eu-south-2-861276092327 | eu-south-2 | AES256 | Enabled | No |

## Secrets Manager

**Total secrets:** 4

| Secret | KMS Key | Rotation | Last Changed |
|---|---|---|---|
| itl-0004-itx-dev-secret-millennial-opensearch-02 | alias/alias/itl-0004-itx-dev-kms-general-02 | No | 2025-10-21 |
| itl-0004-itx-dev-secret-opensearch-02 | alias/alias/itl-0004-itx-dev-kms-general-02 | No | 2025-09-17 |
| itl-0004-itx-dev-secret-rds-app-02 | alias/alias/itl-0004-itx-dev-kms-general-02 | No | 2025-10-21 |
| itl-0004-itx-dev-secret-smtp-app-02 | alias/alias/itl-0004-itx-dev-kms-general-02 | No | 2025-10-21 |
