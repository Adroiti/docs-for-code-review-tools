Pattern: Missing Python version for App Service Web app

Issue: -

## Description

Azure App Service web applications developed with the Python should use the latest available version of Python to ensure the latest security fixes are in use.

**Resolution**: ensure latest Python version is being used.

## Examples

Example of **incorrect** code:

```terraform
resource "azurerm_app_service" "good_example" {
	name                = "example-app-service"
	location            = azurerm_resource_group.example.location
	resource_group_name = azurerm_resource_group.example.name
	app_service_plan_id = azurerm_app_service_plan.example.id
	site_config {
	  python_version = "2.7"
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
  site_config {
    python_version = "3.4"
  }
}
```