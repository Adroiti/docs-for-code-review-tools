Pattern: Disabled encryption for EBS volumes

Issue: -

## Description

By enabling encryption on EBS volumes you protect the volume, the disk I/O and any derived snapshots from compromise if intercepted.

**Resolution**: Enable encryption of EBS volumes.

## Examples

Example of **incorrect** code:

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

Example of **correct** code:

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