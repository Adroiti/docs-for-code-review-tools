Pattern: Missing Microsoft services bypass for Azure storage

Issue: -

## Description

Some Microsoft services that interact with storage accounts operate from networks that can't be granted access through network rules. 

To help this type of service work as intended, allow the set of trusted Microsoft services to bypass the network rules

**Resolution**: Allow Trusted Microsoft Services to bypass.

## Examples

Example of **incorrect** code:

```terraform
resource "azurerm_storage_account" "bad_example" {
  name                = "storageaccountname"
  resource_group_name = azurerm_resource_group.example.name

  location                 = azurerm_resource_group.example.location
  account_tier             = "Standard"
  account_replication_type = "LRS"

  network_rules {
    default_action             = "Deny"
    ip_rules                   = ["100.0.0.1"]
    virtual_network_subnet_ids = [azurerm_subnet.example.id]
	bypass                     = ["Metrics"]
  }

  tags = {
    environment = "staging"
  }
}

resource "azurerm_storage_account_network_rules" "test" {
  resource_group_name  = azurerm_resource_group.test.name
  storage_account_name = azurerm_storage_account.test.name

  default_action             = "Allow"
  ip_rules                   = ["127.0.0.1"]
  virtual_network_subnet_ids = [azurerm_subnet.test.id]
  bypass                     = ["Metrics"]
}
```

Example of **correct** code:

```terraform
resource "azurerm_storage_account" "good_example" {
  name                = "storageaccountname"
  resource_group_name = azurerm_resource_group.example.name

  location                 = azurerm_resource_group.example.location
  account_tier             = "Standard"
  account_replication_type = "LRS"

  network_rules {
    default_action             = "Deny"
    ip_rules                   = ["100.0.0.1"]
    virtual_network_subnet_ids = [azurerm_subnet.example.id]
    bypass                     = ["Metrics", "AzureServices"]
  }

  tags = {
    environment = "staging"
  }
}

resource "azurerm_storage_account_network_rules" "test" {
  resource_group_name  = azurerm_resource_group.test.name
  storage_account_name = azurerm_storage_account.test.name

  default_action             = "Allow"
  ip_rules                   = ["127.0.0.1"]
  virtual_network_subnet_ids = [azurerm_subnet.test.id]
  bypass                     = ["Metrics", "AzureServices"]
}
```