Pattern: Use of public access ACL for AWS S3 bucket

Issue: -

## Description

S3 bucket permissions should be set to deny public access unless explicitly required.

Granting write access publicly with `public-read-write` is especially dangerous as you will be billed for any uploaded files.

Additionally, you should not use the `authenticated-read` canned ACL, as this provides read access to any authenticated AWS user, not just AWS users within your organization.

**Resolution**: Apply a more restrictive bucket ACL.

## Examples

Example of **incorrect** code:

```terraform
resource "aws_s3_bucket" "bad_example" {
	acl = "public-read"
}
```

Example of **correct** code:

```terraform
resource "aws_s3_bucket" "good_example" {
	acl = "private"
}
```