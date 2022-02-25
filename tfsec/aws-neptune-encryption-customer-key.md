Pattern: Missing use of customer managed keys for AWS Neptune

Issue: -

## Description

Encryption using AWS keys provides protection for your Neptune underlying storage. To increase control of the encryption and manage factors like rotation use customer managed keys.

**Resolution**: Enable encryption using customer managed keys.

## Examples

The following example will fail the aws-neptune-encryption-customer-key check.
```terraform

 resource "aws_neptune_cluster" "bad_example" {
   cluster_identifier                  = "neptune-cluster-demo"
   engine                              = "neptune"
   backup_retention_period             = 5
   preferred_backup_window             = "07:00-09:00"
   skip_final_snapshot                 = true
   iam_database_authentication_enabled = true
   apply_immediately                   = true
   storage_encrypted                   = false
 }
 
```

The following example will pass the aws-neptune-encryption-customer-key check.
```terraform

 resource "aws_neptune_cluster" "good_example" {
   cluster_identifier                  = "neptune-cluster-demo"
   engine                              = "neptune"
   backup_retention_period             = 5
   preferred_backup_window             = "07:00-09:00"
   skip_final_snapshot                 = true
   iam_database_authentication_enabled = true
   apply_immediately                   = true
   storage_encrypted                   = true
   kms_key_arn                         = true
 }
 
```

## Further reading

- [https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/neptune_cluster#storage_encrypted](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/neptune_cluster#storage_encrypted)
- [https://docs.aws.amazon.com/neptune/latest/userguide/encrypt.html](https://docs.aws.amazon.com/neptune/latest/userguide/encrypt.html)