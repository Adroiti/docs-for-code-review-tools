Pattern: Unset retention period for Azure database

Issue: -

## Description

When Auditing is configured for a SQL database, if the retention period is not set, the retention will be unlimited.

If the retention period is to be explicitly set, it should be set for no less than `90` days.

**Resolution**: Set retention periods of database auditing to greater than `90` days.

## Examples

Example of **incorrect** code:

```terraform
resource "azurerm_mssql_database_extended_auditing_policy" "bad_example" {
  database_id                             = azurerm_mssql_database.example.id
  storage_endpoint                        = azurerm_storage_account.example.primary_blob_endpoint
  storage_account_access_key              = azurerm_storage_account.example.primary_access_key
  storage_account_access_key_is_secondary = false
  retention_in_days                       = 6
}
```

Example of **correct** code:

```terraform
resource "azurerm_mssql_database_extended_auditing_policy" "good_example" {
  database_id                             = azurerm_mssql_database.example.id
  storage_endpoint                        = azurerm_storage_account.example.primary_blob_endpoint
  storage_account_access_key              = azurerm_storage_account.example.primary_access_key
  storage_account_access_key_is_secondary = false
}

resource "azurerm_mssql_database_extended_auditing_policy" "good_example" {
  database_id                             = azurerm_mssql_database.example.id
  storage_endpoint                        = azurerm_storage_account.example.primary_blob_endpoint
  storage_account_access_key              = azurerm_storage_account.example.primary_access_key
  storage_account_access_key_is_secondary = false
  retention_in_days                       = 90
}
```