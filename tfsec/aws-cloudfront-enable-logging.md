Pattern: Cloudfront distribution should have Access Logging configured

Issue: -

## Description

You should configure CloudFront Access Logging to create log files that contain detailed information about every user request that CloudFront receives

**Resolution**: Enable logging for CloudFront distributions.

## Examples

Example of **incorrect** code:

```terraform
resource "aws_cloudfront_distribution" "bad_example" {
	// other config
	// no logging_config
}
```

Example of **correct** code:

```terraform
resource "aws_cloudfront_distribution" "good_example" {
	// other config
	logging_config {
		include_cookies = false
		bucket          = "mylogs.s3.amazonaws.com"
		prefix          = "myprefix"
	}
}
```