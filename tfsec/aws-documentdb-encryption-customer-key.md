Pattern: Disabled Customer Managed Keys for AWS DocumentDB

Issue: -

## Description

Encryption using AWS keys provides protection for your DocumentDB underlying storage. To increase control of the encryption and manage factors like rotation use customer managed keys.

**Resolution**: Enable encryption using customer managed keys.

## Examples

Example of **incorrect** code:

```terraform
resource "aws_docdb_cluster" "docdb" {
  cluster_identifier      = "my-docdb-cluster"
  engine                  = "docdb"
  master_username         = "foo"
  master_password         = "mustbeeightchars"
  backup_retention_period = 5
  preferred_backup_window = "07:00-09:00"
  skip_final_snapshot     = true
}
```

Example of **correct** code:

```terraform
resource "aws_kms_key" "docdb_encryption" {
	enable_key_rotation = true
}
			
resource "aws_docdb_cluster" "docdb" {
  cluster_identifier      = "my-docdb-cluster"
  engine                  = "docdb"
  master_username         = "foo"
  master_password         = "mustbeeightchars"
  backup_retention_period = 5
  preferred_backup_window = "07:00-09:00"
  skip_final_snapshot     = true
  kms_key_id 			  = aws_kms_key.docdb_encryption.arn
}
```