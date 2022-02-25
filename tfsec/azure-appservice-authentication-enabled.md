Pattern: Disabled Azure App Service authentication

Issue: -

## Description

Enabling authentication ensures that all communications in the application are authenticated. The auth_settings block needs to be filled out with the appropriate auth backend settings

**Resolution**: Enable authentication to prevent anonymous request being accepted.

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

  auth_settings {
    enabled = true
  }
}
```