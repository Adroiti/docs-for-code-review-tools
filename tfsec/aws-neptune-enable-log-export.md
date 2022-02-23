Pattern: Disabled log export for AWS Neptune

Issue: -

## Description

Neptune does not have auditing by default. To ensure that you are able to accurately audit the usage of your Neptune instance you should enable export logs.

**Resolution**: Enable export logs.

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
  enable_cloudwatch_logs_exports      = []
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
  enable_cloudwatch_logs_exports      = ["audit"]
}
```