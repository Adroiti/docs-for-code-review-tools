Pattern: Disabled at-rest encryption for AWS EC2 launch config

Issue: -

## Description

Block devices should be encrypted to ensure sensitive data is held securely at rest.

**Resolution**: Turn on encryption for all block devices.

## Examples

The following example will fail the aws-ec2-enable-launch-config-at-rest-encryption check.
```terraform

 resource "aws_launch_configuration" "bad_example" {
 	root_block_device {
 		encrypted = false
 	}
 }
 
```

The following example will pass the aws-ec2-enable-launch-config-at-rest-encryption check.
```terraform

 resource "aws_launch_configuration" "good_example" {
 	root_block_device {
 		encrypted = true
 	}
 }
 
```

## Further reading

- [https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/instance#ebs-ephemeral-and-root-block-devices](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/instance#ebs-ephemeral-and-root-block-devices)
- [https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/RootDeviceStorage.html](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/RootDeviceStorage.html)