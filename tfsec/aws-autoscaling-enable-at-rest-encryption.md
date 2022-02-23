Pattern: Disabled encryption for AWS block device

Issue: -

## Description

Blocks devices should be encrypted to ensure sensitive data is hel securely at rest.

**Resolution**: Turn on encryption for all block devices.

## Examples

Example of **incorrect** code:

```terraform
resource "aws_launch_configuration" "bad_example" {
	root_block_device {
		encrypted = false
	}
}
```

Example of **correct** code:

```terraform
resource "aws_launch_configuration" "good_example" {
	root_block_device {
		encrypted = true
	}
}
```