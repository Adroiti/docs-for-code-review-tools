Pattern: Unencrypted Azure Data Lake storage

Issue: -

## Description

Data Lake storage encryption defaults to Enabled, it shouldn't be overridden to Disabled.

**Resolution**: Enable encryption of data lake storage.

## Examples

Example of **incorrect** code:

```terraform
resource "azurerm_data_lake_store" "bad_example" {
	encryption_state = "Disabled"
}
```

Example of **correct** code:

```terraform
resource "azurerm_data_lake_store" "good_example" {
	encryption_state = "Enabled"
}
```