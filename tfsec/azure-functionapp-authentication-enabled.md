Pattern: Disabled Function App authentication

Issue: -

## Description

Enabling authentication ensures that all communications in the application are authenticated. The `auth_settings` block needs to be filled out with the appropriate auth backend settings.

**Resolution**: enable authentication to prevent anonymous request being accepted.

## Examples

Example of **incorrect** code:

```terraform
resource "azurerm_function_app" "bad_example" {
  name                = "example-function-app"
  location            = azurerm_resource_group.example.location
  resource_group_name = azurerm_resource_group.example.name
  app_service_plan_id = azurerm_function_app_plan.example.id
}
```

Example of **correct** code:

```terraform
resource "azurerm_function_app" "good_example" {
  name                = "example-function-app"
  location            = azurerm_resource_group.example.location
  resource_group_name = azurerm_resource_group.example.name
  app_service_plan_id = azurerm_function_app_plan.example.id

  auth_settings {
    enabled = true
  }
}
```