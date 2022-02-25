Pattern: Enabled Azure App Service FTP deployments

Issue: -

## Description

FTPS (Secure FTP) is used to enhance security for Azure web application using App Service as it adds an extra layer of security to the FTP protocol, and help you to comply with the industry standards and regulations. For enhanced security, it is highly advices to use FTP over TLS/SSL only. You can also disable both FTP and FTPS if you don't use FTP deployment.

**Resolution**: disable FTP.

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
		ftps_state = "Disabled"
	}
}
```