# Analytics-Dev — Data Layer

_Last updated: 2026-07-17 14:42 UTC_

## RDS Databases

### itl-0005-ana-dev-rds-dbaf-02

**Engine:** postgres 16.13  
**Instance class:** db.t3.micro  
**Status:** available  
**Endpoint:** `itl-0005-ana-dev-rds-dbaf-02.clukawgwmnvf.eu-south-2.rds.amazonaws.com:5432` — use this to connect  
**VPC:** `vpc-092dc05179287e08a`  
**Subnet group:** itl-0005-ana-dev-rds-dbaf-02-dbsng  
**Security Groups:** itl-0005-ana-dev-rds-dbaf-02-sg  
**Multi-AZ:** No  
**Encrypted:** No — KMS: _none_  
**Publicly accessible:** No  
**Backup retention:** 0 days  
**Deletion protection:** Yes

> **To connect:** ensure your resource is in a subnet that can reach the security group `itl-0005-ana-dev-rds-dbaf-02-sg` on port 5432.

## S3 Buckets

**Total:** 8 buckets  
**Encrypted:** 8  
**Versioning enabled:** 6  
**Publicly accessible:** 1  ⚠️

| Bucket | Region | Encryption | Versioning | Public |
|---|---|---|---|---|
| itl-0005-ana-dev-pub-s3-static-02 | eu-south-2 | AES256 | Disabled | ⚠️ Yes |
| itl-0005-ana-dev-s3-airflow-logs-02 | eu-south-2 | AES256 | Enabled | No |
| itl-0005-ana-dev-s3-incontrol-02 | eu-south-2 | AES256 | Enabled | No |
| itl-0005-ana-dev-s3-interchange-02 | eu-south-2 | AES256 | Enabled | No |
| itl-0005-ana-dev-s3-reports-02 | eu-south-2 | AES256 | Enabled | No |
| itl-0005-ana-dev-s3-static-02 | eu-south-2 | AES256 | Suspended | No |
| terraform-backend-221082197632 | us-east-1 | AES256 | Enabled | No |
| tfstate-eu-south-2-221082197632 | eu-south-2 | AES256 | Enabled | No |
