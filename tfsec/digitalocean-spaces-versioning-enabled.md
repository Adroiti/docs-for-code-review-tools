Pattern: Disabled versioning for Spaces bucket

Issue: -

## Description

Versioning is a means of keeping multiple variants of an object in the same bucket. You can use the Spaces (S3) Versioning feature to preserve, retrieve, and restore every version of every object stored in your buckets. With versioning you can recover more easily from both unintended user actions and application failures.

**Resolution**: Enable versioning to protect against accidental or malicious removal or modification.

## Examples

Example of **incorrect** code:

```terraform
resource "digitalocean_spaces_bucket" "bad_example" {
  name   = "foobar"
  region = "nyc3"
}

resource "digitalocean_spaces_bucket" "bad_example" {
  name   = "foobar"
  region = "nyc3"

  versioning {
	enabled = false	
  }
}
```

Example of **correct** code:

```terraform
resource "digitalocean_spaces_bucket" "good_example" {
  name   = "foobar"
  region = "nyc3"

  versioning {
	enabled = true
  }
}
```