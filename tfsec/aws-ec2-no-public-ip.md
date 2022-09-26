Pattern: Use of public IP for EC2 launch config

Issue: -

## Description

You should limit the provision of public IP addresses for resources. Resources should not be exposed on the public internet, but should have access limited to consumers required for the function of your application.

**Resolution**: Set the instance to not be publicly accessible.

## Examples

The following example will fail the aws-ec2-no-public-ip check.
```terraform

 resource "aws_launch_configuration" "bad_example" {
 	associate_public_ip_address = true
 }
 
```

The following example will pass the aws-ec2-no-public-ip check.
```terraform

 resource "aws_launch_configuration" "good_example" {
 	associate_public_ip_address = false
 }
 
```

## Further reading

- [https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/launch_configuration#associate_public_ip_address](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/launch_configuration#associate_public_ip_address)
- [https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/instance#associate_public_ip_address](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/instance#associate_public_ip_address)
- [https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-instance-addressing.html](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-instance-addressing.html)