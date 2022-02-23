Pattern: Missing use of auto rotation for AWS KMS key

Issue: -

## Description

You should configure your KMS keys to auto rotate to maintain security and defend against compromise.

**Resolution**: Configure KMS key to auto rotate.

## Examples

Example of **incorrect** code:

```terraform
resource "aws_kms_key" "bad_example" {
	enable_key_rotation = false
}
```

Example of **correct** code:

```terraform
resource "aws_kms_key" "good_example" {
	enable_key_rotation = true
}
```