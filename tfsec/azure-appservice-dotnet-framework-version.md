Pattern: Missing .NET version for App Service Web app

Issue: -

## Description

Azure App Service web applications developed with the .NET software stack should use the latest available version of .NET to ensure the latest security fixes are in use.

**Resolution**: Use the latest version of the .NET framework.

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
resource "azurerm_app_service" "good_example" {
  name                = "example-app-service"
  location            = azurerm_resource_group.example.location
  resource_group_name = azurerm_resource_group.example.name
  app_service_plan_id = azurerm_app_service_plan.example.id

  site_config {
	dotnet_framework_version = "v5.0"
  }
}
```