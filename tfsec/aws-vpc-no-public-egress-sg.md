Pattern: Use of public AWS egress security group

Issue: -

## Description

Opening up ports to the public internet is generally to be avoided. You should restrict access to IP addresses or ranges that explicitly require it where possible.

**Resolution**: Set a more restrictive cidr range.

## Examples

Example of **incorrect** code:

```terraform
resource "aws_security_group" "bad_example" {
	egress {
		cidr_blocks = ["0.0.0.0/0"]
	}
}
```

Example of **correct** code:

```terraform
resource "aws_security_group" "good_example" {
	egress {
		cidr_blocks = ["1.2.3.4/32"]
	}
}
```