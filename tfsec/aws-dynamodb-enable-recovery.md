Pattern: Missing use of point in time recovery for AWS DynamoDB

Issue: -

## Description

DynamoDB tables should be protected against accidentally or malicious write/delete actions by ensuring that there is adequate protection. By enabling point-in-time-recovery you can restore to a known point in the event of loss of data.

**Resolution**: Enable point in time recovery.

## Examples

Example of **incorrect** code:

```terraform
resource "aws_dynamodb_table" "bad_example" {
	name             = "example"
	hash_key         = "TestTableHashKey"
	billing_mode     = "PAY_PER_REQUEST"
	stream_enabled   = true
	stream_view_type = "NEW_AND_OLD_IMAGES"
  
	attribute {
	  name = "TestTableHashKey"
	  type = "S"
	}
}
```

Example of **correct** code:

```terraform
resource "aws_dynamodb_table" "good_example" {
	name             = "example"
	hash_key         = "TestTableHashKey"
	billing_mode     = "PAY_PER_REQUEST"
	stream_enabled   = true
	stream_view_type = "NEW_AND_OLD_IMAGES"
  
	attribute {
	  name = "TestTableHashKey"
	  type = "S"
	}

	point_in_time_recovery {
		enabled = true
	}
}
```