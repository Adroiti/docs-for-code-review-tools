Pattern: Enabled force destroy on DigitalOcean Spaces bucket

Issue: -

## Description

Enabling force destroy on a Spaces bucket means that the bucket can be deleted without the additional check that it is empty. This risks important data being accidentally deleted by a bucket removal process.

**Resolution**: Don't use force destroy on bucket configuration.

## Examples

Example of **incorrect** code:

```terraform
resource "digitalocean_spaces_bucket" "bad_example" {
  name   		= "foobar"
  region 		= "nyc3"
  force_destroy = true
}
```

Example of **correct** code:

```terraform
resource "digitalocean_spaces_bucket" "good_example" {
  name   = "foobar"
  region = "nyc3"
}
```