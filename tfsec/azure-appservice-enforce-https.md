Pattern: Ensure the Function App can only be accessed via HTTPS. The default is false

Issue: -

## Description

By default, clients can connect to function endpoints by using both HTTP or HTTPS. You should redirect HTTP to HTTPs because HTTPS uses the SSL/TLS protocol to provide a secure connection, which is both encrypted and authenticated.

**Resolution**: You can redirect all HTTP requests to the HTTPS port..

## Examples

Example of **incorrect** code:

```terraform
resource "azurerm_function_app" "bad_example" {
  name                       = "test-azure-functions"
  location                   = azurerm_resource_group.example.location
  resource_group_name        = azurerm_resource_group.example.name
  app_service_plan_id        = azurerm_app_service_plan.example.id
  storage_account_name       = azurerm_storage_account.example.name
  storage_account_access_key = azurerm_storage_account.example.primary_access_key
  os_type                    = "linux"
}
```

Example of **correct** code:

```terraform
resource "azurerm_function_app" "good_example" {
  name                       = "test-azure-functions"
  location                   = azurerm_resource_group.example.location
  resource_group_name        = azurerm_resource_group.example.name
  app_service_plan_id        = azurerm_app_service_plan.example.id
  storage_account_name       = azurerm_storage_account.example.name
  storage_account_access_key = azurerm_storage_account.example.primary_access_key
  os_type                    = "linux"
  https_only                 = true
}
```