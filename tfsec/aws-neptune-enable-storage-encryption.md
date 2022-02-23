Pattern: Disabled storage encryption for AWS Neptune

Issue: -

## Description

Encryption of Neptune storage ensures that if there is compromise of the disks, the data is still protected.

**Resolution**: Enable encryption of Neptune storage.

## Examples

Example of **incorrect** code:

```terraform
resource "aws_neptune_cluster" "bad_example" {
  cluster_identifier                  = "neptune-cluster-demo"
  engine                              = "neptune"
  backup_retention_period             = 5
  preferred_backup_window             = "07:00-09:00"
  skip_final_snapshot                 = true
  iam_database_authentication_enabled = true
  apply_immediately                   = true
  storage_encrypted = false
}
```

Example of **correct** code:

```terraform
resource "aws_neptune_cluster" "good_example" {
  cluster_identifier                  = "neptune-cluster-demo"
  engine                              = "neptune"
  backup_retention_period             = 5
  preferred_backup_window             = "07:00-09:00"
  skip_final_snapshot                 = true
  iam_database_authentication_enabled = true
  apply_immediately                   = true
  storage_encrypted = true
}
```