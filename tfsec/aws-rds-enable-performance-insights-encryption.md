Pattern: Disabled encryption for AWS RDS Performance Insights

Issue: -

## Description

When enabling Performance Insights on an RDS cluster or RDS DB Instance, and encryption key should be provided.

The encryption key specified in `performance_insights_kms_key_id` references a KMS ARN

**Resolution**: Enable encryption for RDS clusters and instances.

## Examples

Example of **incorrect** code:

```terraform

resource "aws_rds_cluster_instance" "bad_example" {
	name = "bar"
	performance_insights_enabled = true
	performance_insights_kms_key_id = ""
}
		
```

Example of **correct** code:

```terraform

resource "aws_rds_cluster_instance" "good_example" {
	name = "bar"
	performance_insights_enabled = true
	performance_insights_kms_key_id = "arn:aws:kms:us-west-2:111122223333:key/1234abcd-12ab-34cd-56ef-1234567890ab"
}
		
```