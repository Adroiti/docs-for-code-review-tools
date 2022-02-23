Pattern: Use of public AWS load balancer

Issue: -

## Description

There are many scenarios in which you would want to expose a load balancer to the wider internet, but this check exists as a warning to prevent accidental exposure of internal assets. You should ensure that this resource should be exposed publicly.

**Resolution**: Switch to an internal load balancer or add a tfsec ignore.

## Examples

Example of **incorrect** code:

```terraform
resource "aws_alb" "bad_example" {
	internal = false
}
```

Example of **correct** code:

```terraform
resource "aws_alb" "good_example" {
	internal = true
}
```