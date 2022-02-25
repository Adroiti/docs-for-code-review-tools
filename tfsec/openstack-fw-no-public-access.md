Pattern: Use of public firewall rule for OpenStack

Issue: -

## Description

Opening up ports to the public internet is generally to be avoided. You should restrict access to IP addresses or ranges that explicitly require it where possible.

**Resolution**: Employ more restrictive firewall rules.

## Examples

Example of **incorrect** code:

```terraform
resource "openstack_fw_rule_v1" "rule_1" {
	name             = "my_rule"
	description      = "let anyone in"
	action           = "allow"
	protocol         = "tcp"
	destination_port = "22"
	enabled          = "true"
}
```

Example of **correct** code:

```terraform
resource "openstack_fw_rule_v1" "rule_1" {
	name                   = "my_rule"
	description            = "don't let just anyone in"
	action                 = "allow"
	protocol               = "tcp"
	destination_ip_address = "10.10.10.1"
	source_ip_address      = "10.10.10.2"
	destination_port       = "22"
	enabled                = "true"
}
```