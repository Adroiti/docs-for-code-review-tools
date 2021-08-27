Pattern: Use of RSA SHA1 for Zone signing

Issue: -

## Description

RSA SHA1 is a weaker algorithm than SHA2-based algorithms such as RSA SHA256/512

**Resolution**: Use RSA SHA512.

## Examples

Example of **incorrect** code:

```terraform
resource "google_dns_managed_zone" "foo" {
	name     = "foobar"
	dns_name = "foo.bar."
	
	dnssec_config {
		state         = "on"
		non_existence = "nsec3"
	}
}
	
data "google_dns_keys" "foo_dns_keys" {
	managed_zone = google_dns_managed_zone.foo.id
	zone_signing_keys {
		algorithm = "rsasha1"
	}
}
	
output "foo_dns_ds_record" {
	description = "DS record of the foo subdomain."
	value       = data.google_dns_keys.foo_dns_keys.key_signing_keys[0].ds_record
}
```

Example of **correct** code:

```terraform
resource "google_dns_managed_zone" "foo" {
	name     = "foobar"
	dns_name = "foo.bar."
	
	dnssec_config {
		state         = "on"
		non_existence = "nsec3"
	}
}
	
data "google_dns_keys" "foo_dns_keys" {
	managed_zone = google_dns_managed_zone.foo.id
	zone_signing_keys {
		algorithm = "rsasha512"
	}
}
	
output "foo_dns_ds_record" {
	description = "DS record of the foo subdomain."
	value       = data.google_dns_keys.foo_dns_keys.key_signing_keys[0].ds_record
}
```