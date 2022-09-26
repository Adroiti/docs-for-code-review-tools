Pattern: Disabled encryption for AWS EBS volume

Issue: -

## Description

By enabling encryption on EBS volumes you protect the volume, the disk I/O and any derived snapshots from compromise if intercepted.

**Resolution**: Enable encryption of EBS volumes.

## Examples

The following example will fail the aws-ec2-enable-volume-encryption check.
```terraform

 resource "aws_ebs_volume" "bad_example" {
   availability_zone = "us-west-2a"
   size              = 40
 
   tags = {
     Name = "HelloWorld"
   }
   encrypted = false
 }
 
```

The following example will pass the aws-ec2-enable-volume-encryption check.
```terraform

 resource "aws_ebs_volume" "good_example" {
   availability_zone = "us-west-2a"
   size              = 40
 
   tags = {
     Name = "HelloWorld"
   }
   encrypted = true
 }
 
```

## Further reading

- [https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/ebs_volume#encrypted](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/ebs_volume#encrypted)
- [https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSEncryption.html](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSEncryption.html)