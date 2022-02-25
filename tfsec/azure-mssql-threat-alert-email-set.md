Pattern: Missing email for Azure SQL Server threat alert

Issue: -

## Description

SQL Server sends alerts for threat detection via email, if there are no email addresses set then mitigation will be delayed.

**Resolution**: Provide at least one email address for threat alerts.

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
  email_addresses = []
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
  disabled_alerts = [
    "Sql_Injection",
    "Data_Exfiltration"
  ]
  email_addresses = ["db-security@acme.org"]
}
```