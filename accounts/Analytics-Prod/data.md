# Analytics-Prod — Data Layer

_Last updated: 2026-05-24 19:32 UTC_

## RDS Databases

### itl-0005-ana-prd-rds-dbaf-02

**Engine:** postgres 16.8  
**Instance class:** db.t3.micro  
**Status:** available  
**Endpoint:** `itl-0005-ana-prd-rds-dbaf-02.clkeeaayq0n0.eu-south-2.rds.amazonaws.com:5432` — use this to connect  
**VPC:** `vpc-0008aceba2432ab91`  
**Subnet group:** itl-0005-ana-prd-rds-dbaf-02-dbsng  
**Security Groups:** itl-0005-ana-prd-rds-dbaf-02-sg  
**Multi-AZ:** No  
**Encrypted:** No — KMS: _none_  
**Publicly accessible:** No  
**Backup retention:** 0 days  
**Deletion protection:** Yes

> **To connect:** ensure your resource is in a subnet that can reach the security group `itl-0005-ana-prd-rds-dbaf-02-sg` on port 5432.

## S3 Buckets

**Total:** 8 buckets  
**Encrypted:** 8  
**Versioning enabled:** 6  
**Publicly accessible:** 0

| Bucket | Region | Encryption | Versioning | Public |
|---|---|---|---|---|
| eu-south-2-scan-analytics-logs | eu-south-2 | AES256 | Disabled | No |
| itl-0005-ana-prd-s3-airflow-logs-02 | eu-south-2 | AES256 | Enabled | No |
| itl-0005-ana-prd-s3-incontrol-02 | eu-south-2 | AES256 | Enabled | No |
| itl-0005-ana-prd-s3-interchange-02 | eu-south-2 | AES256 | Enabled | No |
| itl-0005-ana-prd-s3-reports-02 | eu-south-2 | AES256 | Enabled | No |
| itl-0005-ana-prd-s3-static-02 | eu-south-2 | AES256 | Suspended | No |
| terraform-backend-831926623233 | us-east-1 | AES256 | Enabled | No |
| tfstate-eu-south-2-831926623233 | eu-south-2 | AES256 | Enabled | No |
