Pattern: Use of insecure TLS policy for Google Compute

Issue: -

## Description

TLS versions prior to 1.2 are outdated and insecure. You should use 1.2 as minimum version.

**Resolution**: Enforce a minimum TLS version of 1.2.

## Examples

Example of **incorrect** code:

```terraform
resource "google_compute_ssl_policy" "bad_example" {
  name    = "production-ssl-policy"
  profile = "MODERN"
  min_tls_version = "TLS_1_1"
}
```

Example of **correct** code:

```terraform
resource "google_compute_ssl_policy" "good_example" {
  name    = "production-ssl-policy"
  profile = "MODERN"
  min_tls_version = "TLS_1_2"
}
```