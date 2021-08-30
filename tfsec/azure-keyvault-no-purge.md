Pattern: Key vault should have purge protection enabled

Issue: -

## Description

Purge protection is an optional Key Vault behavior and is not enabled by default.

Purge protection can only be enabled once soft-delete is enabled. It can be turned on via CLI or PowerShell.

**Resolution**: Enable purge protection for key vaults.

## Examples

Example of **incorrect** code:

```terraform
resource "azurerm_key_vault" "bad_example" {
    name                        = "examplekeyvault"
    location                    = azurerm_resource_group.bad_example.location
    enabled_for_disk_encryption = true
    purge_protection_enabled    = false
}
```

Example of **correct** code:

```terraform
resource "azurerm_key_vault" "good_example" {
    name                        = "examplekeyvault"
    location                    = azurerm_resource_group.good_example.location
    enabled_for_disk_encryption = true
    soft_delete_retention_days  = 7
    purge_protection_enabled    = true
}
```