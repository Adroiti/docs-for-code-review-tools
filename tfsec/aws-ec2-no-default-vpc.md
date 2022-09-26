Pattern: Use of default VPC for AWS EC2 workflow

Issue: -

## Description

Default VPC does not have a lot of the critical security features that standard VPC comes with, new resources should not be created in the default VPC and it should not be present in the Terraform.

**Resolution**: Create a non-default vpc for resources to be created in.

## Examples

The following example will fail the aws-ec2-no-default-vpc check.
```terraform

 resource "aws_default_vpc" "default" {
 	tags = {
 	  Name = "Default VPC"
 	}
   }
 
```

The following example will pass the aws-ec2-no-default-vpc check.
```terraform

## Further reading

- [https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/default_vpc](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/default_vpc)
- [https://docs.aws.amazon.com/vpc/latest/userguide/default-vpc.html](https://docs.aws.amazon.com/vpc/latest/userguide/default-vpc.html)