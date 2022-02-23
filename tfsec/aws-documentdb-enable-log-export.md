Pattern: Disabled export logs for AWS DocumentDB

Issue: -

## Description

DocumentDB does not have auditing by default. To ensure that you are able to accurately audit the usage of your DocumentDB cluster you should enable export logs.

**Resolution**: Enable export logs.

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
  enabled_cloudwatch_logs_exports = "something"
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
  enabled_cloudwatch_logs_exports = "audit"
}
```