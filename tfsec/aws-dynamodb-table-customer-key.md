Pattern: Missing use of Customer Managed Key for AWS DynamoDB table

Issue: -

## Description

DynamoDB tables are encrypted by default using AWS managed encryption keys. To increase control of the encryption and control the management of factors like key rotation, use a Customer Managed Key.

**Resolution**: Enable server side encryption with a customer managed key.

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
  
	replica {
	  region_name = "us-east-2"
	}
  
	replica {
	  region_name = "us-west-2"
	}
  }
```

Example of **correct** code:

```terraform
resource "aws_kms_key" "dynamo_db_kms" {
	enable_key_rotation = true
}

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
  
	replica {
	  region_name = "us-east-2"
	}
  
	replica {
	  region_name = "us-west-2"
	}

	server_side_encryption {
		enabled     = true
		kms_key_arn = aws_kms_key.dynamo_db_kms.key_id
	}
  }
```