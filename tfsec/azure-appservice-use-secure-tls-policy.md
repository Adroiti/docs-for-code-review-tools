Pattern: Use of insecure TLS/SSL policy for Azure App Service

Issue: -

## Description

The TLS version being outdated and has known vulnerabilities.

**Resolution**: Use a more recent TLS/SSL policy for the App Service.

## Examples

Example of **incorrect** code:

```terraform
resource "azurerm_app_service" "bad_example" {
  name                = "example-app-service"
  location            = azurerm_resource_group.example.location
  resource_group_name = azurerm_resource_group.example.name
  app_service_plan_id = azurerm_app_service_plan.example.id

  site_config {
	  min_tls_version = "1.0"
  }
}
```

Example of **correct** code:

```terraform
resource "azurerm_app_service" "good_example" {
  name                = "example-app-service"
  location            = azurerm_resource_group.example.location
  resource_group_name = azurerm_resource_group.example.name
  app_service_plan_id = azurerm_app_service_plan.example.id
}
```