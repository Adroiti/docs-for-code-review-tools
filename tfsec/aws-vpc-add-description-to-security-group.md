Pattern: Missing description for AWS security group/rule

Issue: -

## Description

Security groups and security group rules should include a description for auditing purposes. This simplifies auditing, debugging, and managing security groups.

**Resolution**: Add descriptions for all security groups and rules.

## Examples

Example of **incorrect** code:

```terraform
resource "aws_security_group" "bad_example" {
  name        = "http"

  ingress {
    description = "HTTP from VPC"
    from_port   = 80
    to_port     = 80
    protocol    = "tcp"
    cidr_blocks = [aws_vpc.main.cidr_block]
  }
}
```

Example of **correct** code:

```terraform
resource "aws_security_group" "good_example" {
  name        = "http"
  description = "Allow inbound HTTP traffic"

  ingress {
    description = "HTTP from VPC"
    from_port   = 80
    to_port     = 80
    protocol    = "tcp"
    cidr_blocks = [aws_vpc.main.cidr_block]
  }
}
```