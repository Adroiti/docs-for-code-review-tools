Pattern: Missing use of `aws_s3_bucket_public_access_block`

Issue: -

## Description

The “block public access” settings in S3 override individual policies that apply to a given bucket, meaning that all public access can be controlled in one central definition for that bucket. It is therefore good practice to define these settings for each bucket in order to clearly define the public access that can be allowed for it.

**Resolution**: Define a `aws_s3_bucket_public_access_block` for the given bucket to control public access policies.

## Examples

Example of **incorrect** code:

```terraform
resource "aws_s3_bucket" "example" {
	bucket = "example"
	acl = "private-read"
}
```

Example of **correct** code:

```terraform
resource "aws_s3_bucket" "example" {
	bucket = "example"
	acl = "private-read"
}
  
resource "aws_s3_bucket_public_access_block" "example" {
	bucket = aws_s3_bucket.example.id
	block_public_acls   = true
	block_public_policy = true
}
```