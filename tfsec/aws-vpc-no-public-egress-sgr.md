Pattern: An egress security group rule allows traffic to /0

Issue: -

## Description

Opening up ports to connect out to the public internet is generally to be avoided. You should restrict access to IP addresses or ranges that are explicitly required where possible.

**Resolution**: Set a more restrictive cidr range.

## Examples

Example of **incorrect** code:

```terraform
resource "aws_security_group_rule" "bad_example" {
	type = "egress"
	cidr_blocks = ["0.0.0.0/0"]
}
```

Example of **correct** code:

```terraform
resource "aws_security_group_rule" "good_example" {
	type = "egress"
	cidr_blocks = ["10.0.0.0/16"]
}
```