Pattern: EBS volume encryption should use Customer Managed Keys

Issue: -

## Description

Encryption using AWS keys provides protection for your EBS volume. To increase control of the encryption and manage factors like rotation use customer managed keys.

**Resolution**: Enable encryption using customer managed keys.

## Examples

Example of **incorrect** code:

```terraform
resource "aws_ebs_volume" "example" {
  availability_zone = "us-west-2a"
  size              = 40

  tags = {
    Name = "HelloWorld"
  }
}
```

Example of **correct** code:

```terraform
resource "aws_kms_key" "ebs_encryption" {
	enable_key_rotation = true
}

resource "aws_ebs_volume" "example" {
  availability_zone = "us-west-2a"
  size              = 40

  kms_key_id = aws_kms_key.ebs_encryption.arn

  tags = {
    Name = "HelloWorld"
  }
}
```