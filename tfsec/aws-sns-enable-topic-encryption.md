Pattern: Unencrypted AWS SNS topic

Issue: -

## Description

Queues should be encrypted with customer managed KMS keys and not default AWS managed keys, in order to allow granular control over access to specific queues.

**Resolution**: Turn on SNS Topic encryption.

## Examples

Example of **incorrect** code:

```terraform
resource "aws_sns_topic" "bad_example" {
	# no key id specified
}
```

Example of **correct** code:

```terraform
resource "aws_sns_topic" "good_example" {
	kms_master_key_id = "/blah"
}
```