Pattern: Use of insecure TLS policy for Azure database

Issue: -

## Description

You should not use outdated/insecure TLS versions for encryption. You should be using TLS v1.2+.

**Resolution**: Use the most modern TLS policies available.

## Examples

Example of **incorrect** code:

```terraform
resource "azurerm_mssql_server" "bad_example" {
  name                         = "mssqlserver"
  resource_group_name          = azurerm_resource_group.example.name
  location                     = azurerm_resource_group.example.location
  version                      = "12.0"
  administrator_login          = "missadministrator"
  administrator_login_password = "thisIsKat11"
  minimum_tls_version          = "1.1"
}

resource "azurerm_postgresql_server" "bad_example" {
	name                = "bad_example"
  
	public_network_access_enabled    = true
	ssl_enforcement_enabled          = false
	ssl_minimal_tls_version_enforced = "TLS1_1"
  }
```

Example of **correct** code:

```terraform
resource "azurerm_mssql_server" "good_example" {
  name                         = "mssqlserver"
  resource_group_name          = azurerm_resource_group.example.name
  location                     = azurerm_resource_group.example.location
  version                      = "12.0"
  administrator_login          = "missadministrator"
  administrator_login_password = "thisIsKat11"
  minimum_tls_version          = "1.2"
}

resource "azurerm_postgresql_server" "good_example" {
  name                = "bad_example"

  public_network_access_enabled    = true
  ssl_enforcement_enabled          = false
  ssl_minimal_tls_version_enforced = "TLS1_2"
}
```