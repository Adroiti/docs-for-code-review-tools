Pattern: Use of public AWS EC2 ingress security group rule

Issue: -

## Description

Opening up ports to the public internet is generally to be avoided. You should restrict access to IP addresses or ranges that explicitly require it where possible.

**Resolution**: Set a more restrictive cidr range.

## Examples

The following example will fail the aws-ec2-no-public-ingress-sgr check.
```terraform

 resource "aws_security_group_rule" "bad_example" {
 	type = "ingress"
 	cidr_blocks = ["0.0.0.0/0"]
 }
 
```

The following example will pass the aws-ec2-no-public-ingress-sgr check.
```terraform

 resource "aws_security_group_rule" "good_example" {
 	type = "ingress"
 	cidr_blocks = ["10.0.0.0/16"]
 }
 
```

## Further reading

- [https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/security_group_rule#cidr_blocks](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/security_group_rule#cidr_blocks)
- [https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/security-group-rules-reference.html](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/security-group-rules-reference.html)