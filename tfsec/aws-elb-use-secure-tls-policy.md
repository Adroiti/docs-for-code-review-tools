Pattern: Use of insecure TLS/SSL policy for AWS load balancer

Issue: -

## Description

You should not use outdated/insecure TLS versions for encryption. You should be using TLS v1.2+.

**Resolution**: Use a more recent TLS/SSL policy for the load balancer.

## Examples

The following example will fail the aws-elb-use-secure-tls-policy check.

```terraform
 resource "aws_alb_listener" "bad_example" {
 	ssl_policy = "ELBSecurityPolicy-TLS-1-1-2017-01"
 	protocol = "HTTPS"
 }
```

The following example will pass the aws-elb-use-secure-tls-policy check.

```terraform
 resource "aws_alb_listener" "good_example" {
 	ssl_policy = "ELBSecurityPolicy-TLS-1-2-2017-01"
 	protocol = "HTTPS"
 }
```

## Further reading

- [https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/lb_listener](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/lb_listener)