Pattern: Use of sensitive data in `user_data` for `cloudstack_instance`

Issue: -

## Description

When creating instances, user data can be used during the initial configuration. User data must not contain sensitive information

**Resolution**: Don't use sensitive data in the user data section.

## Examples

Example of **incorrect** code:

```terraform
resource "cloudstack_instance" "web" {
  name             = "server-1"
  service_offering = "small"
  network_id       = "6eb22f91-7454-4107-89f4-36afcdf33021"
  template         = "CentOS 6.5"
  zone             = "zone-1"
  user_data        = <<EOF
export DATABASE_PASSWORD=\"SomeSortOfPassword\"
EOF
}
```

Example of **correct** code:

```terraform
resource "cloudstack_instance" "web" {
  name             = "server-1"
  service_offering = "small"
  network_id       = "6eb22f91-7454-4107-89f4-36afcdf33021"
  template         = "CentOS 6.5"
  zone             = "zone-1"
  user_data        = <<EOF
export GREETING="Hello there"
EOF
}
```