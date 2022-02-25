Pattern: Disabled threat alerts for Azure SQL server

Issue: -

## Description

SQL Server can alert for security issues including SQL Injection, vulnerabilities, access anomalies and data ex-filtration. Ensure none of these are disabled to benefit from the best protection

**Resolution**: Use all provided threat alerts.

## Examples

Example of **incorrect** code:

```terraform
resource "azurerm_mssql_server_security_alert_policy" "bad_example" {
  resource_group_name        = azurerm_resource_group.example.name
  server_name                = azurerm_sql_server.example.name
  state                      = "Enabled"
  storage_endpoint           = azurerm_storage_account.example.primary_blob_endpoint
  storage_account_access_key = azurerm_storage_account.example.primary_access_key
  disabled_alerts = [
    "Sql_Injection",
    "Data_Exfiltration"
  ]
  retention_days = 20
}
```

Example of **correct** code:

```terraform
resource "azurerm_mssql_server_security_alert_policy" "good_example" {
  resource_group_name        = azurerm_resource_group.example.name
  server_name                = azurerm_sql_server.example.name
  state                      = "Enabled"
  storage_endpoint           = azurerm_storage_account.example.primary_blob_endpoint
  storage_account_access_key = azurerm_storage_account.example.primary_access_key
  disabled_alerts = []
  retention_days = 20
}
```