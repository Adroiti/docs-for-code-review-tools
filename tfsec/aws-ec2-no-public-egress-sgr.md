Pattern: Use of public AWS EC2 egress security group rule

Issue: -

## Description

Opening up ports to connect out to the public internet is generally to be avoided. You should restrict access to IP addresses or ranges that are explicitly required where possible.

**Resolution**: Set a more restrictive cidr range.

## Examples

The following example will fail the aws-ec2-no-public-egress-sgr check.
```terraform

 resource "aws_security_group" "bad_example" {
 	egress {
 		cidr_blocks = ["0.0.0.0/0"]
 	}
 }
 
```

The following example will pass the aws-ec2-no-public-egress-sgr check.
```terraform

 resource "aws_security_group" "good_example" {
 	egress {
 		cidr_blocks = ["1.2.3.4/32"]
 	}
 }
 
```

## Further reading

- [https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/security_group](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/security_group)
- [https://docs.aws.amazon.com/whitepapers/latest/building-scalable-secure-multi-vpc-network-infrastructure/centralized-egress-to-internet.html](https://docs.aws.amazon.com/whitepapers/latest/building-scalable-secure-multi-vpc-network-infrastructure/centralized-egress-to-internet.html)