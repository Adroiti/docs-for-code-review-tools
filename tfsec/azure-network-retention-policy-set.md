Pattern: Unset log retention for Azure Flow

Issue: -

## Description

Flow logs are the source of truth for all network activity in your cloud environment. 
To enable analysis in security event that was detected late, you need to have the logs available.

Setting an retention policy will help ensure as much information is available for review.

**Resolution**: Ensure flow log retention is turned on with an expiry of >`90` days.

## Examples

Example of **incorrect** code:

```terraform
resource "azurerm_network_watcher_flow_log" "bad_watcher" {
  network_watcher_name = "bad_watcher"
  resource_group_name  = "resource-group"

  network_security_group_id = azurerm_network_security_group.test.id
  storage_account_id        = azurerm_storage_account.test.id
  enabled                   = true

  retention_policy {
    enabled = true
    days    = 7
  }
}
```

Example of **correct** code:

```terraform
resource "azurerm_network_watcher_flow_log" "good_watcher" {
  network_watcher_name = "good_watcher"
  resource_group_name  = "resource-group"

  network_security_group_id = azurerm_network_security_group.test.id
  storage_account_id        = azurerm_storage_account.test.id
  enabled                   = true

  retention_policy {
    enabled = true
    days    = 90
  }
}
```