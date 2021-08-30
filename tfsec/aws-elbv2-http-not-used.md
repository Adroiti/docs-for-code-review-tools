Pattern: Use of plain HTTP

Issue: -

## Description

Plain HTTP is unencrypted and human-readable. This means that if a malicious actor was to eavesdrop on your connection, they would be able to see all of your data flowing back and forth.

You should use HTTPS, which is HTTP over an encrypted (TLS) connection, meaning eavesdroppers cannot read your traffic.

**Resolution**: Switch to HTTPS to benefit from TLS security features.

## Examples

Example of **incorrect** code:

```terraform
resource "aws_alb_listener" "bad_example" {
	protocol = "HTTP"
}
```

Example of **correct** code:

```terraform
resource "aws_alb_listener" "good_example" {
	protocol = "HTTPS"
}
```