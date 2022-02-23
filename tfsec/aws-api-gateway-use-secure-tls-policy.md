Pattern: Use of insecure TLS policy for AWS API Gateway domain name

Issue: -

## Description

You should not use outdated/insecure TLS versions for encryption. You should be using TLS v1.2+.

**Resolution**: Use the most modern TLS/SSL policies available.

## Examples

Example of **incorrect** code:

```terraform
resource "aws_api_gateway_domain_name" "bad_example" {
	security_policy = "TLS_1_0"
}
```

Example of **correct** code:

```terraform
resource "aws_api_gateway_domain_name" "good_example" {
	security_policy = "TLS_1_2"
}
```