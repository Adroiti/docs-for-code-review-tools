Pattern: Use of HTTP for Azure App Service

Issue: -

## Description

By default, clients can connect to App Service by using both HTTP or HTTPS. HTTP should be disabled enabling the HTTPS Only setting.

**Resolution**: enable HTTPS only.

## Examples

Example of **incorrect** code:

```terraform
resource "azurerm_app_service" "bad_example" {
        name                       = "example-app-service"
        location                   = azurerm_resource_group.example.location
        resource_group_name        = azurerm_resource_group.example.name
        app_service_plan_id        = azurerm_app_service_plan.example.id
      }
```

Example of **correct** code:

```terraform
resource "azurerm_app_service" "good_example" {
        name                       = "example-app-service"
        location                   = azurerm_resource_group.example.location
        resource_group_name        = azurerm_resource_group.example.name
        app_service_plan_id        = azurerm_app_service_plan.example.id
        https_only                 = true
      }
```