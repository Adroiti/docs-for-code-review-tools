Pattern: S3 Data should be versioned

Issue: -

## Description

Versioning in Amazon S3 is a means of keeping multiple variants of an object in the same bucket. 
You can use the S3 Versioning feature to preserve, retrieve, and restore every version of every object stored in your buckets. 
With versioning you can recover more easily from both unintended user actions and application failures.

**Resolution**: Enable versioning to protect against accidental/malicious removal or modification.

## Examples

Example of **incorrect** code:

```terraform
resource "aws_s3_bucket" "bad_example" {

}
```

Example of **correct** code:

```terraform
resource "aws_s3_bucket" "good_example" {

	versioning {
		enabled = true
	}
}
```