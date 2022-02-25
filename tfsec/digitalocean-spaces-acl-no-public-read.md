Pattern: Use of public ACL for DigitalOcean Spaces bucket

Issue: -

## Description

Space bucket and bucket object permissions should be set to deny public access unless explicitly required.

**Resolution**: Apply a more restrictive ACL.

## Examples

Example of **incorrect** code:

```terraform
resource "digitalocean_spaces_bucket" "bad_example" {
  name   = "public_space"
  region = "nyc3"
  acl    = "public-read"
}

resource "digitalocean_spaces_bucket_object" "index" {
  region       = digitalocean_spaces_bucket.bad_example.region
  bucket       = digitalocean_spaces_bucket.bad_example.name
  key          = "index.html"
  content      = "<html><body><p>This page is empty.</p></body></html>"
  content_type = "text/html"
  acl          = "public-read"
}
```

Example of **correct** code:

```terraform
resource "digitalocean_spaces_bucket" "good_example" {
  name   = "private_space"
  region = "nyc3"
  acl    = "private"
}
  
resource "digitalocean_spaces_bucket_object" "index" {
  region       = digitalocean_spaces_bucket.good_example.region
  bucket       = digitalocean_spaces_bucket.good_example.name
  key          = "index.html"
  content      = "<html><body><p>This page is empty.</p></body></html>"
  content_type = "text/html"
}
```