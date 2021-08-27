Pattern: Disabled SSL for database connection

Issue: -

## Description

SSL connections should be enforced were available to ensure secure transfer and reduce the risk of compromising data in flight.

**Resolution**: Enable SSL enforcement.

## Examples

Example of **incorrect** code:

```terraform
resource "azurerm_postgresql_server" "bad_example" {
  name                = "bad_example"

  public_network_access_enabled    = false
  ssl_enforcement_enabled          = false
  ssl_minimal_tls_version_enforced = "TLS1_2"
}
```

Example of **correct** code:

```terraform
resource "azurerm_postgresql_server" "good_example" {
  name                = "good_example"

  public_network_access_enabled    = false
  ssl_enforcement_enabled          = true
  ssl_minimal_tls_version_enforced = "TLS1_2"
}
```