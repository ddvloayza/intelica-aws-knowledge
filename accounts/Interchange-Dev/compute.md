# Interchange-Dev — Compute

_Last updated: 2026-07-12 01:20 UTC_

## Lambda Functions

| Name | Runtime | Memory | Timeout | VPC | SGs |
|---|---|---|---|---|---|
| aws-controltower-NotificationForwarder | python3.13 | 128MB | 60s | **No VPC** | — |
| itl-0004-itx-dev-intchg-02-lmbd-archive-file | python3.11 | 8192MB | 240s | Yes | itl-0004-itx-dev-intchg-02-lmbd-vi-sg |
| itl-0004-itx-dev-intchg-02-lmbd-mc-clean | python3.11 | 10240MB | 600s | **No VPC** | — |
| itl-0004-itx-dev-intchg-02-lmbd-mc-exchange-rates | python3.11 | 512MB | 750s | Yes | itl-0004-itx-dev-intchg-02-lmbd-mc-exchange-rates-sg |
| itl-0004-itx-dev-intchg-02-lmbd-mc-extract | python3.11 | 10240MB | 900s | **No VPC** | — |
| itl-0004-itx-dev-intchg-02-lmbd-mc-iar | python3.11 | 1024MB | 300s | **No VPC** | — |
| itl-0004-itx-dev-intchg-02-lmbd-mc-interpreter | python3.11 | 10240MB | 900s | **No VPC** | — |
| itl-0004-itx-dev-intchg-02-lmbd-mc-store | python3.11 | 10240MB | 900s | **No VPC** | — |
| itl-0004-itx-dev-intchg-02-lmbd-mc-transform | python3.11 | 10000MB | 400s | **No VPC** | — |
| itl-0004-itx-dev-intchg-02-lmbd-router | python3.11 | 8192MB | 240s | Yes | itl-0004-itx-dev-intchg-02-lmbd-vi-sg |
| itl-0004-itx-dev-intchg-02-lmbd-test-1 | python3.11 | 512MB | 60s | Yes | itl-0004-itx-dev-intchg-02-lmbd-vi-sg |
| itl-0004-itx-dev-intchg-02-lmbd-test-2 | python3.11 | 512MB | 60s | Yes | itl-0004-itx-dev-intchg-02-lmbd-mc-sg |
| itl-0004-itx-dev-intchg-02-lmbd-unzip | python3.11 | 1024MB | 240s | Yes | itl-0004-itx-dev-intchg-02-lmbd-vi-sg |
| itl-0004-itx-dev-intchg-02-lmbd-vi-ardef | python3.11 | 4096MB | 300s | **No VPC** | — |
| itl-0004-itx-dev-intchg-02-lmbd-vi-clean | python3.11 | 10240MB | 900s | Yes | itl-0004-itx-dev-intchg-02-lmbd-vi-sg |
| itl-0004-itx-dev-intchg-02-lmbd-vi-exchange-rates |  | 2048MB | 750s | Yes | itl-0004-itx-dev-intchg-02-lmbd-vi-exchange-rates-sg |
| itl-0004-itx-dev-intchg-02-lmbd-vi-extract | python3.11 | 10240MB | 900s | Yes | itl-0004-itx-dev-intchg-02-lmbd-vi-sg |
| itl-0004-itx-dev-intchg-02-lmbd-vi-store | python3.11 | 10240MB | 900s | Yes | itl-0004-itx-dev-intchg-02-lmbd-vi-sg |
| itl-0004-itx-dev-intchg-02-lmbd-vi-transform | python3.11 | 10240MB | 900s | Yes | itl-0004-itx-dev-intchg-02-lmbd-vi-sg |
| itl-0004-itx-dev-lambda-pg-audit-02 | python3.12 | 128MB | 60s | Yes | itl-0004-itx-dev-lambda-pg-audit-02-sg |
| itl-0004-itx-dev-lmbd-app-02 | python3.10 | 128MB | 3s | Yes | itl-0004-itx-dev-lmbd-app-02-sg |
| itl-0004-itx-dev-lmbd-file-load-02 | python3.10 | 128MB | 3s | Yes | itl-0004-itx-dev-lmbd-file-load-02-sg |
| itl-0004-itx-dev-lmbd-sbsa-preprocess-02 | python3.10 | 512MB | 300s | Yes | itl-0004-itx-dev-lmbd-sbsa-preprocess-02 |
| itl-0004-itx-dev-lmbd-sendmail-02 | python3.10 | 128MB | 3s | Yes | itl-0004-itx-dev-lmbd-sendmail-02-sg |
| itl-0004-itx-dev-testfunction | python3.14 | 128MB | 3s | **No VPC** | — |
| itl-portal-dev-kms-pgcrypto | python3.13 | 128MB | 3s | **No VPC** | — |

### Lambda VPC Details

**itl-0004-itx-dev-intchg-02-lmbd-unzip**
- Runtime: python3.11 | Memory: 1024MB | Timeout: 240s
- Subnets: itl-0004-itx-dev-private-2b, itl-0004-itx-dev-private-2a
- Execution role: `itl-0004-itx-dev-intchg-02-lmbd-vi-role`
- KMS: _none_
- Environment variable keys: EXTRACT_CHUNK_SIZE_MB, S3_BUCKET_LANDING, S3_BUCKET_ARCHIVE, DYNAMODB_TABLE_FILE_PATTERN

**itl-0004-itx-dev-lmbd-sendmail-02**
- Runtime: python3.10 | Memory: 128MB | Timeout: 3s
- Subnets: itl-0004-itx-dev-private-2b, itl-0004-itx-dev-private-2a
- Execution role: `itl-0004-itx-dev-lmbd-sendmail-02-role`
- KMS: alias/alias/itl-0004-itx-dev-kms-general-02
- Environment variable keys: SMTP_SECRET_ARN

**itl-0004-itx-dev-intchg-02-lmbd-vi-transform**
- Runtime: python3.11 | Memory: 10240MB | Timeout: 900s
- Subnets: itl-0004-itx-dev-private-2b, itl-0004-itx-dev-private-2a
- Execution role: `itl-0004-itx-dev-intchg-02-lmbd-vi-role`
- KMS: alias/alias/itl-0004-itx-dev-kms-general-02
- Environment variable keys: CHUNK_SIZE_MB, S3_BUCKET_STAGING, S3_BUCKET_LANDING, FLUSH_BATCH_SIZE

**itl-0004-itx-dev-intchg-02-lmbd-mc-exchange-rates**
- Runtime: python3.11 | Memory: 512MB | Timeout: 750s
- Subnets: itl-0004-itx-dev-private-2b, itl-0004-itx-dev-private-2a
- Execution role: `itl-0004-itx-dev-intchg-02-lmbd-mc-exchange-rates-role`
- KMS: _none_
- Environment variable keys: —

**itl-0004-itx-dev-intchg-02-lmbd-vi-extract**
- Runtime: python3.11 | Memory: 10240MB | Timeout: 900s
- Subnets: itl-0004-itx-dev-private-2b, itl-0004-itx-dev-private-2a
- Execution role: `itl-0004-itx-dev-intchg-02-lmbd-vi-role`
- KMS: alias/alias/itl-0004-itx-dev-kms-general-02
- Environment variable keys: DYNAMODB_FIELD_DEFINITION, S3_BUCKET_STAGING, S3_BUCKET_LANDING, EXTRACT_CHUNK_SIZE

**itl-0004-itx-dev-lambda-pg-audit-02**
- Runtime: python3.12 | Memory: 128MB | Timeout: 60s
- Subnets: itl-0004-itx-dev-restricted-2b, itl-0004-itx-dev-restricted-2a
- Execution role: `itl-0004-itx-dev-lambda-pg-audit-02-role`
- KMS: _none_
- Environment variable keys: ACCOUNT_ID, PREFIX, LOG_GROUP, BUCKET_NAME

**itl-0004-itx-dev-intchg-02-lmbd-test-1**
- Runtime: python3.11 | Memory: 512MB | Timeout: 60s
- Subnets: itl-0004-itx-dev-private-2b, itl-0004-itx-dev-private-2a
- Execution role: `itl-0004-itx-dev-intchg-02-lmbd-vi-role`
- KMS: _none_
- Environment variable keys: —

**itl-0004-itx-dev-intchg-02-lmbd-router**
- Runtime: python3.11 | Memory: 8192MB | Timeout: 240s
- Subnets: itl-0004-itx-dev-private-2b, itl-0004-itx-dev-private-2a
- Execution role: `itl-0004-itx-dev-intchg-02-lmbd-vi-role`
- KMS: alias/alias/itl-0004-itx-dev-kms-general-02
- Environment variable keys: UNZIP_FUNCTION_NAME, VISA_ARDEF_FUNCTION_NAME, STEP_FUNCTION_ARN, STEP_FUNCTION_MC_ARN, S3_BUCKET_STAGING, STEP_FUNCTION_VI_ARN, MASTERCARD_IAR_FUNCTION_NAME, DYNAMODB_TABLE_FILE_CONTROL, S3_BUCKET_LANDING, DYNAMODB_TABLE_FILE_PATTERN

**itl-0004-itx-dev-intchg-02-lmbd-vi-exchange-rates**
- Runtime:  | Memory: 2048MB | Timeout: 750s
- Subnets: itl-0004-itx-dev-private-2b, itl-0004-itx-dev-private-2a
- Execution role: `itl-0004-itx-dev-intchg-02-lmbd-vi-exchange-rates-role`
- KMS: _none_
- Environment variable keys: —

**itl-0004-itx-dev-intchg-02-lmbd-vi-clean**
- Runtime: python3.11 | Memory: 10240MB | Timeout: 900s
- Subnets: itl-0004-itx-dev-private-2b, itl-0004-itx-dev-private-2a
- Execution role: `itl-0004-itx-dev-intchg-02-lmbd-vi-role`
- KMS: alias/alias/itl-0004-itx-dev-kms-general-02
- Environment variable keys: DYNAMODB_FIELD_DEFINITION, CLEAN_CHUNK_SIZE, S3_BUCKET_STAGING, S3_BUCKET_LANDING

**itl-0004-itx-dev-intchg-02-lmbd-archive-file**
- Runtime: python3.11 | Memory: 8192MB | Timeout: 240s
- Subnets: itl-0004-itx-dev-private-2b, itl-0004-itx-dev-private-2a
- Execution role: `itl-0004-itx-dev-intchg-02-lmbd-vi-role`
- KMS: alias/alias/itl-0004-itx-dev-kms-general-02
- Environment variable keys: S3_BUCKET_STAGING, S3_BUCKET_LANDING, S3_BUCKET_ARCHIVE

**itl-0004-itx-dev-lmbd-file-load-02**
- Runtime: python3.10 | Memory: 128MB | Timeout: 3s
- Subnets: itl-0004-itx-dev-private-2b, itl-0004-itx-dev-private-2a
- Execution role: `itl-0004-itx-dev-lmbd-file-load-02-role`
- KMS: alias/alias/itl-0004-itx-dev-kms-general-02
- Environment variable keys: INTERCHANGE_DATABASE_SECRET_ARN, BUCKET_NAME

**itl-0004-itx-dev-lmbd-sbsa-preprocess-02**
- Runtime: python3.10 | Memory: 512MB | Timeout: 300s
- Subnets: itl-0004-itx-dev-private-2b, itl-0004-itx-dev-private-2a
- Execution role: `itl-0004-itx-dev-lmbd-sbsa-preprocess-02-role`
- KMS: alias/alias/itl-0004-itx-dev-kms-general-02
- Environment variable keys: PRD_BUCKET, PRE_BUCKET

**itl-0004-itx-dev-lmbd-app-02**
- Runtime: python3.10 | Memory: 128MB | Timeout: 3s
- Subnets: itl-0004-itx-dev-private-2b, itl-0004-itx-dev-private-2a
- Execution role: `itl-0004-itx-dev-lmbd-app-02-role`
- KMS: alias/alias/itl-0004-itx-dev-kms-general-02
- Environment variable keys: QUEUES_URL_MAP

**itl-0004-itx-dev-intchg-02-lmbd-test-2**
- Runtime: python3.11 | Memory: 512MB | Timeout: 60s
- Subnets: itl-0004-itx-dev-private-2b, itl-0004-itx-dev-private-2a
- Execution role: `itl-0004-itx-dev-intchg-02-lmbd-mc-role`
- KMS: _none_
- Environment variable keys: —

**itl-0004-itx-dev-intchg-02-lmbd-vi-store**
- Runtime: python3.11 | Memory: 10240MB | Timeout: 900s
- Subnets: itl-0004-itx-dev-private-2b, itl-0004-itx-dev-private-2a
- Execution role: `itl-0004-itx-dev-intchg-02-lmbd-vi-role`
- KMS: alias/alias/itl-0004-itx-dev-kms-general-02
- Environment variable keys: S3_BUCKET_OPERATIONAL, S3_BUCKET_STAGING, DYNAMODB_TABLE_FILE_CONTROL, S3_BUCKET_LANDING

## EC2 Instances

| Name | Type | State | Subnet | Private IP |
|---|---|---|---|---|
| itl-0004-itx-dev-ec2-app-02 | r6g.xlarge | running | itl-0004-itx-dev-private-2a | 10.14.3.173 |

## Load Balancers

### itl-0004-itx-dev-nlb-sftp-02 (NETWORK)
- **DNS:** `itl-0004-itx-dev-nlb-sftp-02-47806c4b41458d6e.elb.eu-south-2.amazonaws.com`
- **Scheme:** internet-facing
- **AZs:** eu-south-2b, eu-south-2a
