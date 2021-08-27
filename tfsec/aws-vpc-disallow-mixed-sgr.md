Pattern: Use of mixed security group rules

Issue: -

## Description

Mixing Terraform standalone `security_group_rule` resource and `security_group` resource with inline ingress/egress rules results in rules being overwritten during Terraform apply.

**Resolution**: Either define all of a security group's rules inline, or none of the security group's rules inline.

## Examples

Example of **incorrect** code:

```terraform
resource "aws_security_group_rule" "bad_example" {
  	security_group_id = aws_security_group.bad_example_sg.id
	type = "ingress"
	cidr_blocks = ["172.31.0.0/16"]
}

resource "aws_security_group" "bad_example_sg" {
	ingress {
		cidr_blocks = ["10.0.0.0/16"]
	}
}
```

Example of **correct** code:

```terraform
resource "aws_security_group_rule" "good_example" {
  	security_group_id = aws_security_group.good_example_sg.id
	type = "ingress"
	cidr_blocks = ["10.0.0.0/16", "172.31.0.0/16"]
}

resource "aws_security_group" "good_example_sg" {
}
```