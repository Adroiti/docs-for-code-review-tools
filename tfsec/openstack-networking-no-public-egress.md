Pattern: Use of egress public access for OpenStack Compute

Issue: -

## Description

Opening up ports to the public internet is generally to be avoided. You should restrict access to IP addresses or ranges that explicitly require it where possible.

**Resolution**: Employ more restrictive security group rules.

## Examples

The following example will fail the openstack-compute-no-public-access check.

```terraform
 resource "openstack_networking_secgroup_rule_v2" "rule_1" {
    direction         = "egress"
    ethertype         = "IPv4"
    protocol          = "tcp"
    port_range_min    = 22
    port_range_max    = 22
    remote_ip_prefix  = "0.0.0.0/0"
 }
```

The following example will pass the openstack-compute-no-public-access check.
```terraform
resource "openstack_networking_secgroup_rule_v2" "rule_1" {
    direction         = "egress"
    ethertype         = "IPv4"
    protocol          = "tcp"
    port_range_min    = 22
    port_range_max    = 22
    remote_ip_prefix  = "1.2.3.4/32"
}
```