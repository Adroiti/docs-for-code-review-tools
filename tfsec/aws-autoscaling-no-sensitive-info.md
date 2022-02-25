Pattern: Use of sensitive info in `aws_launch_configuration`

Issue: -

## Description

When creating Launch Configurations, user data can be used for the initial configuration of the instance. User data must not contain any sensitive data.

**Resolution**: Don't use sensitive data in user data.

## Examples

The following example will fail the aws-autoscaling-no-sensitive-info check.
```terraform

 resource "aws_launch_configuration" "as_conf" {
   name          = "web_config"
   image_id      = data.aws_ami.ubuntu.id
   instance_type = "t2.micro"
   user_data     = <<EOF
 export DATABASE_PASSWORD=\"SomeSortOfPassword\"
 EOF
 }
 
```

The following example will pass the aws-autoscaling-no-sensitive-info check.
```terraform

 resource "aws_launch_configuration" "as_conf" {
   name          = "web_config"
   image_id      = data.aws_ami.ubuntu.id
   instance_type = "t2.micro"
   user_data     = <<EOF
 export GREETING="Hello there"
 EOF
 }
 
```

## Further reading

- [https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/launch_configuration#user_data,user_data_base64](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/launch_configuration#user_data,user_data_base64)