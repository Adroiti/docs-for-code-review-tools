Pattern: Use of public IP for Oracle

Issue: -

## Description

Compute instance requests an IP reservation from a public pool

The compute instance has the ability to be reached from outside, you might want to sonder the use of a non public IP.

**Resolution**: Reconsider the use of an public IP.

## Examples

Example of **incorrect** code:

```terraform
resource "opc_compute_ip_address_reservation" "my-ip-address" {
	name            = "my-ip-address"
	ip_address_pool = "public-ippool"
  }
```

Example of **correct** code:

```terraform
resource "opc_compute_ip_address_reservation" "my-ip-address" {
	name            = "my-ip-address"
	ip_address_pool = "cloud-ippool"
  }
```