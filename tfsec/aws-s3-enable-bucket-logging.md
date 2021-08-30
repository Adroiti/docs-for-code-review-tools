Pattern: S3 Bucket does not have logging enabled

Issue: -

## Description

Buckets should have logging enabled so that access can be audited.

**Resolution**: Add a logging block to the resource to enable access logging.

## Examples

Example of **incorrect** code:

```terraform
resource "aws_s3_bucket" "bad_example" {

}
```

Example of **correct** code:

```terraform
resource "aws_s3_bucket" "good_example" {
	logging {
		target_bucket = "target-bucket"
	}
}
```