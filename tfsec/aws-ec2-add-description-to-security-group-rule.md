Pattern: Missing description for AWS EC2 security group rule

Issue: -

## Description

Security group rules should include a description for auditing purposes.

Simplifies auditing, debugging, and managing security groups.

**Resolution**: Add descriptions for all security groups rules.

## Examples

The following example will fail the aws-ec2-add-description-to-security-group-rule check.
```terraform

 resource "aws_security_group" "bad_example" {
   name        = "http"
 
   ingress {
     from_port   = 80
     to_port     = 80
     protocol    = "tcp"
     cidr_blocks = [aws_vpc.main.cidr_block]
   }
 }
 
```

The following example will pass the aws-ec2-add-description-to-security-group-rule check.
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

## Further reading

- [https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/security_group](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/security_group)
- [https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/security_group_rule](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/security_group_rule)
- [https://www.cloudconformity.com/knowledge-base/aws/EC2/security-group-rules-description.html](https://www.cloudconformity.com/knowledge-base/aws/EC2/security-group-rules-description.html)