Pattern: Missing use of all Azure SQL Server threat alerts

Issue: -

## Description

SQL Server can alert for security issues including SQL Injection, vulnerabilities, access anomalies and data ex-filtration. Ensure none of these are disabled to benefit from the best protection.

**Resolution**: Use all provided threat alerts.

## Examples

The following example will fail the azure-database-all-threat-alerts-enabled check.
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

The following example will pass the azure-database-all-threat-alerts-enabled check.
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

## Further reading

- [https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/mssql_server_security_alert_policy#disabled_alerts](https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/mssql_server_security_alert_policy#disabled_alerts)