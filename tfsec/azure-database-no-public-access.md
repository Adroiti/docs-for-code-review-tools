Pattern: Enabled public access for database

Issue: -

## Description

Database resources should not be publicly available. You should limit all access to the minimum that is required for your application to function.

**Resolution**: Disable public access to database when not required.

## Examples

Example of **incorrect** code:

```terraform
resource "azurerm_postgresql_server" "bad_example" {
  name                = "bad_example"

  public_network_access_enabled    = true
  ssl_enforcement_enabled          = false
  ssl_minimal_tls_version_enforced = "TLS1_2"
}
```

Example of **correct** code:

```terraform
resource "azurerm_postgresql_server" "good_example" {
  name                = "bad_example"

  public_network_access_enabled    = false
  ssl_enforcement_enabled          = false
  ssl_minimal_tls_version_enforced = "TLS1_2"
}
```