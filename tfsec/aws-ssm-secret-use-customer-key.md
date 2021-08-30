Pattern: Secrets Manager should use customer managed keys

Issue: -

## Description

Secrets Manager encrypts secrets by default using a default key created by AWS. To ensure control and granularity of secret encryption, CMK's should be used explictly.

**Resolution**: Use customer managed keys.

## Examples

Example of **incorrect** code:

```terraform
resource "aws_secretsmanager_secret" "bad_example" {
  name       = "lambda_password"
}
```

Example of **correct** code:

```terraform
resource "aws_kms_key" "secrets" {
	enable_key_rotation = true
}

resource "aws_secretsmanager_secret" "good_example" {
  name       = "lambda_password"
  kms_key_id = aws_kms_key.secrets.arn
}
```