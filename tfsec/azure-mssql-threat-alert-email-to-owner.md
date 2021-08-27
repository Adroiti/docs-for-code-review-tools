Pattern: Ensure email is enabled for SQL Server subscription owners

Issue: -

## Description

Subscription owners should be notified when there are security alerts. By ensuring the administrators of the account have been notified they can quickly assist in any required remediation

**Resolution**: Enable email to subscription owners.

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
  ]
  email_account_admins = false
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

  email_account_admins = true
}
```