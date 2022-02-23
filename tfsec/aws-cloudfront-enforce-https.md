Pattern: Use of HTTP for AWS CloudFront

Issue: -

## Description

Plain HTTP is unencrypted and human-readable. This means that if a malicious actor was to eavesdrop on your connection, they would be able to see all of your data flowing back and forth.

You should use HTTPS, which is HTTP over an encrypted (TLS) connection, meaning eavesdroppers cannot read your traffic.

**Resolution**: Only allow HTTPS for CloudFront distribution communication.

## Examples

Example of **incorrect** code:

```terraform
resource "aws_cloudfront_distribution" "bad_example" {
	default_cache_behavior {
	    viewer_protocol_policy = "allow-all"
	  }
}
```

Example of **correct** code:

```terraform
resource "aws_cloudfront_distribution" "good_example" {
	default_cache_behavior {
	    viewer_protocol_policy = "redirect-to-https"
	  }
}
```