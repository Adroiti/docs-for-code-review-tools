Pattern: S3 Access block should restrict public bucket to limit access

Issue: -

## Description

S3 buckets should restrict public policies for the bucket. By enabling, the restrict_public_buckets, only the bucket owner and AWS Services can access if it has a public policy.

**Resolution**: Limit the access to public buckets to only the owner or AWS Services (eg; CloudFront).

## Examples

Example of **incorrect** code:

```terraform
resource "aws_s3_bucket_public_access_block" "bad_example" {
	bucket = aws_s3_bucket.example.id
}

resource "aws_s3_bucket_public_access_block" "bad_example" {
	bucket = aws_s3_bucket.example.id
  
	restrict_public_buckets = false
}
```

Example of **correct** code:

```terraform
resource "aws_s3_bucket_public_access_block" "good_example" {
	bucket = aws_s3_bucket.example.id
  
	restrict_public_buckets = true
}
```