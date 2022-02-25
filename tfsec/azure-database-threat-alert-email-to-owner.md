Pattern: Disabled email for database security alerts to Azure owner(s)

Issue: -

## Description

Subscription owners should be notified when there are security alerts. By ensuring the administrators of the account have been notified they can quickly assist in any required remediation

**Resolution**: Enable email to subscription owners.

## Examples

The following example will fail the azure-database-threat-alert-email-to-owner check.

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

The following example will pass the azure-database-threat-alert-email-to-owner check.

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

## Further reading

- [https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/mssql_server_security_alert_policy#email_account_admins](https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/mssql_server_security_alert_policy#email_account_admins)