Pattern: Missing description for OpenStack security group

Issue: -

## Description

Security groups should include a description for auditing purposes. Simplifies auditing, debugging, and managing security groups.

**Resolution**: Add descriptions for all security groups.

## Examples

The following example will fail the openstack-networking-describe-security-group check.
```terraform

 resource "openstack_networking_secgroup_v2" "group_1" {
 }
 			
```

The following example will pass the openstack-networking-describe-security-group check.
```terraform

 resource "openstack_networking_secgroup_v2" "group_1" {
 	description            = "don't let just anyone in"
 }
 			
``

## Further reading

