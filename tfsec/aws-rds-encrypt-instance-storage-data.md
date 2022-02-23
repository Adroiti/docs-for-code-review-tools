Pattern: Disabled encryption for AWS RDS instance storage

Issue: -

## Description

Encryption should be enabled for an RDS Database instances. 

**Resolution**: Enable encryption for RDS instances.

## Examples

Example of **incorrect** code:

```terraform
resource "aws_db_instance" "bad_example" {
	
}
```

Example of **correct** code:

```terraform
resource "aws_db_instance" "good_example" {
	storage_encrypted  = true
}
```