Pattern: Disabled encryption for AWS RDS cluster storage

Issue: -

## Description

Encryption should be enabled for an RDS Aurora cluster. When enabling encryption by setting the `kms_key_id` and `storage_encrypted` must also be set to true.

**Resolution**: Enable encryption for RDS clusters and instances.

## Examples

Example of **incorrect** code:

```terraform
resource "aws_rds_cluster" "bad_example" {
  name       = "bar"
  kms_key_id = ""
}
```

Example of **correct** code:

```terraform
resource "aws_rds_cluster" "good_example" {
  name              = "bar"
  kms_key_id  = "arn:aws:kms:us-west-2:111122223333:key/1234abcd-12ab-34cd-56ef-1234567890ab"
  storage_encrypted = true
}
```