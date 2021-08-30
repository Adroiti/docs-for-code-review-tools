Pattern: A resource has a public IP address

Issue: -

## Description

You should limit the provision of public IP addresses for resources. Resources should not be exposed on the public internet, but should have access limited to consumers required for the function of your application.

**Resolution**: Set the instance to not be publically accessible.

## Examples

Example of **incorrect** code:

```terraform
resource "aws_launch_configuration" "bad_example" {
	associate_public_ip_address = true
}
```

Example of **correct** code:

```terraform
resource "aws_launch_configuration" "good_example" {
	associate_public_ip_address = false
}
```