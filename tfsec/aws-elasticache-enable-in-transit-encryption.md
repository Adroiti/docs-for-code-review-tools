Pattern: Disabled encryption for AWS ElastiCache replication group

Issue: -

## Description

Traffic flowing between ElastiCache replication nodes should be encrypted to ensure sensitive data is kept private.

**Resolution**: Enable in transit encryption for replication group.

## Examples

Example of **incorrect** code:

```terraform
resource "aws_elasticache_replication_group" "bad_example" {
        replication_group_id = "foo"
        replication_group_description = "my foo cluster"

        transit_encryption_enabled = false
}
```

Example of **correct** code:

```terraform
resource "aws_elasticache_replication_group" "good_example" {
        replication_group_id = "foo"
        replication_group_description = "my foo cluster"

        transit_encryption_enabled = true
}
```