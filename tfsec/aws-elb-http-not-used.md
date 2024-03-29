Pattern: Use of HTTP for `aws_alb_listener`

Issue: -

## Description

Plain HTTP is unencrypted and human-readable. This means that if a malicious actor was to eavesdrop on your connection, they would be able to see all of your data flowing back and forth.

You should use HTTPS, which is HTTP over an encrypted (TLS) connection, meaning eavesdroppers cannot read your traffic.

**Resolution**: Switch to HTTPS to benefit from TLS security features.

## Examples

The following example will fail the aws-elb-http-not-used check.

```terraform
 resource "aws_alb_listener" "bad_example" {
 	protocol = "HTTP"
 }
```

The following example will pass the aws-elb-http-not-used check.

```terraform
 resource "aws_alb_listener" "good_example" {
 	protocol = "HTTPS"
 }
```

## Further reading

- [https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/lb_listener](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/lb_listener)
