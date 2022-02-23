Pattern: Use of outdated SSL policy for AWS load balancer

Issue: -

## Description

You should not use outdated/insecure TLS versions for encryption. You should be using TLS v1.2+.

**Resolution**: Use a more recent TLS/SSL policy for the load balancer.

## Examples

Example of **incorrect** code:

```terraform
resource "aws_alb_listener" "bad_example" {
	ssl_policy = "ELBSecurityPolicy-TLS-1-1-2017-01"
	protocol = "HTTPS"
}
```

Example of **correct** code:

```terraform
resource "aws_alb_listener" "good_example" {
	ssl_policy = "ELBSecurityPolicy-TLS-1-2-2017-01"
	protocol = "HTTPS"
}
```