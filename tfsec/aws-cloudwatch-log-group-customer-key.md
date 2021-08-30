Pattern: CloudWatch log groups should be encrypted using CMK

Issue: -

## Description

CloudWatch log groups are encrypted by default, however, to get the full benefit of controlling key rotation and other KMS aspects a KMS CMK should be used.

**Resolution**: Enable CMK encryption of CloudWatch Log Groups.

## Examples

Example of **incorrect** code:

```terraform
resource "aws_cloudwatch_log_group" "bad_example" {
	name = "bad_example"

}
```

Example of **correct** code:

```terraform
resource "aws_cloudwatch_log_group" "good_example" {
	name = "good_example"

	kms_key_id = aws_kms_key.log_key.arn
}
```