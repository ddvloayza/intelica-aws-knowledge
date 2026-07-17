# Cross-Account Topology Overview

_Last updated: 2026-07-17 14:42 UTC_

This document describes how Intelica AWS accounts are connected to each other.

## Transit Gateway Connections

### TGW: `tgw-042a72cb246bebf1e`
**Connects:** Analytics-Dev ↔ Analytics-Prod ↔ Intelica-Network ↔ Interchange-Dev ↔ Interchange-Prod ↔ Portal-Dev ↔ Portal-Prod

| Account | Attachment ID | VPC |
|---|---|---|
| Analytics-Dev | `tgw-attach-0b9e3e995cfcca714` | `vpc-092dc05179287e08a` |
| Analytics-Prod | `tgw-attach-0075738dd2bed67c3` | `vpc-0008aceba2432ab91` |
| Intelica-Network | `tgw-attach-0075738dd2bed67c3` | `vpc-0008aceba2432ab91` |
| Intelica-Network | `tgw-attach-0374276375df2f3c8` | `vpc-000f7f02c4d4819a3` |
| Intelica-Network | `tgw-attach-051b6928615862d2a` | `vpc-0626d66632373c892` |
| Intelica-Network | `tgw-attach-05f42edf4684ca97e` | `vpc-075c1d6bc4aa2fa81` |
| Intelica-Network | `tgw-attach-07f191cf3bd956294` | `vpc-0101d2c447b67e9db` |
| Intelica-Network | `tgw-attach-08bec69283e6c3018` | `vpc-0fbd191d169cc9efb` |
| Intelica-Network | `tgw-attach-099db8323944dbd48` | `vpc-0c6863a32b8db36e0` |
| Intelica-Network | `tgw-attach-0b9e3e995cfcca714` | `vpc-092dc05179287e08a` |
| Intelica-Network | `tgw-attach-0efdd0c4be3dda9a1` | `vpc-0943c2ad6ac2aeb29` |
| Interchange-Dev | `tgw-attach-07f191cf3bd956294` | `vpc-0101d2c447b67e9db` |
| Interchange-Prod | `tgw-attach-099db8323944dbd48` | `vpc-0c6863a32b8db36e0` |
| Portal-Dev | `tgw-attach-08bec69283e6c3018` | `vpc-0fbd191d169cc9efb` |
| Portal-Prod | `tgw-attach-051b6928615862d2a` | `vpc-0626d66632373c892` |

_Via Transit Gateway, resources in these accounts can route traffic to each other._

## IAM Cross-Account Trust

| Role | Owner Account | Trusts Account |
|---|---|---|
| aws-controltower-AdministratorExecutionRole | Analytics-Dev | Audit |
| aws-controltower-ReadOnlyExecutionRole | Analytics-Dev | Audit |
| aws-controltower-AdministratorExecutionRole | Analytics-Prod | Audit |
| aws-controltower-ReadOnlyExecutionRole | Analytics-Prod | Audit |
| aws-controltower-AdministratorExecutionRole | Intelica-Network | Audit |
| aws-controltower-ReadOnlyExecutionRole | Intelica-Network | Audit |
| itl-0001-shared-network-all-eks-route53-assume-role | Intelica-Network | Portal-Prod |
| aws-controltower-AdministratorExecutionRole | Interchange-Dev | Audit |
| aws-controltower-ReadOnlyExecutionRole | Interchange-Dev | Audit |
| aws-controltower-AdministratorExecutionRole | Interchange-Prod | Audit |
| aws-controltower-ReadOnlyExecutionRole | Interchange-Prod | Audit |
| intelica-copy-from-denver-to-s3-role | Interchange-Prod | Portal-Prod |
| itl-0004-itx-prd-quickSightCrossAccountRole | Interchange-Prod | Portal-Prod |
| aws-controltower-ReadOnlyExecutionRole | Portal-Dev | Audit |
| aws-controltower-AdministratorExecutionRole | Portal-Dev | Audit |
| aws-controltower-ReadOnlyExecutionRole | Portal-Prod | Audit |
| aws-controltower-AdministratorExecutionRole | Portal-Prod | Audit |
