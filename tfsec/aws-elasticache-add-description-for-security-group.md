Pattern: Missing description for AWS ElastiCache security group/rule

Issue: -

## Description

Security groups and security group rules should include a description for auditing purposes. This simplifies auditing, debugging, and managing security groups.

**Resolution**: Add descriptions for all security groups and rules.

## Examples

Example of **incorrect** code:

```terraform
resource "aws_security_group" "bar" {
  name = "security-group"
}

resource "aws_elasticache_security_group" "bad_example" {
  name                 = "elasticache-security-group"
  security_group_names = [aws_security_group.bar.name]
  description = ""
}
```

Example of **correct** code:

```terraform
resource "aws_security_group" "bar" {
  name = "security-group"
}

resource "aws_elasticache_security_group" "good_example" {
  name                 = "elasticache-security-group"
  security_group_names = [aws_security_group.bar.name]
  description = "something"
}
```