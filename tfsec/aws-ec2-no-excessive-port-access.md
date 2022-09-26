Pattern: Excessive port access for AWS EC2

Issue: -

## Description

Ensure access to specific required ports is allowed, and nothing else.

**Resolution**: Set specific allowed ports.

## Examples

The following example will fail the aws-ec2-no-excessive-port-access check.
```terraform

 resource "aws_network_acl_rule" "bad_example" {
   egress         = false
   protocol       = "all"
   rule_action    = "allow"
   cidr_block     = "0.0.0.0/0"
 }
 
```

The following example will pass the aws-ec2-no-excessive-port-access check.
```terraform

 resource "aws_network_acl_rule" "good_example" {
   egress         = false
   protocol       = "tcp"
   from_port      = 22
   to_port        = 22
   rule_action    = "allow"
   cidr_block     = "0.0.0.0/0"
 }
 
```

## Further reading

- [https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/network_acl_rule#to_port](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/network_acl_rule#to_port)
- [https://docs.aws.amazon.com/vpc/latest/userguide/vpc-network-acls.html](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-network-acls.html)