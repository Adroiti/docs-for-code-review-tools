Pattern: Disabled storage encryption for AWS DocumentDB

Issue: -

## Description

Encryption of the underlying storage used by DocumentDB ensures that if there is compromise of the disks, the data is still protected.

**Resolution**: Enable storage encryption.

## Examples

Example of **incorrect** code:

```terraform
resource "aws_docdb_cluster" "bad_example" {
  cluster_identifier      = "my-docdb-cluster"
  engine                  = "docdb"
  master_username         = "foo"
  master_password         = "mustbeeightchars"
  backup_retention_period = 5
  preferred_backup_window = "07:00-09:00"
  skip_final_snapshot     = true
  storage_encrypted = false
}
```

Example of **correct** code:

```terraform
resource "aws_docdb_cluster" "good_example" {
  cluster_identifier      = "my-docdb-cluster"
  engine                  = "docdb"
  master_username         = "foo"
  master_password         = "mustbeeightchars"
  backup_retention_period = 5
  preferred_backup_window = "07:00-09:00"
  skip_final_snapshot     = true
  storage_encrypted = true
}
```