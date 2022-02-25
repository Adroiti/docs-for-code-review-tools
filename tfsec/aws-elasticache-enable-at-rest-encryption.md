Pattern: Disabled at-rest encryption for AWS ElastiCache

Issue: -

## Description

Data stored within an ElastiCache replication node should be encrypted to ensure sensitive data is kept private.

**Resolution**: Enable at-rest encryption for replication group.

## Examples

The following example will fail the aws-elasticache-enable-at-rest-encryption check.
```terraform

 resource "aws_elasticache_replication_group" "bad_example" {
         replication_group_id = "foo"
         replication_group_description = "my foo cluster"
 
         at_rest_encryption_enabled = false
 }
 
```

The following example will pass the aws-elasticache-enable-at-rest-encryption check.
```terraform

 resource "aws_elasticache_replication_group" "good_example" {
         replication_group_id = "foo"
         replication_group_description = "my foo cluster"
 
         at_rest_encryption_enabled = true
 }
 
```

## Further reading

- [https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/elasticache_replication_group#at_rest_encryption_enabled](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/elasticache_replication_group#at_rest_encryption_enabled)
- [https://docs.aws.amazon.com/AmazonElastiCache/latest/red-ug/at-rest-encryption.html](https://docs.aws.amazon.com/AmazonElastiCache/latest/red-ug/at-rest-encryption.html)