Pattern: Disabled HTTP logging for Azure App Service

Issue: -

## Description

Raw HTTP request data in the W3C extended log file format. Each log message includes data such as the HTTP method, resource URI, client IP, client port, user agent, response code, and so on.

**Resolution**: enable `http_logs`.

## Examples

Example of **incorrect** code:

```terraform
resource "azurerm_app_service" "bad_example" {
  name                = "example-app-service"
  location            = azurerm_resource_group.example.location
  resource_group_name = azurerm_resource_group.example.name
  app_service_plan_id = azurerm_app_service_plan.example.id
}
```

Example of **correct** code:

```terraform
resource "azurerm_app_service" "good_example_one" {
  name                = "example-app-service"
  location            = azurerm_resource_group.example.location
  resource_group_name = azurerm_resource_group.example.name
  app_service_plan_id = azurerm_app_service_plan.example.id
  logs {
    http_logs {
	  file_system {
		retention_in_days = 4
		retention_in_mb  = 25
	  }
	}
  }
}
```